# Nested Connection handling

## Current state

`struct connectdata` (`lib/urldata.h:918`) is a collection for all possible things around a connection for a `Curl_easy`. The quirks of all possible protocol end up here: QUIC, socks_proxy, http_proxy, ssl_connect_data (plain+proxy), ssl_config (plain+proxy), gssapi, kerberos, ntlm (plain+proxy), negotiate_state (plain+proxy), trailer and specific members for each protocol family.

This flattens out all possible combinations of how layering of these protocols may be done. This is a simple, easy model, but it has consequences for the code working with it. That code needs to check which combination is present in an instance and act accordingly.

In contrast, `struct Curl_handler` (`lib/urldata.h:733)`) does not have members for all protocols, but "abstract" function pointers with implementations supplied by each family. `http` and `ftp` implementations of these are ignorant of each other, making their lives simpler.

### HTTP

The Powerhouse of curl started with one instance of a `Curl_handler`. Another, 99% identical, was added for `HTTPS`. This worked well for the 1.x versions of http, since those use all the same "transcoding" (the way a HTTP request/response is represented on the wire). There are tweaks for each version, but mostly they are the same.

With HTTP/2, a complete new transcoding was introduced and, with its multiplexing capabilities, the properties of the connection mappings also changed (`multiuse` of several `Curl_easy` on the same TCP connection when possible).

With HTTP/3, a very similar transcoding to HTTP/2 came, but the underlying connection properties changed from TCP to UDP. The new challenge is that addresses and sockets might change over the lifetime of a H3 connection.

The other special thing about HTTP is Proxy CONNECT (optional with Encryption), meaning establishing a bidirectional byte pipe over which protocol handlers can operate. This is not only used for HTTP(S) requests, but also for FTP. The case for other protocols can be made as well (SSH?).

The HTTP Proxy CONNECT implementation of today faces 2 challenges:
1. It only works for HTTP/1.x proxies
2. It does not re-use much from the HTTP Curl_handler. For example, it has it own `sprintf` request transcoding.

Proxying over HTTP/2 is now in the project plan. It is not unthinkable that H3 will follow one day.

**tl;dr**

1. The current `HTTP` protocol handler code needs to handle too many combinations of versions in its implementation.
1. There is no benefit for PROXY handling by improvements in the HTTP handler.
1. H3 does not exactly help here.

## What To Do?

"further source reading required..."

