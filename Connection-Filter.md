# Connection Filter

With increasing variation in Curl connection handling, the complexity of adding cases in `if/else` code branches
becomes a burden. The goal of adding HTTP/2 proxying gives the opportunity to rethink a bit how connections
are handled.

## Current state

`struct connectdata` (`lib/urldata.h:918`) is a collection for all possible things around a connection for a `Curl_easy`. The quirks of all possible protocol end up here: QUIC, socks_proxy, http_proxy, ssl_connect_data (plain+proxy), ssl_config (plain+proxy), gssapi, kerberos, ntlm (plain+proxy), negotiate_state (plain+proxy), trailer and specific members for each protocol family.

This flattens out all possible combinations of how layering of these protocols may be done. This is a simple, easy model, but it has consequences for the code working with it. That code needs to check which combination is present in an instance and act accordingly.

Another example where the "flat" handling is tricky and the `conndata` members `send/recv`. These function pointers are responsible to passing data back and forth on the connection. Initially, these just use the raw socket. When TLS is used, that implementation replaces them with its own that work on the SSL*. The SSL* is told to use the original socket via `SSL_set_fd()`.

Of course, when a https: proxy is in place, it has already done that and the same thing does not work twice. Instead, it fetched the SSL* from the proxy and builds a chain via `BIO_set_ssl()` to chain the two SSL* instances. This will not work for a HTTP/2 proxy, as the encrypted data needs to go over a H2 stream inside the underlying proxy SSL*.

So, something needs to give.

## What To Do?

Apache httpd has the concept of "filters" that can be installed in input or output of a connection or for a request. Data passes through the filters which may modify/supplement them or pass it on unchanged. A filter may just hang in there and wait for the end of a response, do brotli compression or perform the TLS de-/encryption.

One can apply the same concept in curl. That could look like this (partial, not all types declared):

```
typedef ssize_t  Curl_cf_recv(
  struct Curl_conn_filter *f,
  struct Curl_easy *data,   /* transfer */
  char *buf,                /* store data here */
  size_t len,               /* max amount to read */
  CURLcode *err);           /* error to return */
...

struct Curl_conn_filter_handler {
  const char *name;                      /* name of the filter handler */
  Curl_cf_connect *connect;              /* establish conn */
  Curl_cf_connect *close;                /* close conn */
  Curl_cf_destroy *destroy;              /* destroy resources held by filter */
  Curl_cf_getsock *get_wait_socket;      /* get socket to wait on for progress */
  Curl_cf_is_connected *is_connected;    /* conn is established */
  Curl_cf_is_alive *is_alive;            /* conn is alive */
  Curl_cf_data_pending *has_data_pending;/* conn has data pending */
  Curl_cf_send *send;                    /* send data */
  Curl_cf_recv *recv;                    /* receive data */
};

struct Curl_conn_filter {
  const struct Curl_conn_filter_handler *h; /* the handler who does things */
  struct Curl_conn_filter *next;            /* next filter in chain */
  struct connectdata *conn;                 /* the connection this belongs to */
  void *ctx;                                /* filter specific settings */
};

CURLcode Curl_conn_filter_setup(struct connectdata *conn, int sockindex);
void Curl_conn_filter_destroy(struct connectdata *conn, int sockindex);

CURLcode Curl_conn_filter_add(struct connectdata *conn, int sockindex,
                              struct Curl_conn_filter *f);
```
The usage pattern would be like this:

```
  Curl_conn_filter_setup(conn, 0);    // sets up RAW TCP Socket filter
  Curl_conn_filter_add(conn, 0, CF_TLS);
  Curl_conn_filter_add(conn, 0, CF_PROXY_CONNECT);
  Curl_conn_filter_add(conn, 0, CF_TLS);
  Curl_conn_filter_add(conn, 0, CF_HTTP1);
```
which gives the structure at runtime of:

```
connectdata.filter_chain0 
   --> CF_HTTP1
         next--> CF_TLS
                   next->CF_PROXY_CONNEXT
                           next ---> CF_TLS
                                       next --> CF_TCP
```

Many members of `conndata` could be migrated into the `Curl_conn_filter` instances. For example the `struct ssl_connect_data *` for TLS filters would be kept there. The overall memory use would probably less in several cases if `conndata` does not have to keep all possible things around. Same for PROXY filters. Things like the HAProxy protocol would also nicely fit.

This design has no limits on stacking. One could to PROXY to a PROXY to a server, etc with as many TLS in between or not.