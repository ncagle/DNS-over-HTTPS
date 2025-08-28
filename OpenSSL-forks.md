# OpenSSL fork situation

curl supports the following OpenSSL variants

- AmiSSL
- AWS-LC
- BoringSSL
- LibreSSL
- OpenSSL
- QuicTLS

## AmiSSL

This is a fork done for users on AmigaOS. From an API point of view, this
looks like vanilla OpenSSL.

## AWS-LC

This is a BoringSSL fork done by Amazon. It provides the same API BoringSSL
does.

- offers a OpenSSL 1.1 like API
- makes releases
- features the "original" QUIC API
- supports ECH
- requires a C++ library
- requires MSVC compiler on Windows
- symbol hiding issues
- requires Windows 7 minimum
- supports standard build system (cmake)

## BoringSSL

This is a fork run by Google for Google.

- offers a OpenSSL 1.1 like API
- makes no releases
- features the "original" QUIC API
- supports ECH
- requires a C++ library
- requires MSVC compiler on Windows
- supports standard build system (cmake)

## LibreSSL

This is a fork initially done by OpenBSD developers.

- offers a OpenSSL 1.1 like API
- lacks support for ECH
- lacks support for TLSv1.3 session tickets
- lacks support for server signatures signed with ED25519
- lacks support for `SSL_set0_wbio()` function
- lacks support for SSLKEYLOGFILE
- seems to not provide the proper error queue at all times
- symbol hiding issues
- ASM support only for x86_64
- supports standard build systems (autotools and cmake)

## OpenSSL

- offers a QUIC implementation (that underperforms)
- offers the "new" QUIC API
- lacks support for ECH
- Windows vulnerability with configuration
- performance problems in OpenSSL 3
- large footprint
- uses non-standard build system

## QuicTLS

This is a fork run by Akamai and Microsoft with the expressed goal of
providing an OpenSSL version close to the original but with the original QUIC
API.

- features the "original" QUIC API
- releases lag behind OpenSSL
