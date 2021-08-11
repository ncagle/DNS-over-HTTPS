# WebSockets

For a long time people have expressed wishes and ideas about getting WebSockets support added to curl. Every year in the annual survey a large portion of users say they'd like it.

This is meant as a brain-storm area for writing down how WebSockets in curl could be made to work.

[Weston Schmidt's proposals](https://github.com/schmidtw/curl-websocket-proposal)

Ideas were bouncing on [the curl-library list in June 2021](https://curl.se/mail/lib-2021-06/).

Specs:

- [RFC 6455 - WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)
- [RFC 7692 - Compression](https://datatracker.ietf.org/doc/html/rfc7692)

## Not transfer-oriented

WebSockets is similar to "TCP over HTTP". It provides a bidirectional transport meant for "anything". As such, it doesn't fit the "normal" libcurl transfer paradigms very well. It is rather similar to doing `CONNECT_ONLY` + `curl_easy_send/recv`.

## The curl tool

Due to it being a transport for anything, it isn't ideal for the command line tool. It could possibly be made to work like TELNET does:

 - read from stdin and pass it on to the server
 - send data from server to stdout

Makes it work similar to 'nc'.

# API

- Provide a mode (`WS_ALONE`) that makes `CONNECT_ONLY`-style: only the
  WebSockets upgrade dance and then return to the application for
  `curl_easy_perform()`.
- New functions for recv/send so that we can pass on extra flags for
  websockets use (like end of packet flag, compression, binary/text etc)

## `CURLOPT_URL`

Setting a URL with the scheme `ws://` or `wss://` marks this as a WebSockets
transfer.

## `curl_ws_send`

    curl_ws_send( easy, buffer, buflen, &sent, flags );

**flags** is a bitmask featuring the following flags:

- `CURL_WS_TEXT` - this is text data (binary is default)
- `CURL_WS_NOCOMPRESS` - no-op if there’s no compression anyway
- `CURL_WS_MORE` - this is not the end of the packet

## `curl_ws_recv`

    curl_ws_recv( easy, buffer, buflen, &recvflags, flags )

**recvflags** is a bitmask featuring the following flags:

- `CURL_WS_PARTIAL` - received a partial message (without the FIN flag)

**flags** is a bitmask featuring the following flags:

- `CURL_WS_PARTIAL` - accept partial message

**To deal with**: what if the provided buffer is not big enough to hold the
entire message?

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
  /* just using select() ? */
}

curl_easy_cleanup(ws); /* done */
~~~

## Mockup client psuedo source code using, easy interface with callbaks

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
