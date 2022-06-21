# WebSockets in libcurl

For a long time people have expressed wishes and ideas about getting WebSockets support added to curl. Every year in the annual survey a large portion of users say they'd like it.

**Sponsored by [Corellium](https://www.corellium.com/)**

## Initial work

[PR 8995](https://github.com/curl/curl/pull/8995)

Note that the PR has the final say in documentation and functionality. Details will be removed from this wiki page and added to the documentation in the PR as we progress.

## Specs

- [RFC 6455 - WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)
- [RFC 7692 - Compression](https://datatracker.ietf.org/doc/html/rfc7692)
- [RFC 8441 - Bootstrapping WebSockets with HTTP/2](https://datatracker.ietf.org/doc/html/rfc8441)
- [i-d Bootstrapping WebSockets with HTTP/3](https://www.ietf.org/archive/id/draft-ietf-httpbis-h3-websockets-00.html)

## Aim for what's used

WebSockets is highly extensible. This described API and first implementation do
not aim to support all existing and future extensions. But we should not write
the API or implementation to necessarily prevent us from implementing and
providing support for more extensions in a future.

We should support basic WebSockets and the "common" existing extensions to
make this WebSockets support usable for *most* use cases.

## The curl tool

Due to it being a transport for anything, it isn't ideal for the command line tool. It could possibly be made to work like TELNET does:

 - read from stdin and pass it on to the server
 - send data from server to stdout

Makes it work similar to 'nc'.

# Proposed API

There are two ways to do WebSockets with libcurl:

1. Set `CURLOPT_CONNECT_ONLY` to `2` to tell libcurl to do the WebSockets
  upgrade dance only and then return to the application for
  `curl_easy_perform()`. Then use `curl_ws_send()` and `curl_ws_recv()`.
2. Set a write callback with `CURLOPT_WRITEFUNCTION` and get data delivered to
   that and use `curl_ws_send()` from within the callback to send back
   WebSockets frames.
   
libcurl offers WebSockets handling in different modes:

1. "Raw mode" makes libcurl deliver and send data raw to the application
   without parsing or understanding the protocol. This lets the application do
   all the heavy lifting. Primarily perhaps to work as an interface to legacy
   WebSockets users.
2. "Frame mode" makes libcurl deliver WebSockets frames in the API to the
   application. With each parsed frame comes meta-data and information about
   it.
   
A future enhancement might be to provide a "message mode" that can send full
(multi-frame) messages.

## `CURLOPT_URL`

Setting a URL with the scheme `ws://` or `wss://` marks this as a WebSockets
transfer.

## `curl_ws_send`

    curl_ws_send( easy, buffer, buflen, &sent, sendflags );

Send a websocket frame.

## `curl_ws_recv`

    curl_ws_recv( easy, buffer, buflen, &recvflags )

Received a websocket frame.

## `curl_ws_poll`

Pending.

## `curl_ws_meta`

Pending. Returns information about the incoming WebSockets frame within a
`CURLOPT_WRITEFUNCTION` callback.

## `CURLOPT_WS_OPTIONS`

A new *setopt() option that sets a bitmask:

- `CURLWS_RAW_MODE` - get/send raw websockets data

- `CURLWS_COMPRESS` - negotiate compression for this transfer
- `CURLWS_PINGOFF` - disable automated ping/pong handling

## Multi interface

We want the API to allow for and handle *any* amount of concurrent WebSocket
transfers *in addition* to other libcurl transfers using the same multi
handle.

Therefore, we want WebSockets transfers able to deliver data using a
"WebSocket write callback" for the easy handle. From within that callback, we
should allow `curl_ws_send()` calls, and probably further `curl_ws_recv()`
calls as well.

## Mockup client psuedo source code using `WS_ALONE`

~~~c
CURLcode result;
CURL *ws = curl_easy_init();
curl_easy_setopt(ws, CURLOPT_URL, "ws://websockets.example.org");

/* only do the initial bootstrap */
curl_easy_setopt(ws, CURLOPT_WS_OPTIONS, CURLWS_ALONE);

result = curl_easy_perform(ws);

if(CURLE_OK == result) {
  /* this means it actually negotiated WebSockets successfully */

  /* send data */
  curl_ws_send();

  /* recv data */
  curl_ws_recv();

  /* wait for data to arrive */
  curl_ws_poll();
}

curl_easy_cleanup(ws); /* done */
~~~

## Mockup client psuedo source code using, easy interface with callbacks

~~~c

static int write_cb( ... char *data, size_t len ... ) 
{
  /* WebSocket data from the peer */

  /* If we want to send something here, use curl_ws_send() */
}

CURLcode result;
struct customstuff writep;
CURL *ws = curl_easy_init();
curl_easy_setopt(ws, CURLOPT_URL, "ws://websockets.example.org");

curl_easy_setopt(ws, CURLOPT_WRITEFUNCTION, write_cb);
curl_easy_setopt(ws, CURLOPT_WRITEDATA, &writep);

result = curl_easy_perform(ws);

curl_easy_cleanup(ws); /* done */
~~~

This method also works for the multi interface and then it can do many
parallel transfers and coexist with other protocol transfers in the same main
loop. Also even-based.

# Implementation

There's no implementation yet and the work has yet to be started.

It seems clever to base the implementation on an existing websockets library
for the bits over the wire at least.
[libwebsockets.org](https://libwebsockets.org/) looks like a viable contender.

It is expected that the API and details in this description will need updates
and polish once the implementation starts.

# Ping pong

By default libcurl does ping/pongs transparently without involving the
application. They can be set to "manual mode" with `CURLOPT_WS_OPTIONS`.

# Credits

People who have contributed thoughts and design ideas for this work:

Daniel Stenberg, Dmitry Karpov, Felipe Gasper, Stefan Eissing, Weston Schmidt
