# WebSockets in libcurl - draft

For a long time people have expressed wishes and ideas about getting WebSockets support added to curl. Every year in the annual survey a large portion of users say they'd like it.

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

- Set `CURLOPT_CONNECT_ONLY` to `2` to tell libcurl to do the
  WebSockets upgrade dance only and then return to the application for
  `curl_easy_perform()`.
- New functions for recv/send so that we can pass on extra flags for
  websockets use (like end of packet flag, compression, binary/text etc)

## Outstanding questions

- how to set/change the maximum allowed message-size?

- do we need a `curl_ws_poll()` for the `CONNECT_ONLY` use case? It could wait
  for websockets activity and transparently handle ping/pongs.

## `CURLOPT_URL`

Setting a URL with the scheme `ws://` or `wss://` marks this as a WebSockets
transfer.

## `curl_ws_send`

    curl_ws_send( easy, buffer, buflen, &sent, sendflags );

Send a websocket frame.

## `curl_ws_recv`

    curl_ws_recv( easy, buffer, buflen, &recvflags )

Received a websocket frame.

## `curl_ws_poll`?

Pending.

## `CURLOPT_WS_OPTIONS`

A new *setopt() option that sets a bitmask:

- `CURLWS_COMPRESS` - negotiate compression for this transfer
- `CURLWS_PINGOFF` - disable automated ping/pong handling

## `CURLOPT_WS_WRITEFUNCTION`

This sets a websockets write callback to which libcurl will deliver incoming
*messages*.

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
  /* just using select() or curl_ws_poll() ? */
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

curl_easy_setopt(ws, CURLOPT_WS_WRITEFUNCTION, write_cb);
curl_easy_setopt(ws, CURLOPT_WS_WRITEDATA, &writep);

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
