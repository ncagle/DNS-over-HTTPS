# DoH - DNS over HTTPS

DoH queries resolve over HTTPS for privacy, performance, and security. DoH also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Working*| Comment |
|-------------|----------|---------|---------|
| **A**
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: https://dns-nyc.aaflalo.me/dns-query | :heavy_check_mark: | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Checks for DNSSEC and block advertising |
| abel.waringer-atg.de | https://abel.waringer-atg.de/dns-query | :heavy_check_mark:| 
| [Absolight](https://www.absolight.fr/) | https://res-acst3.absolight.net/dns-query | :heavy_check_mark:| 
| [AdGuard](https://adguard.com/en/adguard-dns/overview.html)     | Default: https://dns.adguard.com/dns-query <br> Family protection: https://dns-family.adguard.com/dns-query <br> Uncensored: https://unfiltered.adguard-dns.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: <br> :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. DNSSEC enabled and TLS 1.3 | 
| [AhaDNS](https://ahadns.com) | Netherland : https://doh.nl.ahadns.net/dns-query <br> Los Angeles : https://doh.la.ahadns.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | A zero-logging DNS with support for DNS-over-HTTPS (DoH) & DNS-over-TLS (DoT). Blocks ads, malware, trackers, viruses, and telemetry. DNSSEC, TLS 1.3, Open Source. Uses OISD list |
|[AhaDNS Blitz](https://ahadns.com/blitz/)| Uncensored : https://blitz.ahadns.com <br> OISD filter : https://blitz.ahadns.com/1:1 <br> OISD & Energized Porn filter : https://blitz.ahadns.com/1:1.12 | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| [Customizable](https://blitz-setup.ahadns.com/) globally distributed DoH-only server with no logging |
| [alekberg](https://alekberg.net) | Holland: https://dnsnl.alekberg.net/dns-query <br> Sweden: https://dnsse.alekberg.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| DoH Servers in Spain, Holland and Sweden. No logging, no filtering, DNSSEC support.|
|[Alibaba Public DNS](https://www.alidns.com/)| https://dns.alidns.com/dns-query | :heavy_check_mark:| [DoH/DoT/DNS Json API](https://www.alidns.com/faqs/#dns-safe), Best DoH/DoT server in China |
|[Alica](https://www.alica.idv.tw/service/dns) | https://atelier.alica.idv.tw/dns-query | :heavy_check_mark: | Adblocking, non-logging, based in Taiwan 
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))|
|[Artikel10](https://dns.artikel10.org/) | https://dns.artikel10.org/dns-query | :heavy_check_mark: | Non-logging service based in Germany
| [Aviontex keweonDNS](https://aviontex.de/) | https://dns.keweon.center/dns-query | :heavy_check_mark: | 
| [Awan.ftp.sh](https://awan.ftp.sh/) | Ads and gambling blocking : https://awan.ftp.sh/dns-query <br> Ads, gambling, drug, tobacco block : https://awan.ftp.sh/no-vice <br> Porn, ads, gambling, drug, tobacco block : https://awan.ftp.sh/noporn-cl <br> Unblocked : https://awan.ftp.sh/unblocked | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Japan
| **B**
| [Bancuh](https://blog.bancuh.com/adblock-dns/) | Singapore : https://sg-dns1.bancuh.com/dns-query <br> France : https://fr-dns1.bancuh.com/dns-query <br> Tokyo : https://jp-dns1.bancuh.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Adblocking, porn blocking, log available for originating IP
| [BebasDNS](https://github.com/bebasid/bebasdns) | Singapore : https://dns.bebasid.com/dns-query | :heavy_check_mark: | DNS-based ad-blocking service
| [Belnet](https://dns.belnet.be/) | https://dns.belnet.be/dns-query | :heavy_check_mark: | IP, response code, protocol, and response time are logged for performance & statistic purposes. Hosted in Belgium by the Belgian National Research and Education Network.
| Bitdefender | https://dns.bitdefender.net/dns-query | :heavy_check_mark: |
| [Blahdns](https://blahdns.com/) | Switzerland : https://doh-ch.blahdns.com/dns-query <br> Singapore : https://doh-sg.blahdns.com/dns-query <br> Finland: https://doh-fi.blahdns.com/dns-query <br> Japan: https://doh-jp.blahdns.com/dns-query <br> Germany: https://doh-de.blahdns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based on [Go implementation](https://github.com/m13253/dns-over-https), HAProxy + Dnsdist + Knot-resolver with DNSSEC, No ECS, No logs, Adblock
| [Blokada DNS](https://community.blokada.org/t/the-benefits-of-blokada-dns/6646) | https://dns.blokada.org/dns-query | :heavy_check_mark: | No logging. 
| [Brahma World](https://dns.brahma.world/home.html) | https://dns.brahma.world/dns-query | :heavy_check_mark: | No logging • Blocks Ads + Trackers + Malware + Phishing domains, DNSSEC ready • QNAME Minimization • No EDNS Client-Subnet
| [Bortzmeyer](https://www.bortzmeyer.org/doh-bortzmeyer-fr-policy.html) | https://doh.bortzmeyer.fr | :heavy_check_mark: | French-based, non-logging. 
| [Bunny](https://bunny.net/) | https://doh1.b-cdn.net/dns-query | :heavy_check_mark: | 
| **C**
| Chaos System | https://chaos-system.de/dns-query | :heavy_check_mark: | Adblocking 
| Charter | California: https://doh-01.spectrum.com/dns-query <br> Texas: https://doh-02.spectrum.com/dns-query |:heavy_check_mark:| Trial - Testing multiple platforms
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: https://private.canadianshield.cira.ca/dns-query <br> Protected: https://protected.canadianshield.cira.ca/dns-query <br> Family: https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
| [Cisco Umbrella (OpenDNS)](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query | :heavy_check_mark: <br><br> :heavy_check_mark:| DNSSEC, Anycast
| [CleanBrowsing](https://cleanbrowsing.org/help/docs/dnsoverhttps/) | https://doh.cleanbrowsing.org/doh/family-filter/ <br><br> Filter that allows some mixed-content sites: https://doh.cleanbrowsing.org/doh/adult-filter/ <br><br> Malware blocking only: https://doh.cleanbrowsing.org/doh/security-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br><br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br><br> Block Malware: https://security.cloudflare-dns.com/dns-query <br><br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br><br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports both -04 and -13 content-types
| [CloudVeil](https://www.cloudveil.org/) | Canada : https://ca.doh.cloudveil.org/dns-query <br> US : https://us.doh.cloudveil.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Block adult and gambling sites. 
| Comcast | https://doh.xfinity.com/dns-query | :heavy_check_mark:| DNSSEC Validation, [DNS Privacy Policy](https://www.xfinity.com/privacy/policy/dns) |
| [Computer Incident Response Center Luxembourg](https://circl.lu/) | https://dns.circl.lu/dns-query | :heavy_check_mark:| 
| [Comss](https://www.comss.ru/page.php?id=7315) | https://dns.comss.one/dns-query | :heavy_check_mark: | Block ads, tracker, phishing and malware
| [ControlD](https://controld.com/) | Unfiltered : https://freedns.controld.com/p0 <br> Block Malware : https://freedns.controld.com/p1 <br> Block Malware + Ads : https://freedns.controld.com/p2 <br> Block Malware + Ads + Social : https://freedns.controld.com/p3 | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | ControlD is a fully customizable anycast DNS service that allows you to not only block annoyances like malware, tracking, ads, IoT telemetry, and more, but also unblock over 180 services through a network of proxies in over 100 cities.
| Cryptroute | https://dotdns.cryptroute.com/dns-query | :heavy_check_mark:| Adblocking
| [CZ.NIC](https://www.nic.cz/odvr/) | https://odvr.nic.cz/dns-query | :heavy_check_mark:| Runs on [Knot Resolver](https://www.knot-resolver.cz/) (`doh2`), supports DNSSEC, provided by `.cz` TLD operator
| **D**
| [Datahata.by](https://doh.datahata.by/) | https://doh.datahata.by/dns-query | :heavy_check_mark: |
| [Decloudus](https://decloudus.com/) |  https://dns.decloudus.com/dns-query | :heavy_check_mark: | Based in Germany.
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
| Disconnect.app | https://doh.disconnect.app/dns-query | :heavy_check_mark: | 
| [dns.digitalsize.net](https://dns.digitalsize.net/) | https://dns.digitalsize.net/dns-query | :heavy_check_mark: | A public, non-tracking, non-filtering DNS resolver with DNSSEC enabled and hosted in Germany |
| dns.flatuslifir.is |  https://dns.flatuslifir.is/dns-query | :heavy_check_mark:| Public adblock server that supports DoT & DoH for fun and learning, no logging, supports DNSSEC, qname-minimization, ECS is not enabled. Located in Iceland, built on pihole, nginx, unbound, m13253/DNS-over-HTTPS |
| [dnslow.me](https://dnslow.me/) | https://dnslow.me/dns-query | :heavy_check_mark: | Ad & threat blocking, short time logging for debug
| [DNSPod](https://www.dnspod.com/Products/Public.DNS) | https://dns.pub/dns-query | :heavy_check_mark: | Operated by Tencent Cloud
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query | :heavy_check_mark:| DNSSEC enabled |
| [dnscrypt.ca](https://dnscrypt.ca/) | https://dns1.dnscrypt.ca:453/dns-query | :heavy_check_mark:| Canadian, uncensored, no-logs, encrypted, and DNSSEC
| [dnscrypt.uk](https://dnscrypt.uk/) | Digital Ocean : https://doh.dnscrypt.uk/dns-query <br> Vultr : https://v.dnscrypt.uk/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | UK-based
| [DNS For Family](https://dnsforfamily.com/#DNS_Servers_DNS_Over_HTTPS) | https://dns-doh.dnsforfamily.com/dns-query | :heavy_check_mark: | Filter websites for family use, and enforces safe search in Google, YouTube, Bing, DuckDuckGo and Yandex. DNSSEC-ready, non-logging
| [dnsforge.de](https://dnsforge.de/) | https://dnsforge.de/dns-query |:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|
| [dnsHome.de](https://www.dnshome.de/doh-dot-public-resolver.php) |  https://dns.dnshome.de/dns-query | :heavy_check_mark:| DoH Server in Germany. No logging, No filtering, DNSSEC and own DNS Resolver |
| [doh.li](https://doh.li)| https://doh.li/dns-query | :heavy_check_mark:| Runs on [dns-over-https](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled, based in DigitalOcean London. DNSSEC and adblock are not currently enabled. |
| dnsenc.com | https://dnsenc.com/dns-query | :heavy_check_mark:|
| [dnswarden](https://dnswarden.com)| Adblock - <br> https://dns.dnswarden.com/adblock <br><br> Uncensored -<br> https://dns.dnswarden.com/uncensored <br><br> AdultFilter - <br>  https://dns.dnswarden.com/adultfilter | <br>:heavy_check_mark:<br><br><br>:heavy_check_mark:<br><br><br>:heavy_check_mark:| A zero logging DNS with support for DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) & Dnscrypt. Supports DNSSEC, TLS 1.3, QNAME minimization and does own Recursion. EDNS Client Subnet is disabled.<br> Provides 4 different types of filtering options.<br> Adblock - Blocks ads, trackers, viruses, and telemetry.<br> Adultfilter - Blocks adult content, enforces safe search, and includes all the features from adblock. <br> Uncensored - Unrestricted access/no filtering.<br>[Custom Filter](https://dnswarden.com/customfilter.html) where you can choose your own filter lists! <br>For more information look [here](https://github.com/bhanupratapys/dnswarden) or [here](https://dnswarden.com). |
| Dyn1.de | https://dns.dyn1.de/dns-query | :heavy_check_mark: | Adblocking
| **E**
| [e-utp.net](https://fido.e-utp.net/display/EUTPNET/Recursive+DNS) | https://dnscache.e-utp.net/dns-query | :heavy_check_mark: | IPv6 only
| [Easyhandshake](https://easyhandshake.com/) | https://easyhandshake.com:8053/dns-query | :heavy_check_mark: | Also resolve Handshake domains
| [Enhanced DNS and Defense for Industry](https://eddi.net/) | https://dns.eddi.net/dns-query | :heavy_check_mark: |
| [Edgy DNS](https://edgy.network/dns) | https://edgy-dns.com/dns-query | :heavy_check_mark: | Adblocking
| [ETH-Services](https://www.eth-services.de/) | https://opennic1.eth-services.de:853/ | :heavy_check_mark: | Run by Germany hosting company
| **F**
| [FAELIX](https://faelix.net/) | https://rdns.faelix.net/ | :heavy_check_mark:| No logging, based on dnsdist-doh RC querying our powerdns-recursor resolvers, multiple nodes in UK and CH, [more info](https://faelix.net/ref/dns/#resolving-nameservers) |
| [ffmuc.net](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
| [floDNS](https://www.flodns.com/get-started/) | https://ns1.flodns.net/dns-query | :heavy_check_mark: | All queries are logged for statistical analysis by [TalkDNS](https://www.talkdns.com/)
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| [Froth.zone](https://dns.froth.zone/resolver) | https://dns.froth.zone/dns-query | :heavy_check_mark: | OpenNIC
| Fuchur | https://fuchur.pentament.de/dns-query | :heavy_check_mark: |
| [FutaDNS](https://site.futa.gg/) | https://doh.futa.gg/dns-query | :heavy_check_mark: | Based in Taiwan, query logged for 24 hours.
| **G**
| [Google](https://developers.google.com/speed/public-dns/docs/doh) | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query <br> https://8888.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Full RFC 8484 support, EDNS, no filtering.
| [Gustavus Adolphus College](https://gustavus.edu/) | https://cluster-0.gac.edu/dns-query <br> https://cluster-1.gac.edu/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| 
| **H**
| [HDNS](https://docs.namebase.io/guides-1/resolving-handshake-1/hdns.io) | https://query.hdns.io/dns-query | :heavy_check_mark: | Also resolve Handshake domains
| [Hinet](https://hinet.net/) | https://dns.hinet.net/dns-query | :heavy_check_mark: | Run by Taiwanese ISP
| [hitian.me](https://hitian.me/) | https://hitian.me/dns-query | :heavy_check_mark: | Hosted in Singapore
| [Hostux.net](https://dns.hostux.net) |  Uncensored DNS: https://dns.hostux.net/dns-query <br> Adblocking DNS: https://dns.hostux.net/ads | :heavy_check_mark: <br> :heavy_check_mark: |DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
| [Hshh.org](https://www.hshh.org/) | https://ns2.hshh.org/dns-query | :heavy_check_mark: | 
| [Hurricane Electric (he.net)](https://he.net)  | https://ordns.he.net/dns-query | :heavy_check_mark:| Also supports DoT and TLS 1.3, Does NOT support DNSSEC. Anycast servers. |
| **I**
| [i-Evolve](https://www.i-evolve.com/) | https://ns1.i-evolve.net/dns-query | :heavy_check_mark: |
| [i2pd](https://opennic.i2pd.xyz/) | https://opennic.i2pd.xyz/dns-query | :heavy_check_mark: | OpenNIC resolver
| [Institut national de recherche en sciences et technologies du numérique](https://www.inria.fr/fr) | https://qlf-doh.inria.fr/dns-query | :heavy_check_mark: |
| [Institute of Operating Systems and Computer Networks](https://wiki.ibr.cs.tu-bs.de/en/services) | https://doh.ibr.cs.tu-bs.de/dns-query | :heavy_check_mark: |
| [Inter-University Computation Center](https://www.iucc.ac.il/en/) | https://doh.iucc.ac.il/dns-query | :heavy_check_mark: |
| [Internet Initiative Japan](https://public.dns.iij.jp/) | https://public.dns.iij.jp/dns-query | :heavy_check_mark: | Planned to run until March 2024 
| [Infotek](http://infotek.net.id/dns/) | https://doh.infotek.net.id:3443/dns-query | :heavy_check_mark: | Compliant with Indonesia censorship
| [In-Berlin](https://www.in-berlin.de/) | https://dns1.in-berlin.de/dns-query | :heavy_check_mark: |
| [IPv6DNS](https://www.ipv6dns.com/index) | https://dns.ipv6dns.com/dns-query | :heavy_check_mark: |
| [iQDNS](https://iqdns.xyz/all.html) | Anycast https://a.vvvglass.com/iq <br> CDN https://a.vvvglass.com/cdn  | :heavy_check_mark: <br> :heavy_check_mark: | Based in China
| Irre.li | https://irre.li/dns-query | :heavy_check_mark: | Adblocking
| **J**
| [Jabber Germany](https://jabber-germany.de/) | https://jabber-germany.de/dns-query | :heavy_check_mark: | Part of OpenNIC project
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query | :heavy_check_mark: | No Censorship, No Logging, No ECS, support DNSSEC in Japan |
| **K**
| [Kawa.tf](https://servers.opennicproject.org/edit.php?srv=ns2.fr.dns.opennic.glue) | https://dns.kawa.tf/dns-query | :heavy_check_mark: | Hosted in Strasbourg, France
| [kescherDNS](https://dns.kescher.at/) | https://dns.kescher.at/dns-query | :heavy_check_mark: | Non-logging, hosted in Vienna and Düsseldorf
| **L**
| [La Contre-Voie](https://lacontrevoie.fr/en/services/doh/) | https://doh.lacontrevoie.fr/dns-query | :heavy_check_mark: | Supports DNSSEC and IPv6, not logging queries' content, uses [unbound](https://github.com/NLnetLabs/unbound/). Commits for net neutrality, hosted in France.
| [Lars Lehmn](https://larsl.net/services/dns/) | https://dns.lars-lehmann.net/dns-query | :heavy_check_mark: | Based in Germany, [privacy policy](https://larsl.net/privacy-policy/)
| [Lastentarvike](https://lastentarvike.fi) | https://lastentarvike.fi/dns-query | :heavy_check_mark: |
| [LavaDNS](https://dns.lavate.ch/) | Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in Finland. No logging, no filtering, no ECS, DNSSEC support. |
| [LibreDNS](https://libredns.gr/) | https://doh.libredns.gr/dns-query | :heavy_check_mark: | no logging, TLS 1.3, No DNSSEC |
| [Limo Telu](https://www.limotelu.org/) | https://sby-doh.limotelu.org/dns-query | :heavy_check_mark: | No logging, DNSSEC, query minimization and prefetch, based in Surabaya, Indonesia
| **M**
| [Masters of Cloud](https://www.masters-of-cloud.de/) | https://masters-of-cloud.de/dns-query | :heavy_check_mark: | 
| [MegaNerd](https://meganerd.nl/encrypted-dns-server) | https://chewbacca.meganerd.nl/dns-query | :heavy_check_mark: | No logging, no filtering, DNSSEC, based in the Netherlands
| [Melian](https://dns.melalandia.tk/) | https://dns.melalandia.tk/dns-query | :heavy_check_mark: |
| [Micronets.in](https://doh.micronets.in/) | https://doh.micronets.in/dns-query | :heavy_check_mark: | Logged to publicly available API.
| [Monzoon](https://www.monzoon.net/) | https://zrh1-ns01.monzoon.net/dns-query | :heavy_check_mark: |
| [Morbitzer](https://morbitzer.de/) | https://www.morbitzer.de/dns-query | :heavy_check_mark: | 
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | Non-blocking https://doh.mullvad.net/dns-query <br> Adblocking https://adblock.doh.mullvad.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Public DoH server in AU, US, DE, GB, SG, and SE with QNAME minimization, audited by [Assured](https://www.assured.se/wp-content/uploads/2021/03/Assured_Mullvad_DoH_server_audit_report.pdf)
| **N**
| [ndom91](https://ndo.dev/posts/doh) | https://dns.ndo.dev/dns-query | :heavy_check_mark: | Non-logging, adblocking, ECS disabled, QNAME minimization, recursive resolver through Unbound with DNSSEC.
| [Nebula.tru.io](https://nebula.tru.io) | Adblocking https://nebula.tru.io/dns-query <br> Adblocking & porn blocking https://nebula.tru.io/porn | :heavy_check_mark: <br> :heavy_check_mark: | Server in Japan
| [Neubsi.at](https://cube.neubsi.at/) | https://cube.neubsi.at/dns-query | :heavy_check_mark:|
| [NextDNS](https://nextdns.io) | https://dns.nextdns.io | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free with non-filtering afterward until the end of the month. Granular dashboard, Each account can create multiple configurations, which can be used for multiple devices with prefixes to track activities on the dashboard. [Create a config ID](https://my.nextdns.io/start) 
| [NIC.LV](https://doh.lv/) | https://doh.lv/dns-query <br> https://doh.nic.lv/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run by .lv TLD registry 
| [Njalla](https://dns.njal.la/) | https://dns.njal.la/dns-query | :heavy_check_mark: | Non logging, based in Sweden
| [No Ad DNS](https://noaddns.com/) | https://resolver.noaddns.com/dns-query | :heavy_check_mark: | Adblocking
| [Novg.net](https://novg.net/) | https://dns.novg.net/dns-query | :heavy_check_mark: |
| Nsc.torgues.net | https://nsc.torgues.net/dns-query | :heavy_check_mark: | Adblocking
| **O**
| [Open BLD DNS](https://lab.sys-adm.in/) | Adapted : https://a-bld.sys-adm.in/dns-query <br> Balanced : https://bld.sys-adm.in/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Block ads and trackers
| [opennameserver.org](https://opennameserver.org/) | Baden-Baden https://ns1.opennameserver.org/dns-query <br> Frankfurt https://ns2.opennameserver.org/dns-query <br> Berlin https://ns3.opennameserver.org/dns-query <br> Sandefjord https://ns1.opennameserver.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | DNSSEC, non-logging, OpenNIC 
| **P**
| [PaesaDNS](https://milgradesec.github.io/paesadns/) | https://dns.paesa.es/dns-query | :heavy_check_mark: | Adblocking
| [Plan9-dns](https://jlongua.github.io/plan9-dns/) | New Jersey : https://kronos.plan9-dns.com/dns-query <br> Florida : https://pluton.plan9-dns.com/dns-query <br> Mexico : https://helios.plan9-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted on Vultr
| Pope.cnblw.me | https://pope.cnblw.me/dns-query | :heavy_check_mark: |
| [PureDNS](https://puredns.org/) | https://puredns.org/dns-query | :heavy_check_mark: | Hosted in Indonesia and Singapore
| **Q**
| [Quad9](https://www.quad9.net/doh-quad9-dns-servers/) | Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query <br> Secured w/ECS Support: https://dns11.quad9.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| [Quadrant](https://quadrantsec.com/quadrants_public_dns_resolver_with_tls_https_support/) | https://doh.qis.io/dns-query | :heavy_check_mark: | No filtering, no logging 
| [Qihoo 360](https://360.cn) | https://doh.360.cn/dns-query | :heavy_check_mark: | Based in China
| **R**
| [R0cket](https://resolver.r0cket.net/) | https://resolver.r0cket.net/dns-query | :heavy_check_mark: | Adblocking, queries are logged and monitored when there's abuse
| [Restena](https://www.restena.lu/en/service/public-dns-resolver) | https://kaitain.restena.lu/dns-query | :heavy_check_mark: | Based in Luxembourg, DNSSEC, minimal logging for technical functions
| [RethinkDNS](https://www.rethinkdns.com/) | Non-filtering: https://basic.rethinkdns.com/dns-query | :heavy_check_mark: | [An open-source stub resolver](https://github.com/serverless-dns/serverless-dns) running in 200+ locations world-wide on Cloudfare's network. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logs. [code](https://github.com/celzero/rethink-app). [Configure custom blocklists](https://rethinkdns.com/configure)
| [Rezhajul](https://doh.rezhajul.io/) | https://doh.rezhajul.io/dns-query | :heavy_check_mark: | No Logging, DNSSEC enabled, 1.7M+ hosts filtered (ads, tracker, malware, spam, coinminer and phising).
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | :heavy_check_mark: | East China Zone, Based on https://github.com/m13253/dns-over-https |
| Ryan Palmer | https://dns1.ryan-palmer.com/dns-query | :heavy_check_mark: | Hosted in UK, Non-logging, non-filtering, DNSSEC
| **S**
| [Safe Surfer](https://safesurfer.io/) | https://doh.safesurfer.io/dns-query | :heavy_check_mark: | Filter porn sites, enforce safe search
| [SFR](http://sfr.fr/) | https://pates.services.sfr.fr.casepp.sfr.fr | :heavy_check_mark: |
| Slinkyman.net | https://dns.slinkyman.net/dns-query | :heavy_check_mark: | Adblocking
| [Softcom](https://www.softcom.net/) | https://clientdns3.softcom.net/dns-query | :heavy_check_mark: |
| [Spacedns](https://spacedns.org/) | https://spacedns.org/dns-query | :heavy_check_mark: | Hosted in Poland, adblocking, non-logging.
| [Studentenstadt Freimann](https://www.stusta.de/en/) | https://muli.stusta.mhn.de/dns-query <br> https://esel.stusta.mhn.de/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |
| [SWITCH](https://www.switch.ch/security/info/public-dns/) | https://dns.switch.ch/dns-query | :heavy_check_mark: | DNSSEC validation protects from forged or manipulated DNS data from upstream servers, DNS Query Name Minimisation to improve privacy, [SWITCH DNS Firewall](https://www.switch.ch/dns-firewall/) blocks access to infected or malicious websites and redirects users to a landing page |
| [Syshero](https://syshero.org/) | https://doh.syshero.org/dns-query | :heavy_check_mark: | 
| **T**
| [Telekom Deutschland](https://telekomhilft.telekom.de/t5/Offentliche-Tests-Umfragen/Telekom-hilft-Labor-Testet-mit-uns-DNS-over-HTTPS/m-p/5008054) | https://dns.telekom.de/dns-query | :heavy_check_mark: | 
| [TeraDNS](https://teradns.org/dns-over-https/) | UK : https://uk.teradns.org/dns-query <br> Germany : https://de.teradns.org/dns-query <br> New York : https://ny.teradns.org/dns-query <br> Texas : https://tx.teradns.org/dns-query <br> Singapore : https://sg.teradns.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Adblocking, query logged for 24 hours to detect amplification attack.
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
| Timmes.nl | https://timmes.nl/dns-query | :heavy_check_mark: | Adblocking
| Tls-data.de | https://dns.tls-data.de/dns-query | :heavy_check_mark: |
| [Tuxis](https://www.tuxis.nl/public-doh-dot-dns64-nat64-service/) | https://nat64.tuxis.nl/ | :heavy_check_mark: | IPv6 only, queries logged for abuse tracking, removed after three days
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
| therifleman.name | https://dns.therifleman.name/dns-query | :heavy_check_mark: | Based in Mumbai, IP not logged, query logged for 24 hours
| t53.de | https://dns.t53.de/dns-query | :heavy_check_mark: |
| **U**
| [Universität Bremen](https://www.uni-bremen.de/zfn/weitere-it-dienste/domain-name-service-dns) | https://ines.zfn.uni-bremen.de/dns-query | :heavy_check_mark: | 
| [Università di Padova](https://www.unipd.it/) | https://galileo.math.unipd.it/dns-query | :heavy_check_mark: | 
| [UncensoredDNS](https://blog.uncensoreddns.org/dns-servers/) | Anycast : https://anycast.uncensoreddns.org/dns-query <br> https://anycast.censurfridns.dk/dns-query <br> Denmark : https://unicast.uncensoreddns.org/dns-query <br> https://unicast.censurfridns.dk/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Non-logging, anycast on Denmark and US
| [Usable Privacy](https://docs.usableprivacy.com/updns/) | https://adfree.usableprivacy.net/dns-query | :heavy_check_mark: | Public non-logging DNS server with advertising and tracker filtering, use AdAway and Peter Lowe's list |
| **V**
| [Vasili Sviridov](https://vasi.li/) | https://tor.vasi.li/dns-query | :heavy_check_mark: | 
| **W**
| [WeDNS](https://wevpn.com/wedns) | Non-blocking : https://dns.wevpn.com/dns-query <br> Ad and malware blocking : https://dns-weblock.wevpn.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run on WeVPN infrastructure, freely available for public use.
| [Wewitro](https://wewitro.de/) | https://doh.wewitro.net/dns-query | :heavy_check_mark: | 
| [Woozeno](https://iris.woozeno.eu/) | https://iris.woozeno.eu/dns-query | :heavy_check_mark: | 
| **X**
| [xcom.pro](https://doh.xcom.pro/) | https://doh.xcom.pro/dns-query | :heavy_check_mark: |
| **Y**
| [Yarp](https://yarp.lefolgoc.net/) | https://yarp.lefolgoc.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted in France, no logging.
| [Yoooo](https://wyx.cloud/) | https://wyx.cloud/dns-query | :heavy_check_mark: | 
| **Z**
| Zougloub.eu | https://zougloub.eu/dns-query | :heavy_check_mark: |
| **Others**
| [7vpn](https://dns.7vpn.com/) | https://dns.7vpn.com/dns-query | :heavy_check_mark: |
| @jedisct1  | https://doh.crypto.sx/dns-query | :heavy_check_mark: |a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
| [@null31](https://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | :heavy_check_mark: | Based in Brazil / doh-server (nginx - dnsdist - unbound) / dot-server (dnsdist - unbound) / DNSSEC / QNAME minimization / Uncensored / no logging, no ECS, hosted on Oracle Cloud VPS by [null31](https://gitlab.com/null31/DoT-DoH-public-config). |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query <br> https://doh.seby.io:8443/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), Unbound with DNSSEC, No ECS, and No logs|

*: Tested via `curl --doh-url <RESOLVER_URI> http://google.com`.

# Private DNS Server with DoH setup examples
| Base | Source | Comment |
|-------------|----------|---------|
| Docker | https://github.com/satishweb/docker-doh | Complete Docker stack using Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) and [Docker Flow Proxy](https://github.com/docker-flow/docker-flow-proxy)
| Docker | https://github.com/coolquasar/dnsproxy | Complete DoH, DoT, and DoQ stack in docker based on Adguard home dnsproxy project. Could host DoH, DoT and DoQ quickly in a cloud server, and run respective clients in local Docker env. It has been tested in Raspberry PI as well

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
|[bulldohzer](https://github.com/commonshost/bulldohzer) | Commonshost | Benchmark DoH and Do53 servers
|[coredns](https://github.com/coredns/coredns)|Cloudflare| CoreDNS is a DNS server/forwarder, written in Go from the Cloud Native Computing Foundation. |
|[dealdoh](https://github.com/noglitchyo/dealdoh)|Maxime Elomari| a middleware to proxy DoH requests to different DNS upstreams, written in PHP.|
|[dns-over-https](https://github.com/m13253/dns-over-https)|Star Brilliant| server-side and client-side implementation, written in Golang|
|[dns2doh](https://github.com/bagder/dns2doh)|Daniel| tool for generating DOH responses and questions.|
|[dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy)|Frank Denis|dnscrypt-proxy 2 - A flexible DNS proxy, with support for encrypted DNS protocols.|
|[dnsdist](https://dnsdist.org/)|PowerDNS|supports doh, see <https://dnsdist.org/guides/dns-over-https.html>|
|[dnss](https://github.com/albertito/dnss)|Alberto Bertogli|daemon written in Go which acts as a proxy (the most common use case), and as a server (in case you want end-to-end control).|
|[doh-cf-workers](https://github.com/tina-hello/doh-cf-workers)|tina-hello|A single JS file to forward DoH to DoH on Cloudflare Workers
|[doh-gcf](https://github.com/tina-hello/doh-gcf)|tina-hello|A single C# file to forward DoH to DoH/Do53 on Google Cloud Function 
|[doh-js-client](https://github.com/sc0Vu/doh-js-client)|Peter Lai| client-side implementation of DoH, can be used in nodejs backend.|
|[doh-php-client](https://github.com/dcid/doh-php-client)|Daniel Cid| can be used to test and run DoH requests via PHP applications.|
|[doh-proxy](https://facebookexperimental.github.io/doh-proxy/)|Facebook| tools for DoH|
|[doh-proxy](https://github.com/jedisct1/rust-doh)|Frank Denis| server-side proxy in rust|
|[DOHD](https://github.com/dyne/dohd)|[Dyne.org](https://dyne.org)|Very fast and lightweight daemon written in C functioning as a simple proxy for DNS queries over HTTPS using the HTTP/2 protocol and WolfSSL.
|[dohjs](https://github.com/byu-imaal/dohjs) | [BYU IMAAL](https://imaal.byu.edu) | Client DoH JavaScript library for accessing DNS information from web applications. Can be tested at [dohjs.org](https://dohjs.org)
|[DoH](https://github.com/NotMikeDEV/DoH)|NotMikeDEV|A single PHP file to add DoH forwarder on any PHP-capable server
|[EasyDoH](https://github.com/ElevenPaths/EasyDoH)|ElevenPaths| a simple [add-on for Firefox](https://addons.mozilla.org/es/firefox/addon/easydoh/) that allows one to easily activate DNS over HTTPS and its working mode with just one click.|
|[Encrypted DNS Server](https://github.com/jedisct1/encrypted-dns-server)|Frank Denis|can serve DNSCrypt and DoH traffic simultaneously,  written in Rust.|
|[Encrypted-DNS](https://github.com/Siujoeng-Lau/Encrypted-DNS)|Siujoeng Lau| DNS-over-HTTPS forwarder written in Python|
|[godnsbench](https://github.com/ameshkov/godnsbench) | Andrey Meshkov | Benchmark DoH, Do53, DoT and DoQ servers.
|[h2odoh](https://github.com/xm74/h2odoh)|Max Kostikov| an implementation with H2O HTTP/2 server using embedded mruby.|
|[jDnsProxy](https://github.com/moparisthebest/jDnsProxy)|Travis Burtrum| DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)|
|[kdig](https://gitlab.nic.cz/knot/knot-dns)|CZ.NIC|Utility that sends one or more DNS queries to a nameserver. Each query can have individual settings, or it can be specified globally via common settings, which must precede query specification. This utility supports DoH.
|[nss-tls](https://github.com/dimkr/nss-tls)|Dima Krasner| a daemon that makes gethostbyname(), getaddrinfo(), etc. happen through DoH, without any change to applications, thus transparently migrating all applications that don't use their own resolver (like some browsers) from DNS to DoH.|
|[quart-doh](https://github.com/treussart/quart-doh)|Matthieu Treussart| HTTP/2 server who serves a DOH proxy written in Python, with [Quart](https://pgjones.gitlab.io/quart/index.html) Python web microframework.|
|[RouteDNS](https://github.com/folbricht/routedns)|Frank Olbricht| a flexible stub resolver, proxy, and router with support for DoH, DoT, and plain DNS written in Go.|
|[serverless-dns](https://github.com/serverless-dns/serverless-dns)|[RethinkDNS](https://rethinkdns.com/)| Host your own RethinkDNS instance on Cloudflare Worker, support customizable filter from URL parameter
|[Technitium DNS Server](https://github.com/TechnitiumSoftware/DnsServer)|Technitium|A FOSS, cross-platform DNS Server written in C# that can consume as well as host DNS-over-HTTPS (DoH) and DNS-over-TLS (DoT) services.
# Other

[Script to parse DoH provider URLs from this wiki page](https://gist.github.com/kimbo/dd65d539970e3a28a10628f15398247b)