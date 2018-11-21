Thoughts on how to support HTTP/3 and QUIC in (lib)curl is [here](QUIC-implementation).

QUIC is a new transport protocol in the making, and HTTP/3 is the adaptation of HTTP to run over this transport.

The [drafts](https://quicwg.github.io/) from IETF Working Group.

More on Alt-svc extension (http://httpwg.org/http-extensions/alt-svc.html)

ALPN RFC:  https://tools.ietf.org/html/rfc7301

## HTTPS://

Due to QUIC being done over UDP, and yet is here to serve HTTPS:// URLs, servers upgrade to QUIC from TCP-based HTTP versions with the `Alt-Svc:` header.

The client makes a HTTP/1 or HTTP/2 request and gets a response back that says that it can also use HTTP/3 on a certain hostname and port.

A browser can then try to open a new QUIC connection *in parallel* to the existing connection so that it can transparently switch to the new QUIC connection - if that works (or otherwise stick to the TCP based one). (lib)curl might not initially provide the same parallel style of operation but should support switching to the Alt-Svc server if asked to, or to directly use QUIC on a specific port if told so by the right options.

## QUIC libraries

As for HTTP/2 we intend to rely on an existing third party library for all the transport layer bits and pieces of QUIC. Here are some libraries to consider to use for this:

 - [ngtcp2](https://github.com/ngtcp2/ngtcp2)  (C-library)
 - [MozQuic](https://github.com/mcmanus/mozquic) (C++ library)
 - [quicly](https://github.com/h2o/quicly) (C-library)
 - [LiteSpeed QUIC client](https://github.com/litespeedtech/lsquic-client) (C-library)

We start out using one dedicated library and add QUIC support with that, to get a focused effort. If someone at a later time wants spend time and effort to add support for another/more libraries, we consider that at that point in time.

HTTP/3 (h3) is different enough to warrant a completely separate take från HTTP/2. It will make the HTTP/3 support to be completely independently implemented from the HTTP/2 support. libcurl should be possible to build with only h1 + h3 support, as well as h1 + h2 + h3.

## TLS 1.3
QUIC uses TLS 1.3 and pretty much requires that the library interfaces a TLS library directly, which makes it tied to a specific TLS library harder than what is ideal for curl.

## ngtcp2 library
This library uses OpenSSL.  It implements QUIC protocol only, that is, we need to build HTTP 1.1 or HTTP/2 on the top of it. The bridging code needs to map HTTP/2 streams, messages and frames into ngtcp2's streams. 
Client code needs to defines callbacks, as a list of function pointers. For example, in C++ it looks like this:

  auto callbacks = ngtcp2_conn_callbacks{
      send_client_initial,
      send_client_cleartext,
      nullptr,
      nullptr,
      recv_stream0_data,
      config.quiet ? nullptr : debug::send_pkt,
      config.quiet ? nullptr : debug::send_frame,
      config.quiet ? nullptr : debug::recv_pkt,
      config.quiet ? nullptr : debug::recv_frame,
      handshake_completed,
      config.quiet ? nullptr : debug::recv_version_negotiation,
      do_hs_encrypt,
      do_hs_decrypt,
      do_encrypt,
      do_decrypt,
      recv_stream_data,
      acked_stream_data_offset,
      stream_close,
      config.quiet ? nullptr : debug::recv_stateless_reset,
      recv_server_stateless_retry,
      extend_max_stream_id,
  };

Then, instantiates and fill in ngtcp2 settings, for example:

  ngtcp2_settings settings;
  settings.max_stream_data = 256_k;
  settings.max_data = 1_k;
  settings.max_stream_id = 0;
  settings.idle_timeout = config.timeout;
  settings.omit_connection_id = 0;
  settings.max_packet_size = NGTCP2_MAX_PKT_SIZE;

and then call this API:

  rv = ngtcp2_conn_client_new(&conn_, conn_id, version, &callbacks, &settings, this);

This API creates a new connection.  Last parameter is "void *user_data", so we can pass "this" pointer.
When necessary, callbacks will be invoked, for example for TLS handshake.  We need to perform handshake ourselves,
using OpenSSL, for example.


Licence:  MIT licence.

## LiteSpeed library
This library uses BoringSSL.  BoringSSL is a fork from OpenSSL. Although, most of headers are similar, there are some differences between them (for example, BoringSSL implements cryptographic channel ID-s, etc.). So, it is not possible to drop in OpenSSL instead of BoringSSL and expect that everything will compiler, link and work. So this needs to be investigated.

Licence:  MIT licence.

Additional references:
- The author of this blog explains QUIC in more accessible way:
https://ma.ttias.be/googles-quic-protocol-moving-web-tcp-udp/
- QUIC: Design Document and Specification Rationale
https://docs.google.com/document/d/1RNHkx_VvKWyWg6Lr8SZ-saqsQx7rFV-ev2jRFUoVD34/edit?usp=sharing

## MozQuic
This is the library that will be used for QUIC in the Firefox browser. The library is implemented in C++, which limits portability much more than curl and really any other 3rd party library curl uses do.