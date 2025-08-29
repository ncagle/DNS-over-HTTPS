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
- requires MSVC for native Windows threading [[link]](https://github.com/aws/aws-lc/blob/6d2eb62ba375ebba7ab20ab277332f5bff9e13f0/crypto/thread_win.c#L194-L210)
- symbol hiding issues
- requires Windows 7 minimum with mingw-w64 [[link]](https://github.com/aws/aws-lc/blob/6d2eb62ba375ebba7ab20ab277332f5bff9e13f0/CMakeLists.txt#L510)
- supports standard build system (cmake)
- contributing: responsive, easy

## BoringSSL

This is a fork run by Google for Google.

- offers a OpenSSL 1.1 like API
- makes no releases
- features the "original" QUIC API
- supports ECH
- requires a C++ library
- requires MSVC for native Windows threading, and ASM support [[link]](https://github.com/curl/curl-for-win/blob/e7a1232f3478a85f1d8e57f75703421e2f958812/boringssl.patch) [[link]](https://boringssl.googlesource.com/boringssl/+/refs/tags/0.20250818.0/crypto/thread_win.cc#149)
- lacks option to disable debug info, reproducibility issues [[link]](https://boringssl.googlesource.com/boringssl/+/refs/tags/0.20250818.0/CMakeLists.txt#138)
- supports standard build systems (bazel, cmake)
- contributing: almost impossible, also requires CLA

## LibreSSL

This is a fork initially done by OpenBSD developers.

- offers a OpenSSL 1.1 like API
- lacks support for ECH [[link]](https://github.com/libressl/portable/issues/546)
- lacks support for TLSv1.3 session tickets [[link]](https://github.com/libressl/portable/issues/719) [[link]](https://github.com/curl/curl/issues/18031#issuecomment-3144406973)
- lacks support for server signatures signed with ED25519 [[link]](https://github.com/libressl/portable/issues/821) [[link]](https://github.com/curl/curl-for-win/discussions/78)
- lacks support for `SSL_set0_wbio()` function [[link]](https://github.com/libressl/portable/issues/838)
- lacks support for `SSLKEYLOGFILE` [[link]](https://marc.info/?l=libressl&m=158908819814107) [[link]](https://github.com/curl/curl/issues/18236) [[link]](https://github.com/curl/curl/issues/13672)
- lacks ASM support for arm64
- seems to not provide the proper error queue at all times [[link]](https://github.com/curl/curl/issues/18297)
- symbol hiding issues [[link]](https://github.com/libressl/portable/issues/957)
- supports standard build systems (autotools, cmake)
- contributing: responsive, easy

## OpenSSL

- offers a QUIC implementation (that underperforms)
- offers the "new" QUIC API
- lacks support for ECH [[link]](https://github.com/openssl/openssl/pull/22938)
- Windows vulnerability with configuration [[link]](https://github.com/openssl/openssl/issues/24528)
- performance problems in OpenSSL 3 [[link]](https://www.haproxy.com/blog/state-of-ssl-stacks) [[link]](https://www.memorysafety.org/blog/rustls-server-perf/)
- large footprint [[link]](https://github.com/curl/curl-for-win/commit/c90c3c1ea5b9ddeed8b0f87afe2aff6dee0adb35)
- uses non-standard build system
- contributing: complicated, requires [CLA](https://openssl-library.org/policies/cla/)

## QuicTLS

This is a fork run by Akamai and Microsoft with the expressed goal of
providing an OpenSSL version close to the original but with the original QUIC
API.

- features the "original" QUIC API
- releases lag behind OpenSSL [[link]](https://github.com/quictls/openssl/releases)

# QUIC

- 2018: BoringSSL introduced a QUIC API (known as the Original above)
- 2019: a PR for OpenSSL for the same API was offered 
- 2021: OpenSSL rejected the PR
- 2023: OpenSSL introduced their own QUIC implementation, we call it OpenSSL-QUIC
- 2025: OpenSSL released 3.4.1, which is the minimum version curl recommends for OpenSSL-QUIC
- 2025: OpenSSL released 3.5.0 introduced the "New" QUIC API so that other QUIC implementations can use OpenSSL

The OpenSSL-QUIC is **much** slower than the competition (ngtcp2 for example), uses **a lot** more memory and has quite an inefficient API. For these reasons, curl still considers the OpenSSL-QUIC backend *experimental*.

![HTTP_3 for scania,js(2)](https://github.com/user-attachments/assets/6b6bd518-8c06-456a-9776-a43f73796b7e)
