# DOH

Do DNS resolves over HTTPS for privacy, performance, and security. It also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Working*| Comment |
|-------------|----------|---------|---------|
| **A**
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: https://dns-nyc.aaflalo.me/dns-query <br> Server EU: https://dns.aaflalo.me/dns-query | :heavy_check_mark: <br> :heavy_multiplication_x:  | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Both servers check for DNSSEC and block advertising|
| [AdGuard](https://adguard.com/en/adguard-dns/overview.html)     | Default: https://dns.adguard.com/dns-query <br> Family protection: https://dns-family.adguard.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. 
|[Alibaba Public DNS](https://www.alidns.com/)| https://dns.alidns.com/dns-query | :heavy_check_mark:| [DoH/DoT/DNS Json API](https://www.alidns.com/faqs/#dns-safe), Best DoH/DoT server in China |
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))|
| [alekberg](https://alekberg.net) | Spain: https://dnses.alekberg.net/dns-query <br> Holland: https://dnsnl.alekberg.net/dns-query <br> Sweden: https://dnsse.alekberg.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| DoH Servers in Spain, Holland and Sweden. No logging, no filtering, DNSSEC support.|
| [armadillodns.net](https://www.armadillodns.net/) | https://doh.armadillodns.net/dns-query | :heavy_multiplication_x:|  No source IP logging. |
|[Association 42l](https://42l.fr) | https://doh.42l.fr/dns-query | :heavy_check_mark:| DNSSEC, not logging queries' content, uses [doh-proxy](https://github.com/jedisct1/rust-doh) and [edgedns](https://github.com/jedisct1/edgedns) for caching. Queries proxied randomly through [FFDN](https://www.ffdn.org/) members' open DNS resolvers (French ISPs committing for net neutrality).
| **B**
| blahdns.com | Finland: https://doh-fi.blahdns.com/dns-query <br> Japan: https://doh-jp.blahdns.com/dns-query <br> Germany: https://doh-de.blahdns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based on [Go implementation](https://github.com/m13253/dns-over-https), knot-resolver, Unbound with DNSSEC, No ECS, No logs, Adsblock
| [blockerDNS](https://blockerdns.com/) | https://example.doh.blockerdns.com/dns-query | :question: (:moneybag:)| DNS-based ad-blocking service; One-man operation; ZERO IP and DNS query logging for DoH and DoT. **Charges 99c per month** for https DOH service |
| [BraveDNS](https://www.bravedns.com/) | Malware and ad-blocking: https://free.bravedns.com/dns-query <br> Endpoint configuration with custom blocklists: https://bravedns.com/configure | :heavy_check_mark: | A stub resolver running in 200+ locations world-wide on Cloudfare. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logging. [github](https://github.com/celzero/brave-android-app#bravedns-resolver)
| **C**
| [captnemo.in](https://captnemo.in) | https://doh.captnemo.in/dns-query | :heavy_multiplication_x:| Runs [dnss](https://blitiri.com.ar/git/r/dnss/) with local unbound resolver running [DNSCrypt](https://captnemo.in/dnscrypt/) with DNSSEC support as the upstream. [Privacy Policy](https://captnemo.in/dns/privacy/). More details at <https://captnemo.in/doh/>. No logging or filtering. Runs in Bangalore, India | 
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: https://private.canadianshield.cira.ca/dns-query <br> Protected: https://protected.canadianshield.cira.ca/dns-query <br> Family: https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
| [Cisco Umbrella/OpenDNS](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query | :heavy_check_mark: <br><br> :heavy_check_mark:| DNSSEC, Anycast
| CleanBrowsing | https://doh.cleanbrowsing.org/doh/family-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br> also available via [Tor onion service](https://blog.cloudflare.com/welcome-hidden-resolver) <br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br> Block Malware: https://security.cloudflare-dns.com/dns-query <br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :question: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :question:| Supports both -04 and -13 content-types
| Comcast | https://doh.xfinity.com/dns-query | :heavy_multiplication_x:| Experimental, DNSSEC
| Commons Host | https://commons.host | :heavy_multiplication_x:| ~20 PoPs worldwide, Node.js/[playdoh](https://github.com/qoelet/playdoh) over [Knot Resolver](https://www.knot-resolver.cz). |
| [ContainerPI](https://dns.containerpi.com)| Unfiltered by Cloudflare:<br>https://dns.containerpi.com/dns-query <br>Filtered by CleanBrowsing, blocks adult content:<br>https://dns.containerpi.com/doh/family-filter/ <br>Filtered, blocks malicious domains only:<br>https://dns.containerpi.com/doh/secure-filter/ | :heavy_check_mark: <br> :heavy_multiplication_x: <br> :heavy_multiplication_x: | Based on [m13253/DNS-over-HTTPS](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled. Multiple nodes in `China Mainland(limited)`, `China Taiwan`, `Japan`, `South Korea`, `India`, `Germany`, `România`, `Russia`, `USA` and `Brazil`. |
| Cox | https://dohdot.coxlab.net/dns-query |:heavy_multiplication_x: | Experimental, No DNSSEC
| [CZ.NIC](https://www.nic.cz) | https://odvr.nic.cz/doh | :heavy_check_mark:| Experimental, using [Knot Resolver](https://www.knot-resolver.cz/)
| **D**
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
| dns.flatuslifir.is |  https://dns.flatuslifir.is/dns-query | :heavy_check_mark:| Public adblock server that supports DoT & DoH for fun and learning, no logging, supports DNSSEC,  qname-minimisation, ECS is not enabled. Located in Iceland, built on pihole, nginx, unbound, m13253/DNS-over-HTTPS |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query | :heavy_check_mark:| DNSSEC enabled |
| [dnsforge.de](https://dnsforge.de/) | https://dnsforge.de/dns-query |:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|
| [dnsHome.de](https://www.dnshome.de/doh-dot-public-resolver.php) |  https://dns.dnshome.de/dns-query | :heavy_check_mark:| DoH Server in Germany. No logging, No filtering, DNSSEC and own DNS Resolver |
| [DNSlify](https://www.dnslify.com) | https://doh.dnslify.com/dns-query | :heavy_check_mark:|  Anycast, No Logging, Own Recursion, Strict Privacy Policy.
| [doh.li](https://doh.li)| https://doh.li/dns-query | :heavy_check_mark:| Runs on [dns-over-https](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled, based in DigitalOcean London. DNSSEC and adblock not currently enabled. |
| **F**
| [FAELIX](https://faelix.net/) | https://rdns.faelix.net/ | :heavy_check_mark:| No logging, based on dnsdist-doh RC querying our powerdns-recursor resolvers, multiple nodes in UK and CH, [more info](https://faelix.net/ref/dns/#resolving-nameservers) |
| ffmuc.net | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| **G**
| Google      | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark:|Full RFC 8484 support
| **H**
| [Hostux.net](https://dns.hostux.net) |  Uncensored DNS: https://dns.hostux.net/dns-query <br> Adblocking DNS: https://dns.hostux.net/ads | :heavy_check_mark: <br> :heavy_check_mark: |DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
| [Hurricane Electric (he.net)](https://he.net)  | https://ordns.he.net/dns-query | :heavy_check_mark:| Also supports DoT and TLS 1.3, Does not support DNSSEC. Anycast servers. |
| **J**
| [jcdns.fun](https://jcdns.fun)| https://jcdns.fun/dns-query | :heavy_multiplication_x:| secure nginx, Non-Logged / Uncensored, hosted on Digital Ocean VPS by [jamesacampbell](https://github.com/jamesacampbell) AKA James Campbell.  |
| jitender| https://jit.ddns.net:3443/dns-query | :heavy_check_mark: | DoH server - India, Oracle Cloud, Hyderabad, India, Runs with nginx, high availability, load balanced by nginx with multiple backend DNS servers. Blocks ad, analytics, trackers blocking provides a clean browsing experience. @coolquasar |
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query| :heavy_check_mark: | No Censorship, No Logging, No ECS, support DNSSEC in Japan |
| **L**
| [LavaDNS](https://dns.lavate.ch/) | USA: https://us1.dns.lavate.ch/dns-query, Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in USA and Finland. No logging, no filtering, no ECS, DNSSEC support. |
| [lelux.fi](https://lelux.fi/resolver/) | https://resolver-eu.lelux.fi/dns-query | :heavy_multiplication_x: | DoH server in France. No logging, no filtering, DNSSEC support. |
| [LibreDNS](https://libredns.gr/) | https://doh.libredns.gr/dns-query | :heavy_check_mark: | no logging, TLS 1.3, No DNSSEC |
| **N**
| [nextdns.io](https://nextdns.io) | https://dns.nextdns.io/<config_id><br>[Create a config ID](https://my.nextdns.io/start) | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free! Quite a fine-granular dashboard, the same account can be used for multiple devices with prefixes to easier track activities on the dashboard!
| NekomimiRouter.com | https://dns.dns-over-https.com/dns-query | :heavy_check_mark: | Runs [Go implementation](https://github.com/m13253/dns-over-https). Does recursion itself with no upstream servers. Toy server may fail, please report if fails |
| **P**
| [pi-dns.com](https://pi-dns.com) | https://doh.pi-dns.com/dns-query <br> https://doh.centraleu.pi-dns.com/dns-query <br> https://doh.northeu.pi-dns.com/dns-query <br> https://doh.westus.pi-dns.com/dns-query <br> https://doh.eastus.pi-dns.com/dns-query <br> https://doh.eastau.pi-dns.com/dns-query <br> https://doh.eastas.pi-dns.com/dns-query | :heavy_check_mark: | A zero logging DNS with support for DNS-over-HTTPS (DoH) & DNS-over-TLS (DoT). Blocks ads, malware, trackers, viruses and telemetry. DNSSEC, TLS 1.3 |
| PowerDNS  | https://doh.powerdns.org | :heavy_check_mark: | Based on [dnsdist-doh](https://github.com/ahupowerdns/pdns/tree/dnsdist-doh) branch
| **Q**
| [Quad9](https://www.quad9.net/doh-quad9-dns-servers/)       |  Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query <br> Secured w/ECS Support: https://dns11.quad9.net/dns-query| :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| **R**
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | :heavy_check_mark: | East China Zone, Based on https://github.com/m13253/dns-over-https |
| **S**
| [Snopyta](https://snopyta.org/service/dns/) | https://fi.doh.dns.snopyta.org/dns-query | :heavy_check_mark: | Non-logging DoH Server in Finland |
| [SWITCH](https://www.switch.ch/security/info/public-dns/) | https://dns.switch.ch/dns-query | :heavy_check_mark: | DNSSEC validation protects from forged or manipulated DNS data from upstream servers, DNS Query Name Minimisation to improve privacy, [SWITCH DNS Firewall](https://www.switch.ch/dns-firewall/) blocks access to infected or malicious websites and redirects users to a landing page |
| **T**
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
| **W**
| [wugui.zone](https://wugui.zone/archives/48.sghtml) | https://dns.wugui.zone/dns-query <br>https://dns-asia.wugui.zone/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | DoH Server in Russia. No logging, No filtering |
| **@#$%**
| @chantra    | https://dns.dnsoverhttps.net/dns-query | :heavy_check_mark: | "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy) |
| @jedisct1  | https://doh.crypto.sx/dns-query | :heavy_check_mark: |a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| [ibksturm.synology.me](https://ibksturm.synology.me)| https://ibksturm.synology.me/dns-query | :heavy_check_mark: | doh-server (nginx - dnsproxy - unbound), DNSSEC / Non-Logged / Uncensored, OpenNIC and Root DNS-Zone Copy Hosted in Switzerland by ibksturm, aka Andreas Ziegler. |
|[@matthewgall - mydns.network](https://twitter.com/matthewgall) | https://adblock.mydns.network/dns-query (adblock, using PiHole) | :heavy_check_mark: | no logging, DNSSEC enforcing, DDoS protected (using Spectrum by Cloudflare), anycast)
| [@null31](https://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | :heavy_check_mark: | Brazilian server that runs Nginx, [Unbound](https://nlnetlabs.nl/projects/unbound/about/) with DNSSEC doing recursion with no upstream servers, QNAME minimization, TLS 1.3, DoT, uncensored, no logging, no ECS, hosted on Oracle Cloud VPS by [null31](https://github.com/null31). |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query <br> https://doh.seby.io:8443/dns-query | :heavy_multiplication_x: <br> :heavy_check_mark: | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), Unbound with DNSSEC, No ECS, and No logs|

*: Tested via `curl --doh-url <RESOLVER_URI> http://google.com`.

# Private DNS Server with DoH setup examples
| Base | Source | Comment |
|-------------|----------|---------|
| Docker | https://github.com/satishweb/docker-doh | Complete Docker stack using Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) and [Docker Flow Proxy](https://github.com/docker-flow/docker-flow-proxy)


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
|[dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy)|Frank Denis|dnscrypt-proxy 2 - A flexible DNS proxy, with support for encrypted DNS protocols.|
|[quart-doh](https://github.com/treussart/quart-doh)|Matthieu Treussart| HTTP/2 server who serves a DOH proxy written in Python, with [Quart](https://pgjones.gitlab.io/quart/index.html) Python web microframework.|
|[EasyDoH](https://github.com/ElevenPaths/EasyDoH)|ElevenPaths| a simple [add-on for Firefox](https://addons.mozilla.org/es/firefox/addon/easydoh/) that allows one to easily activate DNS over HTTPS and its working mode with just one click.|
|[dohjs](https://github.com/byu-imaal/dohjs) | [BYU IMAAL](https://imaal.byu.edu) | Client DoH JavaScript library for accessing DNS information from web applications. Can be tested at [dohjs.org](https://dohjs.org)
|[Technitium DNS Server](https://github.com/TechnitiumSoftware/DnsServer)|Technitium|A FOSS, cross-platform DNS Server written in C# that can consume as well as host DNS-over-HTTPS (DoH) and DNS-over-TLS (DoT) services.
|[kdig](https://gitlab.nic.cz/knot/knot-dns)|CZ.NIC|Utility that sends one or more DNS queries to a nameserver. Each query can have individual settings, or it can be specified globally via common-settings, which must precede query specification. This utility supports DoH.

# Other

[Script to parse DoH provider URLs from this wiki page](https://gist.github.com/kimbo/dd65d539970e3a28a10628f15398247b)