# DOH

Do DNS resolves over HTTPS for privacy, performance and security. Also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Comment |
|-------------|----------|---------|
| Google      | https://dns.google.com/experimental |
| Cloudflare  | https://cloudflare-dns.com/dns-query | Supports both -04 and -13 content-types
| Quad9       | Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query | Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| CleanBrowsing | https://doh.cleanbrowsing.org/doh/family-filter/ | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| @chantra    | https://dns.dnsoverhttps.net/dns-query | "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy) |
| @jedisct1  | https://doh.crypto.sx/dns-query | a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| PowerDNS  | https://doh.powerdns.org | Based on [dnsdist-doh](https://github.com/ahupowerdns/pdns/tree/dnsdist-doh) branch
| blahdns.com | Japan: https://doh-jp.blahdns.com/dns-query <br> Germany: https://doh-de.blahdns.com/dns-query | Run on [Go implementation](https://github.com/m13253/dns-over-https), knot-resolver with DNSSEC and ads block
| NekomimiRouter.com | https://dns.dns-over-https.com/dns-query | Runs [Go implementation](https://github.com/m13253/dns-over-https). Does recursion itself with no upstream servers. Toy server may fail, send email if fails |
| SecureDNS.eu | https://doh.securedns.eu/dns-query | No Logging & DNSSEC |
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | East China Zone, Based on https://github.com/m13253/dns-over-https |
| Commons Host | https://commons.host | ~20 PoPs worldwide, Node.js/[playdoh](https://github.com/qoelet/playdoh) over [Knot Resolver](https://www.knot-resolver.cz). |
| dnswarden.com | Server 1: https://doh1.dnswarden.com <br> Server 2: https://doh2.dnswarden.com | Runs on [dnsdist-doh](https://github.com/ahupowerdns/pdns/tree/dnsdist-doh) . No query logging with DNSSEC. <br> Server 2 enforces safe search and blocks adult content |
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: https://dns-gcp.aaflalo.me/dns-query <br> Server EU: https://dns.aaflalo.me/dns-query | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Both servers check for DNSSEC and block advertising|

# Supported in browsers and clients

|Name|Version|Comments|
|----|-------|----|
|Firefox|62| [temporary docs](https://daniel.haxx.se/trr) |
|[Bromite](https://www.bromite.org/)|67.0.3396.88|[How to enable DoH](https://github.com/bromite/bromite/wiki/Enabling-DNS-over-HTTPS)|
|curl| 7.62.0 | See [DOH-implementation](DOH-implementation) |
|[OkHttp](https://github.com/square/okhttp/tree/master/okhttp-dnsoverhttps)| 3.11 | See [Providers](https://github.com/square/okhttp/blob/master/okhttp-dnsoverhttps/src/test/java/okhttp3/dnsoverhttps/DohProviders.java) |
| [curl-doh](https://github.com/curl/doh) | n/a | basic stand-alone DoH client that uses curl |
| Chrome | 66 | https://bugs.chromium.org/p/chromium/issues/detail?id=799753 |

# DOH Tools

Facebook's [doh-proxy](https://facebookexperimental.github.io/doh-proxy/) and associated tools.

Daniel's [dns2doh](https://github.com/bagder/dns2doh) tool for generating DOH responses and questions.

Frank Denis' [doh-proxy](https://github.com/jedisct1/rust-doh) (server-side proxy) and [dnscrypt-proxy](https://github.com/jedisct1/dnscrypt-proxy) (client proxy).

Daniel Cid's [doh-php-client](https://github.com/dcid/doh-php-client) can be used to test and run DoH requests via PHP applications.

Travis Burtrum's [jDnsProxy](https://github.com/moparisthebest/jDnsProxy) DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)

Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https), with server-side and client-side implementation, written in Golang.

Alberto Bertogli's [dnss](https://github.com/albertito/dnss), a daemon written in Go which act as a proxy (the most common use case), and as a server (in case you want end to end control).

Dima Krasner's [nss-tls](https://github.com/dimkr/nss-tls), a daemon that makes gethostbyname(), getaddrinfo(), etc' happen through DoH, without any change to applications, thus transparently migrating all applications that don't use their own resolver (like some browsers) from DNS to DoH.