# DOH

Do DNS resolves over HTTPS for privacy, performance, and security. It also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Comment |
|-------------|----------|---------|
| [AdGuard](https://adguard.com/en/adguard-dns/overview.html)     | Default: https://dns.adguard.com/dns-query <br> Family protection: https://dns-family.adguard.com/dns-query <br> | Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. 
| Google      | https://dns.google/dns-query | Full RFC 8484 support
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br> also available via [Tor onion service](https://blog.cloudflare.com/welcome-hidden-resolver)| Supports both -04 and -13 content-types
| [Quad9](https://www.quad9.net/doh-quad9-dns-servers/)       | Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query <br> Secured w/ECS Support: https://dns11.quad9.net/dns-query| Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| Cisco Umbrella/OpenDNS | https://doh.opendns.com/dns-query | Experimental, No DNSSEC
| CleanBrowsing | https://doh.cleanbrowsing.org/doh/family-filter/ | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| Comcast | https://doh.xfinity.com/dns-query | Experimental, DNSSEC
| Cox | https://dohdot.coxlab.net/dns-query | Experimental, No DNSSEC
| [nextdns.io](https://nextdns.io) | https://dns.nextdns.io/<config_id><br>[Create a config ID](https://my.nextdns.io/start) | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet.
| @chantra    | https://dns.dnsoverhttps.net/dns-query | "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy) |
| @jedisct1  | https://doh.crypto.sx/dns-query | a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| PowerDNS  | https://doh.powerdns.org | Based on [dnsdist-doh](https://github.com/ahupowerdns/pdns/tree/dnsdist-doh) branch
| blahdns.com | Finland: https://doh-fi.blahdns.com/dns-query <br> Japan: https://doh-jp.blahdns.com/dns-query <br> Germany: https://doh-de.blahdns.com/dns-query | Based on [Go implementation](https://github.com/m13253/dns-over-https), knot-resolver, Unbound with DNSSEC, No ECS, No logs, Adsblock
| ffmuc.net | https://doh.ffmuc.net/dns-query | DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
| NekomimiRouter.com | https://dns.dns-over-https.com/dns-query | Runs [Go implementation](https://github.com/m13253/dns-over-https). Does recursion itself with no upstream servers. Toy server may fail, please report if fails |
| SecureDNS.eu | https://doh.securedns.eu/dns-query | No Logging & DNSSEC |
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | East China Zone, Based on https://github.com/m13253/dns-over-https |
| ContainerPI | Unfiltered by Cloudflare:<br>https://dns.containerpi.com/dns-query <br>Filtered by CleanBrowsing, blocks adult content:<br>https://dns.containerpi.com/doh/family-filter/ <br>Filtered, blocks malicious domains only:<br>https://dns.containerpi.com/doh/secure-filter/ | Based on [m13253/DNS-over-HTTPS](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled. Multiple nodes in `China Mainland(limited)`, `China Taiwan`, `Japan`, `South Korea`, `India`, `Germany`, `România`, `Russia`, `USA` and `Brazil`. |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query https://doh.seby.io:8443/dns-query | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), Unbound with DNSSEC, No ECS, and No logs
| Commons Host | https://commons.host | ~20 PoPs worldwide, Node.js/[playdoh](https://github.com/qoelet/playdoh) over [Knot Resolver](https://www.knot-resolver.cz). |
| [DnsWarden](https://dnswarden.com) | Adblocking DNS: https://doh.dnswarden.com/adblock <br> Uncensored DNS: https://doh.dnswarden.com/uncensored <br> Adult-filter DNS: https://doh.dnswarden.com/adult-filter | No query/IP logging with DNSSEC enabled. <br>  Blocks ads and trackers in Adblocking DNS.<br> No filtering in Uncensored DNS. <br> Blocks adult content, ads, trackers and also enforces force safe search for search engines and youtube in Adult-filter DNS. |
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: https://dns-nyc.aaflalo.me/dns-query <br> Server EU: https://dns.aaflalo.me/dns-query | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Both servers check for DNSSEC and block advertising|
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| [captnemo.in](https://captnemo.in) | https://doh.captnemo.in/dns-query | Runs [dnss](https://blitiri.com.ar/git/r/dnss/) with local unbound resolver running [DNSCrypt](https://captnemo.in/dnscrypt/) with DNSSEC support as the upstream. [Privacy Policy](https://captnemo.in/dns/privacy/). More details at <https://captnemo.in/doh/>. No logging or filtering. Runs in Bangalore, India | 
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query | DNSSEC enabled |
| [FAELIX](https://faelix.net/) | https://rdns.faelix.net/ | No logging, based on dnsdist-doh RC querying our powerdns-recursor resolvers, multiple nodes in UK and CH, [more info](https://faelix.net/ref/dns/#resolving-nameservers) |
| [doh.li](https://doh.li)| https://doh.li/dns-query | Runs on [dns-over-https](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled, based in DigitalOcean London. DNSSEC and adblock not currently enabled. |
| [armadillodns.net](https://www.armadillodns.net/) | https://doh.armadillodns.net/dns-query | No source IP logging. |
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query| No Censorship, No Logging, No ECS, support DNSSEC in Japan |
|[Association 42l](https://42l.fr) | https://doh.42l.fr/dns-query | DNSSEC, not logging queries' content, uses [doh-proxy](https://github.com/jedisct1/rust-doh) and [edgedns](https://github.com/jedisct1/edgedns) for caching. Queries proxied randomly through [FFDN](https://www.ffdn.org/) members' open DNS resolvers (French ISPs committing for net neutrality).
| [Hostux.net](https://dns.hostux.net) | Uncensored DNS: https://dns.hostux.net/dns-query <br> Adblocking DNS: https://dns.hostux.net/ads | DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))
|[@matthewgall - mydns.network](https://twitter.com/matthewgall) | https://adblock.mydns.network/dns-query (adblock, using PiHole) | no logging, DNSSEC enforcing, DDoS protected (using Spectrum by Cloudflare), anycast)
| [ibksturm.synology.me](https://ibksturm.synology.me)| https://ibksturm.synology.me/dns-query | doh-server (nginx - dnsproxy - unbound), DNSSEC / Non-Logged / Uncensored, OpenNIC and Root DNS-Zone Copy Hosted in Switzerland by ibksturm, aka Andreas Ziegler. |
| [jcdns.fun](https://jcdns.fun)| https://jcdns.fun/dns-query | secure nginx, Non-Logged / Uncensored, hosted on Digital Ocean VPS by [jamesacampbell](https://github.com/jamesacampbell) AKA James Campbell. |
| [@null31](http://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | Brazilian server that runs [dnsdist](https://dnsdist.org/), [Unbound](https://nlnetlabs.nl/projects/unbound/about/) with DNSSEC doing recursion with no upstream servers, QNAME minimization, TLS 1.3, DoT, uncensored, no logging, no ECS, hosted on Google Cloud VPS by [null31](https://github.com/null31). Toy server -- may fail. |
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
| [blockerDNS](https://blockerdns.com/) | https://example.doh.blockerdns.com/dns-query | DNS-based ad-blocking service; One-man operation; ZERO IP and DNS query logging for DoH and DoT. **Charges 99c per month** for https DOH service |
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/) | https://dns.digitale-gesellschaft.ch/dns-query | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
| [LibreDNS](https://libredns.gr/) | https://doh.libredns.gr/dns-query | no logging, TLS 1.3, No DNSSEC |
| [pi-dns.com](https://pi-dns.com) | https://doh.centraleu.pi-dns.com/dns-query <br> https://doh.northeu.pi-dns.com/dns-query <br> https://doh.westus.pi-dns.com/dns-query <br> https://doh.eastus.pi-dns.com/dns-query | Public ad-blocking DNS service built on Pi-hole that support DNS over HTTPS (DoH) and DNS over TLS (DoT). |


# Supported in browsers and clients

|Name|Version|Comments|
|----|-------|----|
|Firefox|62| [Firefox DNS-over-HTTPS](https://support.mozilla.org/en-US/kb/firefox-dns-over-https) |
|[Bromite](https://www.bromite.org/)|67.0.3396.88|[How to enable DoH](https://github.com/bromite/bromite/wiki/Enabling-DNS-over-HTTPS)|
|curl| 7.62.0 | See [DOH-implementation](DOH-implementation) |
|[OkHttp](https://github.com/square/okhttp/tree/master/okhttp-dnsoverhttps)| 3.11 | See [Providers](https://github.com/square/okhttp/blob/master/okhttp-dnsoverhttps/src/test/java/okhttp3/dnsoverhttps/DohProviders.java) |
| [curl-doh](https://github.com/curl/doh) | n/a | basic stand-alone DoH client that uses curl |
| Chrome | 66 | https://bugs.chromium.org/p/chromium/issues/detail?id=799753 |

# DOH Tools

|Name|Author/Organization|Comments|
|----|-------|----|
|[coredns](https://github.com/coredns/coredns)|Cloudflare| CoreDNS is a DNS server/forwarder, written in Go from the Cloud Native Computing Foundation. |
|[doh-proxy](https://facebookexperimental.github.io/doh-proxy/)|Facebook| tools for DoH|
|[dns2doh](https://github.com/bagder/dns2doh)|Daniel| tool for generating DOH responses and questions.|
|[doh-proxy](https://github.com/jedisct1/rust-doh)|Frank Denis| server-side proxy in rust|
|[doh-php-client](https://github.com/dcid/doh-php-client)|Daniel Cid| can be used to test and run DoH requests via PHP applications.|
|[doh-js-client](https://github.com/sc0Vu/doh-js-client)|Peter Lai| client-side implementation of DoH, can be used in nodejs backend.|
|[jDnsProxy](https://github.com/moparisthebest/jDnsProxy)|Travis Burtrum| DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)|
|[dns-over-https](https://github.com/m13253/dns-over-https)|Star Brilliant| server-side and client-side implementation, written in Golang|
|[dnsdist](https://dnsdist.org/)|PowerDNS|supports doh, see <https://dnsdist.org/guides/dns-over-https.html>|
|[dnss](https://github.com/albertito/dnss)|Alberto Bertogli|daemon written in Go which acts as a proxy (the most common use case), and as a server (in case you want end-to-end control).|
|[nss-tls](https://github.com/dimkr/nss-tls)|Dima Krasner| a daemon that makes gethostbyname(), getaddrinfo(), etc. happen through DoH, without any change to applications, thus transparently migrating all applications that don't use their own resolver (like some browsers) from DNS to DoH.|
|[dealdoh](https://github.com/noglitchyo/dealdoh)|Maxime Elomari| a middleware to proxy DoH requests to different DNS upstreams, written in PHP.|
|[Encrypted-DNS](https://github.com/Siujoeng-Lau/Encrypted-DNS)|Siujoeng Lau| DNS-over-HTTPS forwarder written in Python|
|[RouteDNS](https://github.com/folbricht/routedns)|Frank Olbricht| a flexible stub resolver, proxy, and router with support for DoH, DoT, and plain DNS written in Go.|
|[h2odoh](https://github.com/xm74/h2odoh)|Max Kostikov| an implementation with H2O HTTP/2 server using embedded mruby.|
|[Encrypted DNS Server](https://github.com/jedisct1/encrypted-dns-server)|Frank Denis|can serve DNSCrypt and DoH traffic simultaneously,  written in Rust.|
|[quart-doh](https://github.com/treussart/quart-doh)|Matthieu Treussart| HTTP/2 server who serves a DOH proxy written in Python, with [Quart](https://pgjones.gitlab.io/quart/index.html) Python web microframework.|
|[EasyDoH](https://github.com/ElevenPaths/EasyDoH)|ElevenPaths| a simple [add-on for Firefox](https://addons.mozilla.org/es/firefox/addon/easydoh/) that allows one to easily activate DNS over HTTPS and its working mode with just one click.|
|[dohjs](https://github.com/byu-imaal/dohjs) | [BYU IMAAL](https://imaal.byu.edu) | Client DoH JavaScript library for accessing DNS information from web applications. Can be tested at [dohjs.org](https://dohjs.org)

# Other

[Script to parse DoH provider URLs from this wiki page](https://gist.github.com/kimbo/dd65d539970e3a28a10628f15398247b)