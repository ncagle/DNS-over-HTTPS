# OpenSSL fork situation

curl can be built with many different TLS libraries. The most common choice is OpenSSL, but over the past years, several forks have emerged, each with different goals, features, and trade-offs. Supporting these OpenSSL forks means having to deal with with differences in API stability, feature availability (ex. QUIC and ECH), as well as build environments.

curl supports the following OpenSSL variants:

<!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!---->
Fork | Maintained By | Description | QUIC API | ECH Support | Release Model
-- | -- | -- | -- | -- | --
OpenSSL | OpenSSL Project | The official, most widely used TLS library. | New | No | Yes, regular
BoringSSL | Google | A streamlined fork for Google's needs; not for general use. | Original | Yes | No releases
AWS-LC | Amazon | A fork of BoringSSL with stable releases and long-term support. | Original | Yes | Yes, regular
QuicTLS | Akamai/Microsoft | A minimal fork of OpenSSL focused on providing the original QUIC API. | Original | Yes | Lags OpenSSL
LibreSSL | OpenBSD Project | A security-focused fork aiming to modernize and simplify the codebase. | Original | No | Yes, regular
AmiSSL | AmiSSL Project | A fork for AmigaOS that maintains API compatibility with OpenSSL. | No | No | Yes, regular


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
- contributing: responsive, easy

## BoringSSL

This is a fork run by Google for Google.

- offers a OpenSSL 1.1 like API
- makes no releases
- features the "original" QUIC API
- supports ECH
- requires a C++ library
- requires MSVC compiler on Windows
- supports standard build systems (bazel, cmake)
- contributing: almost impossible

## LibreSSL

This is a fork initially done by OpenBSD developers.

- offers a OpenSSL 1.1 like API
- lacks support for ECH
- lacks support for TLSv1.3 session tickets
- lacks support for server signatures signed with ED25519
- lacks support for `SSL_set0_wbio()` function
- lacks support for `SSLKEYLOGFILE`
- seems to not provide the proper error queue at all times
- symbol hiding issues
- ASM support only for x86_64
- supports standard build systems (autotools, cmake)
- contributing: responsive, easy

## OpenSSL

- offers a QUIC implementation (that underperforms)
- offers the "new" QUIC API
- lacks support for ECH
- Windows vulnerability with configuration
- performance problems in OpenSSL 3
- large footprint
- uses non-standard build system
- contributing: complicated, requires CLA

## QuicTLS

This is a fork run by Akamai and Microsoft with the expressed goal of
providing an OpenSSL version close to the original but with the original QUIC
API.

- features the "original" QUIC API
- releases lag behind OpenSSL

# QUIC

- 2018: BoringSSL introduced a QUIC API (known as the Original above)
- 2019: a PR for OpenSSL for the same API was offered 
- 2021: OpenSSL rejected the PR
- 2023: OpenSSL introduced their own QUIC implementation, we call it OpenSSL-QUIC
- 2025: OpenSSL released 3.4.1, which is the minimum version curl recommends for OpenSSL-QUIC
- 2025: OpenSSL released 3.5.0 introduced the "New" QUIC API so that other QUIC implementations can use OpenSSL

The OpenSSL-QUIC is **much** slower than the competition (ngtcp2 for example), uses **a lot** more memory and has quite an inefficient API. For these reasons, curl still considers the OpenSSL-QUIC backend *experimental*.

![HTTP_3 for scania,js(2)](https://github.com/user-attachments/assets/6b6bd518-8c06-456a-9776-a43f73796b7e)
