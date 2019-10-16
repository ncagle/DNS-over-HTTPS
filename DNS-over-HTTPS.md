# DOH

Do DNS resolves over HTTPS for privacy, performance and security. Also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Comment |
|-------------|----------|---------|
| [AdGuard](https://adguard.com/en/adguard-dns/overview.html)     | Default: https://dns.adguard.com/dns-query <br> Family protection: https://dns-family.adguard.com/dns-query <br> | Default provides ad blocking at DNS level, while Family protection adds adult site blocking. 
| Google      | https://dns.google/dns-query | Full RFC 8484 support
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br> also available via [Tor onion service](https://blog.cloudflare.com/welcome-hidden-resolver)| Supports both -04 and -13 content-types
| [Quad9](https://www.quad9.net/doh-quad9-dns-servers/)       | Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query <br> Secured w/ECS Support: https://dns11.quad9.net/dns-query| Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| Cisco Umbrella/OpenDNS | https://doh.opendns.com/dns-query | Experimental, No DNSSEC
| CleanBrowsing | https://doh.cleanbrowsing.org/doh/family-filter/ | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| [nextdns.io](https://nextdns.io) | https://dns.nextdns.io/<config_id><br>[Create a config ID](https://my.nextdns.io/start) | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet.
| @chantra    | https://dns.dnsoverhttps.net/dns-query | "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy) |
| @jedisct1  | https://doh.crypto.sx/dns-query | a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| PowerDNS  | https://doh.powerdns.org | Based on [dnsdist-doh](https://github.com/ahupowerdns/pdns/tree/dnsdist-doh) branch
| blahdns.com | Switzerland: https://doh-ch.blahdns.com/dns-query (IPv6 ONLY) <br> Japan: https://doh-jp.blahdns.com/dns-query <br> Germany: https://doh-de.blahdns.com/dns-query | Based on [Go implementation](https://github.com/m13253/dns-over-https), knot-resolver, Unbound with DNSSEC, No ECS, No logs, Adsblock
| NekomimiRouter.com | https://dns.dns-over-https.com/dns-query | Runs [Go implementation](https://github.com/m13253/dns-over-https). Does recursion itself with no upstream servers. Toy server may fail, please report if fails |
| SecureDNS.eu | https://doh.securedns.eu/dns-query | No Logging & DNSSEC |
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | East China Zone, Based on https://github.com/m13253/dns-over-https |
| ContainerPI | Unfiltered by CloudFlare:<br>https://dns.containerpi.com/dns-query <br>Filtered by CleanBrowsing, blocks adult content:<br>https://dns.containerpi.com/doh/family-filter/ <br>Filtered, blocks malicious domains only:<br>https://dns.containerpi.com/doh/secure-filter/ | Based on [m13253/DNS-over-HTTPS](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled. Multiple nodes in China Mainland, Japan and Germany. |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query https://doh.seby.io:8443/dns-query | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), Unbound with DNSSEC, No ECS and No logs
| Commons Host | https://commons.host | ~20 PoPs worldwide, Node.js/[playdoh](https://github.com/qoelet/playdoh) over [Knot Resolver](https://www.knot-resolver.cz). |
| [DnsWarden](https://dnswarden.com) | Adblocking DNS: https://doh.dnswarden.com/adblock <br> Uncensored DNS: https://doh.dnswarden.com/uncensored | No query/IP logging with DNSSEC enabled. <br>  Blocks ads and trackers in Adblocking DNS.<br> No filtering in Uncensored DNS.  |
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: https://dns-nyc.aaflalo.me/dns-query <br> Server EU: https://dns.aaflalo.me/dns-query | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Both servers check for DNSSEC and block advertising|
| [Foundation for Applied Privacy](https://appliedprivacy.net) | https://doh.appliedprivacy.net/query | No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://appliedprivacy.net/services/dns/ |
| [captnemo.in](https://captnemo.in) | https://doh.captnemo.in/dns-query | Runs [dnss](https://blitiri.com.ar/git/r/dnss/) with local unbound resolver running [DNSCrypt](https://captnemo.in/dnscrypt/) with DNSSEC support as the upstream. [Privacy Policy](https://captnemo.in/dns/privacy/). More details at <https://captnemo.in/doh/>. No logging or filtering. Runs in Bangalore, India | 
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query | No Logging, DNSSEC enabled |
| [FAELIX](https://faelix.net/) | https://rdns.faelix.net/ | No logging, based on dnsdist-doh RC querying our powerdns-recursor resolvers, multiple nodes in UK and CH, [more info](https://faelix.net/ref/dns/#resolving-nameservers) |
| [doh.li](https://doh.li)| https://doh.li/dns-query | Runs on [dns-over-https](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled, based in DigitalOcean London. DNSSEC and adblock not currently enabled. |
| [armadillodns.net](https://www.armadillodns.net/) | https://doh.armadillodns.net/dns-query | No source IP logging. |
| [NetWeaver](https://www.netweaver.uk/) | https://doh.netweaver.uk/dns-query | UK servers, no logging, DNSSEC enabled |
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query| No Censorship, No Logging, No ECS, support DNSSEC in Japan |
|[Association 42l](https://42l.fr) | https://doh.42l.fr/dns-query | DNSSEC, not logging queries' content, uses [doh-proxy](https://github.com/jedisct1/rust-doh) and [edgedns](https://github.com/jedisct1/edgedns) for caching. Queries proxied to the French ISP [FDN](https://www.fdn.fr/actions/dns/)'s open DNS resolver, commiting for net neutrality.
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))
|[@matthewgall - mydns.network](https://twitter.com/matthewgall) | https://adblock.mydns.network/dns-query (adblock, using PiHole) | no logging, DNSSEC enforcing, DDoS protected (using Spectrum by Cloudflare), anycast)
| [ibksturm.synology.me](https://ibksturm.synology.me)| https://ibksturm.synology.me/dns-query | doh-server (nginx - dnsproxy - unbound), DNSSEC / Non-Logged / Uncensored, OpenNIC and Root DNS-Zone Copy Hosted in Switzerland by ibksturm, aka Andreas Ziegler. |
| [jcdns.fun](https://jcdns.fun)| https://jcdns.fun/dns-query | secure nginx, Non-Logged / Uncensored, hosted on Digital Ocean VPS by [jamesacampbell](https://github.com/jamesacampbell) AKA James Campbell. |
| [@null31](http://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | Brazilian server that runs [dnsdist](https://dnsdist.org/), [Unbound](https://nlnetlabs.nl/projects/unbound/about/) with DNSSEC doing recursion with no upstream servers, QNAME minimization, TLS 1.3, DoT, uncensored, no logging, no ECS, hosted on Google Cloud VPS by [null31](https://github.com/null31). Toy server, may fail. |


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

Peter Lai's [doh-js-client](https://github.com/sc0Vu/doh-js-client) client-side implementation of DoH, can be used in nodejs backend.

Travis Burtrum's [jDnsProxy](https://github.com/moparisthebest/jDnsProxy) DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)

Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https), with server-side and client-side implementation, written in Golang.

Alberto Bertogli's [dnss](https://github.com/albertito/dnss), a daemon written in Go which act as a proxy (the most common use case), and as a server (in case you want end to end control).

Dima Krasner's [nss-tls](https://github.com/dimkr/nss-tls), a daemon that makes gethostbyname(), getaddrinfo(), etc' happen through DoH, without any change to applications, thus transparently migrating all applications that don't use their own resolver (like some browsers) from DNS to DoH.

Maxime Elomari's [dealdoh](https://github.com/noglitchyo/dealdoh), a middleware to proxy DoH requests to different DNS upstreams, written in PHP.

Frank Olbricht's [RouteDNS](https://github.com/folbricht/routedns), a flexible stub resolver, proxy, and router with support for DoH, DoT, and plain DNS written in Go.

Max Kostikov's [h2odoh](https://github.com/xm74/h2odoh), an implementation with H2O HTTP/2 server using embedded mruby.

Frank Denis' [Encrypted DNS Server](https://github.com/jedisct1/encrypted-dns-server), written in Rust, can serve DNSCrypt and DoH traffic simultaneously. A [Docker image](https://github.com/dnscrypt/dnscrypt-server-docker) including a recursive server is also available.

Matthieu Treussart' [quart-doh](https://github.com/treussart/quart-doh), written in Python, with [Quart](https://pgjones.gitlab.io/quart/index.html) Python web microframework. HTTP/2 server who serve a DOH proxy.

ElevenPaths's [EasyDoH](https://github.com/ElevenPaths/EasyDoH), a simple [addon for Firefox](https://addons.mozilla.org/es/firefox/addon/easydoh/) that allows to easily activate DNS over HTTPS and its working mode with just one click.