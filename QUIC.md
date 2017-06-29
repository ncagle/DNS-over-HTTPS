Thoughts on how to support QUIC in (lib)curl.

QUIC is a new transport protocol in the making.

The [drafts](https://quicwg.github.io/)

## HTTPS://

Due to QUIC being done over UDP, and yet is here to serve HTTPS:// URLs, servers upgrade to QUIC from TCP-based HTTP versions with the `Alt-Svc:` header.

The client makes a request using TCP(+TLS) and gets a response back that says that it can also use QUIC on a certain hostname and port.

A browser can then try to open a new QUIC connection *in parallel* to the existing connection so that it can transparently switch to the new QUIC connection - if that works (or otherwise stick to the TCP based one). (lib)curl might not conveniently be able to provide the same parallel style of operation but should switching to the Alt-Svc server if asked to, or to directly use QUIC on a specific port if told so by the right options.

## Alt-Svc cache

The Alt-Svc information is probably best stored in a new "Alt-Svc cache" in libcurl. It gives information about a hostname + port number combo, with a specific life time for each entry also set in the response headers. There's also an ALTSVC HTTP/2 header providing basically the same info.

I think starting out with an in-memory cache only is fine, but we should probably consider being able to write it to disk as well to allow for example repeated curl tool invokes to better take advantage of it.

Alt-Svc can be used for more than QUIC, and there are good reasons to support the other things too. I think starting out with a QUIC focus is fine, but aim for later expansion.

## QUIC libraries

As for HTTP/2 we intend to rely on an existing third party library for all the transport layer bits and pieces of QUIC. Here are some libraries to consider to use for this:

 - [ngtcp2](https://github.com/ngtcp2/ngtcp2)
 - [MozQuic](https://github.com/mcmanus/gecko/tree/quic/netwerk/protocol/http/quic/mozquic)
 - [quicly](https://github.com/h2o/quicly)

We start out using one dedicated library and add QUIC support with that, to get a focused effort. If someone at a later time wants spend time and effort to add support for another/more libraries, we consider that at that point in time.

HTTP QUIC (hq) is not exactly HTTP/2 frames, but will be different enough to warrant a completely separate take. It will make the QUIC support to be completely independently implemented from the HTTP/2 support. libcurl should be possible to build with only h1 + hq support, as well as h1 + h2 + hq.