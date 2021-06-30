# WebSockets

For a long time people have expressed wishes and ideas about getting WebSockets support added to curl. Every year in the annual survey a large portion of users say they'd like it.

This is meant as a brain-storm area for writing down how WebSockets in curl could be made to work.

[Weston Schmidt's proposals](https://github.com/schmidtw/curl-websocket-proposal)

Ideas were bouncing on [the curl-library list in June 2021](https://curl.se/mail/lib-2021-06/).

## Not transfer-oriented

WebSockets is similar to "TCP over HTTP". It provides a bidirectional transport meant for "anything". As such, it doesn't fit the "normal" libcurl transfer paradigms very well. It is rather similar to doing `CONNECT_ONLY` + `curl_easy_send/recv.

## libcurl-only

Due to it being a transport for anything, it seems likely that websockets won't be exposed by the command line tool. Unless someone thinks of a good way to do it.

# API

- We probably want to support `ws://` and `wss://` URLs, and then have special handling of them to imply `CONNECT_ONLY`-style: do the WebSockets upgrade dance and then return.
- We probably need new functions for recv/send so that we can pass on extra flags for websockets use (like end of packet flag, compression, binary/text etc)

