# Modeling of multiple connections per curl_easy

## Current state

In the internal APIs, often a `socketindex` is passed, because what curl calls a `connection`, or more precisely `struct connectdata`, does represent two connections for `ftp`. No other protocol seems to make use of this (`quic` has 2 extra sockets, but let's disregard that for now).

Example:

```
struct connectdata {
  ...
  curl_socket_t sock[2]; /* two sockets, the second is used for the data
                            transfer when doing FTP */
  curl_socket_t tempsock[2]; /* temporary sockets for happy eyeballs */
  int tempfamily[2]; /* family used for the temp sockets */
  Curl_recv *recv[2];
  Curl_send *send[2];
  ...   
  char *secondaryhostname; /* secondary socket host name (ftp) */
  unsigned short secondary_port; /* secondary socket remote port to connect to (ftp) */
  ...
  struct ssl_connect_data ssl[2]; /* this is for ssl-stuff */
  ...
```

To know which socket they should operate on, many functions in `proxy` and `vtls` get a `sockindex` parameter. Which is then used in `conn->sock[sockindex]` like access, but also to check if `conn->hostname` or `conn->secondaryhostname` is relevant. This design requires duplication of SSL related connection info and also timeout values.

It works, obviously, but it feels as if one protocol is twisting a lot of other code into complications.

## Alternative

Regard `struct connectdata` more as "the context in which connections are made". It holds all information needed to create a connection in a `Curl_easy` instance. Move the members relevant to a connection to a new `struct connection`. Allow for *one or more* connection instances attached to a `Curl_easy`. Maybe as simple as a linked list.

Something like:

```
struct connection {
  struct connectdata *ctx; 
  struct connection *next; /* other connection, side by side */
  curl_socket_t sock; 
  curl_socket_t tempsock;
  int tempfamily;
  Curl_recv *recv;
  Curl_send *send;
  struct ssl_connect_data ssl;
  ...   
}

struct Curl_easy {
  ...
  struct connectdata *conn_ctx;
  struct connection *conn;

```

Then the proxy/vtls functions can work on `struct connection*` alone. Maybe `ctx` can be shared between connections, maybe it is better to have individual copies where lifetimes are more easily managed.

## Virtual Connections

As the `http2` protocol shows, there are connections on top of connections. The `recv_underlying/send_underlying` special `proto` members could be modelled with a virtual connection stacked onto another one. When the http2 protocol "switches", it creates a new `struct connection` wrapping the existing one.

```
struct connection {
  struct connectdata *ctx; 
  struct connection *next; /* other connection, side by side */
  struct connection *underlying; /* NULL, or connection this one wraps */
```

With this, it could be simpler to model a vtls connection on top of a plain socket connection.

## multi curl h2/h3

Once there are "virtual" connections on top of others, it becomes interesting to consider sharing underlying connections in the case of h2 and h3. In h2, this could mean a stack like this:

```
 * Curl_easy has a
 * stream connection on top of
 * a h2 connection on top of
 * a TLS connection on top of
 * a socket connection
```
