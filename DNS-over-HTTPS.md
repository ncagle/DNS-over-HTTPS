# DOH

Do DNS resolves over HTTPS for privacy, performance and security. Also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

This is work in progress: https://tools.ietf.org/html/draft-ietf-doh-dns-over-https-11

# Publicly available servers

| Who runs it | Base URL | POST/GET | Comment |
|-------------|----------|----------|---------|
| Google      | https://dns.google.com/experimental | both |
| Cloudflare  | https://dns.cloudflare.com/.well-known/dns-query | POST |
| CleanBrowsing | https://doh.cleanbrowsing.org/doh/family-filter/ | both? | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| @chantra    | https://dns.dnsoverhttps.net/dns-query | both? | "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy) |
| @jedisct1  | https://doh.crypto.sx/dns-query | both | a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| SecureDNS.eu | https://doh.securedns.eu/dns-query | both? |

# Supported in browsers and clients

|Name|Version|Comments|
|----|-------|----|
|Firefox|62| [temporary docs](https://daniel.haxx.se/trr) |
|curl| [PR](https://github.com/curl/curl/pull/2668) | See [DOH-implementation](DOH-implementation) |

# DOH Tools

Facebook's [doh-proxy](https://facebookexperimental.github.io/doh-proxy/) and associated tools.

Daniel's [dns2doh](https://github.com/bagder/dns2doh) tool for generating DOH responses and questions and [curl-doh](https://github.com/curl/doh) a small doh-client written on top of libcurl.

Frank Denis' [doh-proxy](https://github.com/jedisct1/rust-doh) (server-side proxy) and [dnscrypt-proxy](https://github.com/jedisct1/dnscrypt-proxy) (client proxy).

Daniel Cid's [doh-php-client](https://github.com/dcid/doh-php-client) can be used to test and run DoH requests via PHP applications.

Travis Burtrum's [jDnsProxy](https://github.com/moparisthebest/jDnsProxy) DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)

Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https), with server-side and client-side implementation, written in Golang.