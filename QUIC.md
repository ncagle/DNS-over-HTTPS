Thoughts on how to support QUIC in (lib)curl.

QUIC is a new transport protocol in the making.

The [drafts](https://quicwg.github.io/)

## HTTPS://

Due to QUIC being done over UDP, and yet is here to serve HTTPS:// URLs, servers upgrade to QUIC from TCP-based HTTP versions with the `Alt-Svc:` header.

The client makes a request using TCP(+TLS) and gets a response back that says that it can also use QUIC on a certain hostname and port.

A browser can then try to open a new QUIC connection *in parallel* to the existing connection so that it can transparently switch to the new QUIC connection - if that works (or otherwise stick to the TCP based one). (lib)curl might not conveniently be able to provide the same parallel style of operation but should switching to the Alt-Svc server if asked to, or to directly use QUIC on a specific port if told so by the right options.

## Alt-Svc cache

The Alt-Svc information is probably best stored in a new "Alt-Svc cache" in libcurl. It gives information about a hostname + port number combo, with a specific life time for each entry also set in the response headers.

## QUIC libraries

As for HTTP/2 we intend to rely on an existing third party library for all the transport layer bits and pieces of QUIC. Here are some libraries to consider to use for this:

 - [ngtcp2](https://github.com/ngtcp2/ngtcp2)
 - [MozQuic](https://github.com/mcmanus/gecko/tree/quic/netwerk/protocol/http/quic/mozquic)
 - [quicly](https://github.com/h2o/quicly)
