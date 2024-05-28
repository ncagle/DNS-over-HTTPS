# DoH - DNS over HTTPS

DoH queries resolve over HTTPS for privacy, performance, and security. DoH also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Working*| Comment |
|-------------|----------|---------|---------|
| **A**
|[ABD](https://abd.ong/)|https://adguard.abd.ong/dns-query|:heavy_check_mark:|Adblocking
|[Abraservice.xyz](https://abraservice.xyz/)|https://doh.abraservice.xyz/dns-query|:heavy_check_mark:|
|[AdFilter](https://adfilter.net/)|Perth: https://per.adfilter.net/dns-query<br>Sydney: https://syd.adfilter.net/dns-query<br>Adelaide: https://adl.adfilter.net/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking, aggregated statistics kept for 30 days
|Adfreedns|https://adfreedns.top/dns-query|:heavy_check_mark:|Adblocking
| [AdGuard](https://adguard-dns.io/en/public-dns.html)     | Default: https://dns.adguard-dns.com/dns-query <br> Family protection: https://family.adguard-dns.com/dns-query <br> Uncensored: https://unfiltered.adguard-dns.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: <br> :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. DNSSEC enabled and TLS 1.3 | 
|[AhaDNS Blitz](https://ahadns.com/blitz/)| Uncensored : https://blitz.ahadns.com <br> OISD filter : https://blitz.ahadns.com/1:1 | :heavy_check_mark: <br> :heavy_check_mark:| [Customizable](https://blitz-setup.ahadns.com/) globally distributed DoH-only server with no logging |
| [AhaDNS](https://ahadns.com) | Netherland:<br> https://doh.nl.ahadns.net/dns-query | :heavy_check_mark: | Deprecated in favor of AhaDNS Blitz |
|alleesph|https://alleesph.online/dns-query|:heavy_check_mark:|
|[Andrew](https://andrewnw.xyz/)|https://dns.andrewnw.xyz/dns-query|:heavy_check_mark:|Ad & porn blocking
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))|
| [Anudeep](https://anudeep.me) | https://secure.anudeep.me/dns-query | :heavy_check_mark: | Adblocking
|[Apollinaria](https://hypercute.eu/)|https://dns.hypercute.eu/dns-query| :heavy_check_mark: |
|[Aquilenet](https://www.aquilenet.fr/services/dns/)|https://dns.aquilenet.fr/dns-query|:heavy_check_mark:|Block ads
| [Artikel10](https://dns.artikel10.org/) | https://dns.artikel10.org/dns-query | :heavy_check_mark: | Non-logging service based in Germany
|Asteri Moon|https://dns.asterimoon.com/dns-query| :heavy_check_mark: | Adblocking
| [Avast](https://www.avast.com/dns) | https://secure.avastdns.com/dns-query | :heavy_check_mark: | Non-logging
| [Awan.ftp.sh](https://awan.ftp.sh/) | Ads and gambling blocking : https://awan.ftp.sh/dns-query <br> Ads, gambling, drug, tobacco block : https://awan.ftp.sh/no-vice <br> Porn, ads, gambling, drug, tobacco block : https://awan.ftp.sh/noporn-cl <br> Unblocked : https://awan.ftp.sh/unblocked | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Japan
|a47.me|https://dns.a47.me/dns-query|:heavy_check_mark:|
| **B**
|baishiyuan.cn|https://dns.baishiyuan.cn/dns-query|:heavy_check_mark:|Adblocking
|[Belnet](https://dns.belnet.be)|https://dns.belnet.be/dns-query|:heavy_check_mark:|
|b-ii|https://b-ii.com/dns-query|:heavy_check_mark:|Block ads
| Bitdefender | https://dns.bitdefender.net/dns-query | :heavy_check_mark: |
|[BITServices](https://www.bitservices.io/)|https://dns.bitservices.io/dns-query|:heavy_check_mark:|Adblocking
|[Blahdns](https://blahdns.com)|Finland: https://doh-fi.blahdns.com/dns-query<br>Germany: https://doh-de.blahdns.com/dns-query<br>Singapore: https://doh-sg.blahdns.com/dns-query<br>Japan: https://doh-jp.blahdns.com/dns-query<br>Switzerland: https://doh-ch.blahdns.com/dns-query|:heavy_check_mark:|Block ads, non-logging, no ECS, DNSSEC ready, support OpenNIC & ENS
| [Blokada DNS](https://community.blokada.org/t/the-benefits-of-blokada-dns/6646) | https://dns.blokada.org/dns-query | :heavy_check_mark: | No logging.
|bonis.de|https://adguard.bonis.de/dns-query|:heavy_check_mark:|
| [Brahma World](https://dns.brahma.world/home.html) | https://dns.brahma.world/dns-query | :heavy_check_mark: | No logging • Blocks Ads + Trackers + Malware + Phishing domains, DNSSEC ready • QNAME Minimization • No EDNS Client-Subnet
|bugz.fr|https://stratus.bugz.fr/dns-query|:heavy_check_mark:|Ad & porn blocking
|[bunny.net](https://bunny.net/)|https://doh1.b-cdn.net/dns-query<br>https://doh2.b-cdn.net/dns-query|:heavy_check_mark:|
|b612.me|https://dns.b612.me/dns-query|:heavy_check_mark:|
| **C**
|[Canarypwn](https://aaaab3n.moe/networks) | Cloudflare upstream: https://doh.aaaab3n.moe/dns-query-114514 | :heavy_check_mark: | 
|carter.me|https://dns.carter.me/dns-query|:heavy_check_mark:|Adblocking
|catdns.org|https://catdns.org/dns-query|:heavy_check_mark:|
|chadeyron.fr|https://dns.chadeyron.fr/dns-query|:heavy_check_mark:|Adblocking
|[Charter](https://corporate.charter.com/)|https://doh-01.spectrum.com/dns-query<br>https://doh-02.spectrum.com/dns-query|:heavy_check_mark:|
|[chenu.ch](https://chenu.ch/)|https://dns.chenu.ch/dns-query|:heavy_check_mark:|Adblocking
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: <br>https://private.canadianshield.cira.ca/dns-query <br> Protected: <br>https://protected.canadianshield.cira.ca/dns-query <br> Family: <br>https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
| [CIRCL](https://www.circl.lu/) | https://dns.circl.lu/dns-query  | :heavy_check_mark:| Adblocking
| [Cisco Umbrella (OpenDNS)](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query <br> Umbrella: https://doh.umbrella.com/dns-query | :heavy_check_mark: <br>:heavy_check_mark:<br> :heavy_check_mark:| DNSSEC, Anycast
| [CleanBrowsing](https://cleanbrowsing.org/help/docs/dnsoverhttps/) | https://doh.cleanbrowsing.org/doh/family-filter/ <br><br> Filter that allows some mixed-content sites: https://doh.cleanbrowsing.org/doh/adult-filter/ <br><br> Malware blocking only: https://doh.cleanbrowsing.org/doh/security-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
|[Cloud88](https://cloud88.com.au/)|https://dns.cloud88.com.au/dns-query|:heavy_check_mark:|Adblocking
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br><br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br><br> Block Malware: https://security.cloudflare-dns.com/dns-query <br><br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br><br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports both -04 and -13 content-types
|[Comss](https://www.comss.ru/)|https://dns.comss.one/dns-query|:heavy_check_mark:|Block ads
| [Control D](https://controld.com/free-dns) | Unfiltered: <br> https://freedns.controld.com/p0 <br> Malware (Block Malware): <br> https://freedns.controld.com/p1 <br> Ads & Tracking (Block Malware + Ads & Tracking): <br> https://freedns.controld.com/p2 <br> Social (Block Malware + Ads & Tracking + Social Networks): <br> https://freedns.controld.com/p3 <br> Family Friendly (Block Malware + Ads & Tracking + Adult Content + Drugs): <br> https://freedns.controld.com/family <br> Uncensored (Unblock censored domains from various countries) <br> https://freedns.controld.com/uncensored <br><br> - 3rd Party Filters - <br><br> OISD - Full: <br> https://freedns.controld.com/x-oisd <br> OISD - Basic: <br> https://freedns.controld.com/x-oisd-basic <br> StevenBlack Unified: <br> https://freedns.controld.com/x-stevenblack <br> Dev Dan's Hosts: <br> https://freedns.controld.com/x-devdan <br> 1Hosts - Mini: <br> https://freedns.controld.com/x-1hosts-mini <br> 1Hosts - Lite: <br> https://freedns.controld.com/x-1hosts-lite <br> 1Hosts - Pro: <br> https://freedns.controld.com/x-1hosts-pro <br> Hagezi's DNS - Light <br> https://freedns.controld.com/x-hagezi-light <br> Hagezi's DNS - Normal: <br> https://freedns.controld.com/x-hagezi-normal <br> Hagezi's DNS - Pro: <br> https://freedns.controld.com/x-hagezi-pro <br> Hagezi's DNS - Pro Plus: <br> https://freedns.controld.com/x-hagezi-proplus <br> Hagezi's DNS - Ultimate: <br> https://freedns.controld.com/x-hagezi-ultimate <br> Hagezi's DNS - TIF (Threat Intelligence Feeds) <br> https://freedns.controld.com/x-hagezi-tif <br> GoodbyeAds: <br> https://freedns.controld.com/x-goodbyeads <br> AdGuard Filter: <br> https://freedns.controld.com/x-adguard <br> | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | ControlD is a fully customizable anycast DNS service that allows you to not only block annoyances like malware, tracking, ads, IoT telemetry, and more but also unblock over 180 services through a network of proxies in over 100 cities.
|[CubeDNS](https://cubedns.com/)|https://cubedns.com/dns-query|:heavy_check_mark:|
|[CynthiaLabs](https://cynthialabs.net/dns/)|https://dns.cynthialabs.net/dns-query|:heavy_check_mark:|Adblocking
| [CZ.NIC](https://www.nic.cz/odvr/) | https://odvr.nic.cz/dns-query | :heavy_check_mark:| Runs on [Knot Resolver](https://www.knot-resolver.cz/) (`doh2`), supports DNSSEC, provided by `.cz` TLD operator
| **D**
|daemon.za.net|https://dns.daemon.za.net/dns-query|:heavy_check_mark:|
| [Danielle McLean](https://00dani.me/) | https://ns.00dani.me/dns-query | :heavy_check_mark: |
| [data.haus](https://data.haus/) | https://ns.data.haus/dns-query | :heavy_check_mark: | Adblocking, non-logging
|dev-umbrellagov|https://dns.dev-umbrellagov.com/dns-query| :heavy_check_mark: | 
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/dns/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
| Disconnect.app | https://doh.disconnect.app/dns-query | :heavy_check_mark: | 
| [dns.digitalsize.net](https://dns.digitalsize.net/) | https://dns.digitalsize.net/dns-query | :heavy_check_mark: | A public, non-tracking, non-filtering DNS resolver with DNSSEC enabled and hosted in Germany |
|dns.expert|https://dns.expert/dns-query| :heavy_check_mark: |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query <br> https://doh.sb/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| DNSSEC & QNAME minimization enabled, no logging |
| [dns0.eu](https://www.dns0.eu/) | Non-blocking: https://open.dns0.eu<br>Malware blocking: https://dns0.eu<br>Hardened security: https://zero.dns0.eu<br>Child safe: https://kids.dns0.eu | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Non-logging, GDPR compliant
|[DNS4all](https://dns4all.eu/)|https://doh.dns4all.eu/dns-query|:heavy_check_mark:| Non-logging
|[dns4me](https://dns4me.net)|https://ca01.dns4me.net<br>https://us01.dns4me.net<br>https://sg01.dns4me.net<br>https://sa01.dns4me.net<br>https://au01.dns4me.net<br>https://uk01.dns4me.net<br>https://nz01.dns4me.net|:heavy_check_mark:|
| [dnscry.pt](https://www.dnscry.pt/) | Adelaide, Australia: https://adl01.dnscry.pt/dns-query<br>Allentown, US: https://abe01.dnscry.pt/dns-query<br>Atlanta, US: https://atl01.dnscry.pt/dns-query<br>Budapest, Hungary: https://bud01.dnscry.pt/dns-query<br>Chicago, US: https://ord01.dnscry.pt/dns-query<br>Chișinău, Moldova: https://kiv01.dnscry.pt/dns-query<br>Coeur d'Alene, US: https://coe01.dnscry.pt/dns-query<br>Coventry, UK: https://cvt01.dnscry.pt/dns-query<br>Dallas, US: https://dfw02.dnscry.pt/dns-query<br>Denver, US: https://den01.dnscry.pt/dns-query<br>Detroit, US: https://dtw01.dnscry.pt/dns-query<br>Durham, US: https://rdu01.dnscry.pt/dns-query<br>Düsseldorf, Germany: https://dus01.dnscry.pt/dns-query<br>Ebène, Mauritius: https://mru01.dnscry.pt/dns-query<br>Eygelshoven, Netherlands: https://eyg01.dnscry.pt/dns-query<br>Flint, US: https://fnt01.dnscry.pt/dns-query<br>Frankfurt, Germany: https://fra01.dnscry.pt/dns-query<br>Fremont, US: https://fet01.dnscry.pt/dns-query<br>Fujairah, UAE: https://fjr01.dnscry.pt/dns-query<br>Geneva, Switzerland: https://gva01.dnscry.pt/dns-query<br>Helsinki, Finland: https://hel01.dnscry.pt/dns-query<br>Hong Kong Spike Telecom: https://hkg01.dnscry.pt/dns-query<br> Hong Kong MillenialHost: https://hkg02.dnscry.pt/dns-query<br>Istanbul, Turkey: https://ist01.dnscry.pt/dns-query<br>Jakarta, Indonesia: https://jkt01.dnscry.pt/dns-query<br>Kharkiv, Ukraine: https://hrk01.dnscry.pt/dns-query<br>Lagos: https://los01.dnscry.pt/dns-query<br>Las Vegas, US: https://las01.dnscry.pt/dns-query<br>Liberty Lake, US: https://llk01.dnscry.pt/dns-query<br>Lima, Colombia: https://lim01.dnscry.pt/dns-query<br>London, UK: https://lon01.dnscry.pt/dns-query<br>Los Angeles Webhosting24, US: https://lax01.dnscry.pt/dns-query<br>Los Angeles CrownCloud, US: https://lax02.dnscry.pt/dns-query<br>Madrid, Spain: https://mad01.dnscry.pt/dns-query<br>Miami, US: https://mia01.dnscry.pt/dns-query<br>Milan, Italy: https://mil01.dnscry.pt/dns-query<br>Mumbai, India: https://bom01.dnscry.pt/dns-query<br>Munich, Germany: https://muc01.dnscry.pt/dns-query<br>New York, US: https://nyc01.dnscry.pt/dns-query<br>Nuremberg, Germany: https://nue01.dnscry.pt/dns-query<br>Oradea, Romania: https://omr01.dnscry.pt/dns-query<br>Ottoville, US: https://ott01.dnscry.pt/dns-query<br>Paris, France: https://par01.dnscry.pt/dns-query<br>Philadelphia, US: https://phl01.dnscry.pt/dns-query<br>Phoenix, US: https://phx01.dnscry.pt/dns-query<br>Portland, US: https://pdx01.dnscry.pt/dns-query<br>Port Edwards, US: https://ped01.dnscry.pt/dns-query<br>Salt Lake City, US: https://slc01.dnscry.pt/dns-query<br>Sandefjord, Norway: https://trf01.dnscry.pt/dns-query<br>Santa Clara, US: https://sjc01.dnscry.pt/dns-query<br>Seattle, US: https://sea01.dnscry.pt/dns-query<br>Singapore WebHosting24: https://sin01.dnscry.pt/dns-query<br>Singapore WebHorizon: https://sin02.dnscry.pt/dns-query<br>Sofia: https://sof01.dnscry.pt/dns-query<br>Spokane, US: https://geg01.dnscry.pt/dns-query<br>Stockholm, Sweden: https://sto01.dnscry.pt/dns-query<br>Sydney, Australia: https://syd01.dnscry.pt/dns-query<br>Taipei, Taiwan: https://tpe01.dnscry.pt/dns-query<br>Tallinn, Estonia: https://tll01.dnscry.pt/dns-query<br>Tampa, US: https://tpa01.dnscry.pt/dns-query<br>Taos, US: https://tsm01.dnscry.pt/dns-query<br>Tokyo WebHosting24, Japan: https://tyo01.dnscry.pt/dns-query<br>Tokyo WebHorizon, Japan: https://tyo02.dnscry.pt/dns-query<br>Toronto, Canada: https://yyz01.dnscry.pt/dns-query<br>Valdivia, Chile: https://zal01.dnscry.pt/dns-query<br>Vienna, Austria: https://vie01.dnscry.pt/dns-query<br>Warsaw, Poland: https://waw02.dnscry.pt/dns-query| :heavy_check_mark:| Support IPv4+IPv6, uncensored, unfiltered, encrypted, DNSSEC, no logging.
| [dnsforge.de](https://dnsforge.de/) | Adblocking : https://dnsforge.de/dns-query <br> Ads and pornblocking : https://clean.dnsforge.de/dns-query |:heavy_check_mark:<br>:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|
| [dnslow.me](https://dnslow.me/) | https://dnslow.me/dns-query | :heavy_check_mark: | A protective DNS that blocks Ads, Malware, Trackers, Phishing and Newly Registered Domains. Randomly forward requests to different upstreams for enhanced privacy. |
| [DNSPod](https://docs.dnspod.cn/public-dns/dot-doh/) | https://dns.pub/dns-query | :heavy_check_mark: | Operated by Tencent Cloud
| [dnswarden](https://dnswarden.com)| Adblock - <br> https://dns.dnswarden.com/adblock <br><br> Uncensored -<br> https://dns.dnswarden.com/uncensored <br><br> AdultFilter - <br>  https://dns.dnswarden.com/adultfilter | <br>:heavy_check_mark:<br><br><br> :heavy_check_mark:<br><br><br>:heavy_check_mark: | A zero logging DNS with support for DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) & Dnscrypt. Supports DNSSEC, TLS 1.3, QNAME minimization and does own Recursion. EDNS Client Subnet is disabled.<br> Provides 4 different types of filtering options.<br> Adblock - Blocks ads, trackers, viruses, and telemetry.<br> Adultfilter - Blocks adult content, enforces safe search, and includes all the features from adblock. <br> Uncensored - Unrestricted access/no filtering.<br>[Custom Filter](https://dnswarden.com/customfilter.html) where you can choose your own filter lists! <br>For more information look [here](https://github.com/bhanupratapys/dnswarden) or [here](https://dnswarden.com). |
|dnswebvsn.com|https://dnswebvsn.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|doh.best|https://dns.doh.best/dns-query|:heavy_check_mark:|Adblocking
|doh.xyz|https://doh.xyz/dns-query|:heavy_check_mark:|
|[Dom!nic](https://dom1nic.eu/)|https://3dns.eu/dns-query|:heavy_check_mark:|
| [Dukun.de](https://dukun.de/) |https://dukun.de/dns-query | :heavy_check_mark: |
|dyn1.de|https://dns.dyn1.de/dns-query|:heavy_check_mark:|Block ads
| **E**
|[EasyMosdns](https://doh.apad.pro/)|https://doh.apad.pro/dns-query|:heavy_check_mark:|
| [Edgy DNS](https://edgy.network/dns) | https://edgy-dns.com/dns-query | :heavy_check_mark: | Adblocking
|editechstudio|https://dns.editechstudio.com/dns-query|:heavy_check_mark:|Block ads & gambling
|[Egor Glukhikh](https://henek.ovh/)|https://dns.henek.ovh/dns-query|:heavy_check_mark:|Adblocking
|[ELIV](https://dns.eliv.co.kr)|https://dns.eliv.co.kr/dns-query|:heavy_check_mark:|Block ads
| [Emiliyan Parvanov](https://emiliyan.com/) | https://dns.emiliyan.com/dns-query | :heavy_check_mark: | Adblocking
|[Enzonix](https://enzonix.com)|https://dns.enzonix.com/dns-query|:heavy_check_mark:|Block ads
|engineer.web.id|https://dns.engineer.web.id/dns-query|:heavy_check_mark:|Block ads
| **F**
|familiamv.net|https://dnsvps.familiamv.net/dns-query|:heavy_check_mark:|Adblocking
| Fancyorg.at | https://dns.fancyorg.at/dns-query |  :heavy_check_mark: | Adblocking
| [FDN](https://www.fdn.fr/) - French Data Network | https://ns0.fdn.fr/dns-query <br> https://ns1.fdn.fr/dns-query |:heavy_check_mark:| No log, no filter, DNSSEC, … ([more informations in French](https://www.fdn.fr/ouverture-des-services-dot-doh/)) |
| [ffmuc.net](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
| Flm9.net | https://dns01.flm9.net/dns-query |  :heavy_check_mark: |
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| [Froth.zone](https://dns.froth.zone/resolver) | https://dns.froth.zone/dns-query | :heavy_check_mark: | OpenNIC
|fullaccesstointernet.jp.eu.org|https://dns.fullaccesstointernet.jp.eu.org/dns-query|:heavy_check_mark:|
|futa.gg|https://doh.futa.gg/dns-query|:heavy_check_mark:|Block ads
| **G**
|[Gamban](https://gamban.com/)|https://dns.gamban.com/dns-query|:heavy_check_mark:|
|[Gensokyo](https://freyja.pw/)|https://dns.freyja.pw/dns-query|:heavy_check_mark:|Adblocking
| [Google](https://developers.google.com/speed/public-dns/docs/doh) | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query <br> https://8888.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Full RFC 8484 support, EDNS, no filtering.
|[Guardio](https://guard.io/)|https://dns.guard.io/dns-query|:heavy_check_mark:|
| **H**
|[HiNet](https://hinet.net)|https://dns.hinet.net/dns-query|:heavy_check_mark:|
|hitian.me|https://hitian.me/dns-query|:heavy_check_mark:|
| [Hostux.net](https://dns.hostux.net) |  Nonblocking: https://dns.hostux.net/dns-query <br> Adblocking: https://dns.hostux.net/ads | :heavy_check_mark: |DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
| Huque | https://doth.huque.com/dns-query | :heavy_check_mark: | 
|[Hurricane Electric](https://forums.he.net/index.php?topic=3996.0)|https://ordns.he.net|:heavy_check_mark:|
| **I**
|[Ian ROCKS](https://blog.ian.rocks)|https://dns.ian.rocks/dns-query|:heavy_check_mark:|Block ads & porn
|ikarosalpha.xyz|https://ikarosalpha.xyz/dns-query|:heavy_check_mark:|Adblocking
| [In-Berlin](https://wiki.in-berlin.de/dns) | https://dns1.in-berlin.de/dns-query | :heavy_check_mark: |
|indybanipal.com|https://dns.indybanipal.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Institut national de recherche en sciences et technologies du numérique](https://www.inria.fr/fr) | https://qlf-doh.inria.fr/dns-query | :heavy_check_mark: |
| [Internet Initiative Japan](https://public.dns.iij.jp/) | https://public.dns.iij.jp/dns-query | :heavy_check_mark: | Planned to run until March 2027 
|is.my.waifu.cz|https://aqua.is.my.waifu.cz/dns-query<br>https://megumin.is.my.waifu.cz/dns-query<br>https://darkness.is.my.waifu.cz/dns-query|:heavy_check_mark:|
|[i2pd.xyz](https://opennic.i2pd.xyz)|https://opennic.i2pd.xyz/dns-query|:heavy_check_mark:|Also resolves OpenNIC domains
| **J**
| Jackyes.ovh | https://jackyes.ovh/dns-query | :heavy_check_mark: | Adblocking
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query | :heavy_check_mark: | No Censorship, No Logging, No ECS, support DNSSEC in Japan |
|[Justin Counts](https://justincounts.com/)|https://ad.justincounts.com/dns-query|:heavy_check_mark:|
| **K**
|[[Kamil Szczepański](https://kamilszczepanski.com/)|https://dns.kamilszczepanski.com/dns-query|:heavy_check_mark:|Block ads
|kawa.tf|https://dns.kawa.tf/dns-query|:heavy_check_mark:|Block ads
|keke125|https://dns.keke125.com/dns-query|:heavy_check_mark:|Adblocking
|Kerekes|https://dns.kerekes.xyz/dns-query|:heavy_check_mark:|Adblocking
|[kescher](https://dns.kescher.at)|https://dns.kescher.at/dns-query|:heavy_check_mark:|DNSSEC-validating
|kipp.cool|https://noad.kipp.cool/dns-query|:heavy_check_mark:|Block ads
|[Kishore](https://avdkishore.dev/)|https://adguard.avdkishore.dev/dns-query|:heavy_check_mark:|
|[Koala](https://koala.us.to)|https://dns.koala.us.to/dns-query|:heavy_check_mark:|Adblocking
|kooman|https://doh.kooman.org/dns-query|:heavy_check_mark:|
|Konikoni428|https://adguard.konikoni428.com/dns-query|:heavy_check_mark:|Adblocking
|[KRC Technologies](https://krctechnologies.net)|https://pdns.krctechnologies.net/dns-query|:heavy_check_mark:|Block ads
| Krnl.eu | https://xray.krnl.eu/dns-query | :heavy_check_mark: | Adblocking
|kugoapps|https://dns.kugoapps.com/dns-query|:heavy_check_mark:|Block ads
|Kukal|https://dns.kukal.cz/dns-query| :heavy_check_mark: | Adblocking
|kusoneko|https://dns.kusoneko.moe:9443/dns-query|:heavy_check_mark:|
| **L**
| [La Contre-Voie](https://lacontrevoie.fr/en/services/doh/) | https://doh.lacontrevoie.fr/dns-query | :heavy_check_mark: | Supports DNSSEC and IPv6, not logging queries' content, uses [unbound](https://github.com/NLnetLabs/unbound/). Commits for net neutrality, hosted in France.
|[Lars Lehmann](https://larsl.net/)|https://dns.lars-lehmann.net/dns-query|:heavy_check_mark:|
| [LavaDNS](https://dns.lavate.ch/) | Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in Finland. No logging, no filtering, no ECS, DNSSEC support. |
|[Levonet](https://www.levonet.sk/)|https://dns.levonet.sk/dns-query|:heavy_check_mark:|
|[LibreDNS](https://libredns.gr/) | Non-filtering: https://doh.libredns.gr/dns-query <br> Adblocking: https://doh.libredns.gr/noads| :heavy_check_mark: <br> :heavy_check_mark: | Non-logging, OpenNIC.
| [Lindung](https://lindung.pp.ua/) | Adblocking: https://lindung.pp.ua/dns-query <br> Ad & porn blocking: https://lindung.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |
|[Lista](https://lista.my.id/dns-lista-sudah-online-untuk-publik/)|https://dns.lista.my.id/dns-query|:heavy_check_mark:|Block ads
|[LobbyGod](https://lobbygod.com/)|https://dns.lobbygod.com/dns-query|:heavy_check_mark:|
|loii.in|https://ca.loii.in/dns-query|:heavy_check_mark:|Block ads
|[loNET](https://dns.lonet.org/) | Germany 1: https://doh.phdns1.lonet.org/dns-query <br>Germany 2: https://doh.phdns2.lonet.org/dns-query  | :heavy_check_mark:|Adblocking
| **M**
|mandre.dev|https://dns.mandre.dev/dns-query|:heavy_check_mark:|Adblocking
|maskab|https://doh.maskab.com/dns-query|:heavy_check_mark:|
| [Masters of Cloud](https://www.masters-of-cloud.de/) | https://masters-of-cloud.de/dns-query | :heavy_check_mark: | 
|mateo.ovh|https://dns.mateo.ovh/dns-query|:heavy_check_mark:|Block ads & porn
|[Maxindo Mitra Solusi](https://max.net.id)|https://doh.max.net.id/dns-query|:heavy_check_mark:|
|meddy94.de|https://adguard.meddy94.de/dns-query|:heavy_check_mark:|Adblocking
|meexx.de|https://testguard.meexx.de/dns-query|:heavy_check_mark:|Adblocking
|[MegaNerd.nl](https://www.meganerd.nl/encrypted-dns-server)|https://snoke.meganerd.nl/dns-query|:heavy_check_mark:|
|[MERCURY](https://mtsoln.com/)|https://ns.mtsoln.com/dns-query|:heavy_check_mark:|Adblocking
|meshkov.info|https://testaghome.meshkov.info/dns-query|:heavy_check_mark:|Block ads
|mnet-online.de|https://dns.mnet-online.de/dns-query|:heavy_check_mark:|
|[modr.club](https://modr.club/)|https://ps1.modr.club/dns-query|:heavy_check_mark:|
|modsh.top|https://dot.modsh.top/dns-query|:heavy_check_mark:|Block ads
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | Non-blocking https://dns.mullvad.net/dns-query <br> Adblocking https://adblock.dns.mullvad.net/dns-query <br> Ad & malware blocking https://base.dns.mullvad.net/dns-query <br> Ad, malware, social media blocking https://extended.dns.mullvad.net/dns-query <br> Ad, malware, social media, adult content and gamble blocking https://all.dns.mullvad.net/dns-query <br> Ad, malware, adult content and gamble blocking https://family.dns.mullvad.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Public DoH server in US, DE, GB, SG, and SE with QNAME minimization, audited by [Assured](https://www.assured.se/wp-content/uploads/2021/03/Assured_Mullvad_DoH_server_audit_report.pdf)
| [mydns.network](https://mydns.network) | Uncensored: https://freedom.mydns.network/dns-query <br> Paranoia (no Google/Cloudflare): https://paranoia.mydns.network/dns-query <br> Adblocking: https://adblock.mydns.network/dns-query <br> Family: https://family.mydns.network/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Public DoH server powered by Cloudflare Workers. Uniquely disguises your queries by relaying queries your behalf to upstream DoH servers with no IP address information. [Open source](https://github.com/matthewgall/doh-proxy), deploy your own instance at any time!
| **N**
|narl.app|https://dns.narl.app/dns-query|:heavy_check_mark:|Adblocking
|[Neil](https://neilzone.co.uk)|https://dns.neilzone.co.uk/dns-query|:heavy_check_mark:|Adblocking
|nenam.eu|https://nenam.eu/dns-query|:heavy_check_mark:|
|[Newpangea](https://newpangea.de/service/resolvers/overview/)|https://dns1.us.newpangea.de/dns-query<br>https://dns1.in.newpangea.de/dns-query<br>https://dns1.pl.newpangea.de/dns-query|:heavy_check_mark:|
| Nexific.it | https://doh.luigi.nexific.it/dns-query | :heavy_check_mark:|
| [NextDNS](https://nextdns.io) | https://dns.nextdns.io | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free with non-filtering afterward until the end of the month. Granular dashboard, Each account can create multiple configurations, which can be used for multiple devices with prefixes to track activities on the dashboard. [Create a config ID](https://my.nextdns.io/start)
|nhtsky|https://dns.nhtsky.com/dns-query|:heavy_check_mark:|Block ads
| [NIC.LV](https://doh.lv/) | https://doh.lv/dns-query <br> https://doh.nic.lv/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run by .lv TLD registry 
| [Nightly Moon](https://nightlymoon.us.kg/) | Adblocking https://nightlymoon.us.kg/dns-query <br> Adblocking & porn blocking https://nightlymoon.us.kg/family | :heavy_check_mark: <br> :heavy_check_mark: |
| [NiYaWe](https://www.niyawe.de/) | https://doh.niyawe.de/dns-query | :heavy_check_mark: |
| [Njalla](https://dns.njal.la/) | https://dns.njal.la/dns-query | :heavy_check_mark: | Non logging, based in Sweden
| [No Ad DNS](https://noaddns.com/) | https://resolver.noaddns.com/dns-query | :heavy_check_mark: | Adblocking
| [Node15](https://node15.com/) | https://pi1.node15.com/dns-query | :heavy_check_mark: | Block ads and porn
| [NordVPN](https://nordvpn.com)|https://dns1.nordvpn.com/dns-query <br> https://dns2.nordvpn.com/dns-query| :heavy_check_mark: |
|[Noridev](https://adblock.noridev.moe/html/dns_android.html) | https://1.dns.noridev.moe/dns-query |:heavy_check_mark:|Adblocking
|novg.net|https://dns.novg.net/dns-query|:heavy_check_mark:|
|[NS3](https://ns3.com/web)|https://dns8.org/dns-query<br>https://n0.eu/dns-query<br>https://ns3.com/dns-query<br>https://ns3.cx/dns-query<br>https://ns3.link/dns-query|:heavy_check_mark:|
|nydau.fr|https://dns.nydau.fr|:heavy_check_mark:|
| **O**
|oliviertv|https://dns.oliviertv.co.za/dns-query|:heavy_check_mark:|Adblocking
|[OpenBLD.net](https://openbld.net/) | Adapted: https://ada.openbld.net/dns-query <br> Strict: https://ric.openbld.net/dns-query |:heavy_check_mark: <br> :heavy_check_mark:|Adblocking
|[OSZX DNS](https://dns.oszx.co/)|https://dns.oszx.co/dns-query|:heavy_check_mark:|Adblocking
| **P**
| [PaesaDNS](https://milgradesec.github.io/paesadns/) | https://dns.paesa.es/dns-query | :heavy_check_mark: | Adblocking, non-logging
| Path of Grace | https://doh.gcp.pathofgrace.com/dns-query | :heavy_check_mark: | Adblocking
|[Paulo](https://paulo.nom.za)|https://paulo.nom.za/dns-query| :heavy_check_mark: | Adblocking
|pesaventofilippo|https://dns.pesaventofilippo.com/dns-query|:heavy_check_mark:|Adblocking
|phillipjberry.net|https://dns.phillipjberry.net/dns-query|:heavy_check_mark:|Block ads
|pietjacobs.be|https://dns1.pietjacobs.be/dns-query|:heavy_check_mark:|Adblocking
|[plan9-dns](https://github.com/jlongua/plan9-dns)|New Jersey: https://kronos.plan9-dns.com/dns-query<br>Mexico: https://helios.plan9-dns.com/dns-query<br>Florida: https://pluton.plan9-dns.com/dns-query|:heavy_check_mark:|
|[PlumeDNS](https://plumedns.com)|https://privacy.plumedns.com/dns-query|:heavy_check_mark:|Block ads
|pooblet.co.za|https://pooblet.co.za/dns-query|:heavy_check_mark:|Adblocking
|powerbs.net|https://dns.powerbs.net/dns-query|:heavy_check_mark:|Block ads
|[PragmaSEC](https://pragmasec.nl/)|https://dns.pragmasec.nl/dns-query|:heavy_check_mark:|Adblocking
|[Pubhole](https://pubhole.archuser.org/)|https://doh.archuser.org/dns-query|:heavy_check_mark:|Block ads, also resolves OpenNIC
|puregeni.us|https://dns-privacy.puregeni.us/dns-query|:heavy_check_mark:|Adblocking
|pzhg.me|https://vpsus3.pzhg.me/dns-query|:heavy_check_mark:|Block ads
| **Q**
| [Quad9](https://quad9.net) | 9.9.9.9 (Secure): A threat-blocking, privacy-first recursive DNS service. <br> https://dns.quad9.net/dns-query <br><br> 9.9.9.10 (No Threat Blocking): For users who want to take advantage of privacy-first recursive DNS service, but do not want threat blocking. <br> https://dns10.quad9.net/dns-query <br><br> 9.9.9.11 (Secure + ECS): For users who do not route to the closest-possible Quad9 location, use 9.9.9.11 for better CDN performance. <br> https://dns11.quad9.net/dns-query <br><br> 9.9.9.12 (No Threat Blocking + ECS): For users who do not route to the closest-possible Quad9 location, and also do not want threat blocking, use 9.9.9.12 for better CDN performance. <br> https://dns12.quad9.net/dns-query | ✔️ <br> ✔️ <br> ✔️ <br> ✔️ | 9.9.9.9 - Malware blocking, DNSSEC validation <br> 9.9.9.10 - No malware blocking, no DNSSEC validation <br> 9.9.9.11 - Malware blocking, DNSSEC validation, ECS enabled <br> 9.9.9.12 - No malware blocking, no DNSSEC validation, ECS enabled
|[quydang.name.vn](https://quydang.name.vn/)|https://adguard.quydang.name.vn/dns-query|:heavy_check_mark:|
| **R**
|[RAL9005](https://ral9005.org/)|https://ns.ral9005.org/dns-query|:heavy_check_mark:|Adblocking
|[Restena](https://www.restena.lu/en/document/190-configuring-your-server-public-dns-resolver)|https://dnspub.restena.lu/dns-query|:heavy_check_mark:|DNSSEC validation
|[RetakeCS](https://retakecs.com/)|https://dns.retakecs.com/dns-query|:heavy_check_mark:|Adblocking
| [RethinkDNS](https://www.rethinkdns.com/) | Non-filtering: https://sky.rethinkdns.com/dns-query <br> OISD: https://sky.rethinkdns.com/1:IAAgAA== | :heavy_check_mark: <br> :heavy_check_mark: | [An open-source stub resolver](https://github.com/serverless-dns/serverless-dns) running in 200+ locations world-wide on Cloudfare's network. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logs. [code](https://github.com/celzero/rethink-app). [Configure custom blocklists](https://rethinkdns.com/configure)
|[Rezha Julio](https://rezhajul.io/)|https://doh.rezhajul.io/dns-query|:heavy_check_mark:|Block ads & gambling
| Rin.sh | https://dns.rin.sh/dns-query | :heavy_check_mark: |
|[RobinGroppe.de](https://www.robingroppe.de/serverzeug/dns-server)|https://dns.rbn.gr/dns-query|:heavy_check_mark:| Malware blocking, DNSSEC validation
| [RoTunneling](https://www.rotunneling.net/rotunneling-doh-free/) | https://dns.rotunneling.net/dns-query/public | :heavy_check_mark: | Adblocking
|[Ruby.ci](https://ruby.ci/)|https://adguard.ruby.ci/dns-query|:heavy_check_mark:|Adblocking
|rueiliu|https://adg.rueiliu.space/dns-query|:heavy_check_mark:|Adblocking
|ryan palmer|https://dns1.ryan-palmer.com/dns-query|:heavy_check_mark:|
| **S**
| [Safe Surfer](https://safesurfer.io/) | https://doh.safesurfer.io/dns-query | :heavy_check_mark: | Filter porn sites, enforce safe search
| [SafeServe](https://www.namecheap.com/dns/free-public-dns/) | https://safeservedns.com/dns-query | :heavy_check_mark: | Operated by Namecheap
|saneaki|https://dns.saneaki.com/dns-query|:heavy_check_mark:|Block ads
|[Sari](https://sarilouis.com/)|https://dns.sarilouis.com/dns-query|:heavy_check_mark:|
|sc-lezhi.com|https://ns1.sc-lezhi.com/dns-query|:heavy_check_mark:|Adblocking
|[Sheggi](https://sheggi.ch/)|https://dns.sheggi.ch/dns-query|:heavy_check_mark:|Porn blocking
|shoupperuser.com|https://adguard.shoupperuser.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|shutgaming.net|https://adguard.shutgaming.net/dns-query|:heavy_check_mark:|Adblocking
|signsservers.ru|https://signsservers.ru/dns-query|:heavy_check_mark:|Block ads
|silen.org|https://dns.silen.org/dns-query|:heavy_check_mark:|Block ads
|[Silentlybren](https://silentlybren.com/)|https://dns.silentlybren.com/dns-query|:heavy_check_mark:|Adblocking
| Slinkyman.net | https://dns.slinkyman.net/dns-query | :heavy_check_mark: | Adblocking
|[SmartGuard](https://www.smartguard.io/en#server)|https://dns.smartguard.io/dns-query|:heavy_check_mark:|Customizable policy and filtering
|[spacedns.org](https://spacedns.org/index.html)| https://spacedns.org/dns-query | :heavy_check_mark: | Adblocking, hosted in Poland
|[StuSta](https://www.stusta.de/en/)|https://muli.stusta.mhn.de/dns-query|:heavy_check_mark:|
|sukidayo.eu.org|https://sukidayo.eu.org/dns-query|:heavy_check_mark:|
| [Sundalandia](https://sundalandia.pp.ua) | Adblock https://sundalandia.pp.ua/dns-query <br> Family filter https://sundalandia.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |
|[Sunet DNS](https://wiki.sunet.se/display/DNS/Sunet+DNS) | https://resolver.sunet.se/dns-query |:heavy_check_mark:|
|sunnygyl.com|https://sunnygyl.com/dns-query|:heavy_check_mark:|Adblocking
|superstefan.win|https://dns.superstefan.win/dns-query|:heavy_check_mark:|Adblocking
|[Svoi](https://svoi.dev/)|https://dns.svoi.dev/dns-query| :heavy_check_mark: | 
|[Switch](https://www.switch.ch/en/switch-public-dns)|https://dns.switch.ch/dns-query|:heavy_check_mark:|Block porn & gambling
| [Syshero](https://syshero.org/) | https://doh.syshero.org/dns-query | :heavy_check_mark: | 
| **T**
| t53.de | https://dns.t53.de/dns-query | :heavy_check_mark: |
|technicule.info|https://vpn.technicule.info/dns-query|:heavy_check_mark:|
|technostriker|https://dns.technostriker.com/dns-query|:heavy_check_mark:|Block ads & porn
| [Telekom Deutschland](https://telekomhilft.telekom.de/t5/Offentliche-Tests-Umfragen/Telekom-hilft-Labor-Testet-mit-uns-DNS-over-HTTPS/m-p/5008054) | https://dns.telekom.de/dns-query | :heavy_check_mark: | 
|[The Good Source](https://www.thegoodsource.net/)|https://dns.thegoodsource.net/dns-query|:heavy_check_mark:|Block porn and violent extremism
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
|Tirapan.top|https://tirapan.top/nomen-quaesitum|:heavy_check_mark:|
| Tls-data.de | https://dns.tls-data.de/dns-query | :heavy_check_mark: |
|[totoro625](https://totoro.pub/)|https://doh.totoro.pub/dns-query/|:heavy_check_mark:|
|[Trash.net](https://www.trash.net/doh/)|Nonblocking: https://resolv1.trash.net/trash-dns<br>https://resolv2.trash.net/trash-dns<br>Adblocking: https://resolv3.trash.net/trash-dns|:heavy_check_mark: |
|[TrcNeTin](https://ns1.trcnet.fi)|https://ns.trcnet.fi/dns-query|:heavy_check_mark:|
|[truta](https://helio.loureiro.eng.br/index.php/todas-categorias/70-networking/19-apache/463-criando-um-servico-de-relay-de-dns-over-https)|https://truta.org/dns-query|:heavy_check_mark:|
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
| **U**
| [Unstoppable Domains](https://docs.unstoppabledomains.com/d-websites/resolving-dwebsites-in-a-browser/) | https://resolver.unstoppable.io/dns-query | :heavy_check_mark: | Also resolve `.crypto` TLD of Unstoppable Domains.
|unx.io|https://dns.unx.io/dns-query|:heavy_check_mark:|
|[Usable Privacy](https://docs.usableprivacy.com/dns)|https://adfree.usableprivacy.net/dns-query|:heavy_check_mark:|Block ads
| **V**
|[Val Cosmos](https://valscosmos.com)|https://doh.valscosmos.com|:heavy_check_mark:|Block ads
|[Vasili Sviridov](https://vasi.li)|https://tor.vasi.li/dns-query|:heavy_check_mark:|
|[VIA](https://viatech.com.tw)|https://doh.viatech.com.tw/dns-query|:heavy_check_mark:|Block ads
|[Vinny Perella](https://vinnyp.xyz)|https://dns.vinnyp.xyz/dns-query|:heavy_check_mark:|
| [Virga DNS](https://virga.pp.ua) | Adblocking https://virga.pp.ua/dns-query <br> Adblocking & porn blocking https://virga.pp.ua/porn | :heavy_check_mark: <br> :heavy_check_mark: | Server in Japan
| **W**
|wahr.top|https://dns.wahr.top/dns-query|:heavy_check_mark:|
|[Wang Art](https://wang.art/)|https://dns.wang.art/dns-query|:heavy_check_mark:|Adblocking
|waringer-atg.de|https://abel.waringer-atg.de/dns-query|:heavy_check_mark:|
|warpnine.de|https://dns.warpnine.de/dns-query|:heavy_check_mark:|Block ads
|[Wheezy Notes](https://wheezy.naftalie.net/)|https://doh-ca.naftalie.net/dns-query|:heavy_check_mark:|
|[Wikimedia DNS](https://wikitech.wikimedia.org/wiki/Wikimedia_DNS)|https://wikimedia-dns.org/dns-query|:heavy_check_mark:|No filtering, no ECS except for Wikimedia-run servers, QNAME minimization enabled, DNSSEC validation enforced. Requests are served by the nearest Wikimedia data center.
|wixxm.asia|https://dns.wixxm.asia/dns-query|:heavy_check_mark:|Block ads
| **Y**
| [Yarp](https://yarp.lefolgoc.net/) | https://yarp.lefolgoc.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted in France, no logging.
|[yatima](https://yatima.tv/)|https://dns.yatima.tv/dns-query|:heavy_check_mark:|Adblocking
|[your-dns](https://github.com/yegle/your-dns)|https://your-dns.run/dns-query|:heavy_check_mark:|Block ads
| **Z**
|zburger.top|https://www.zburger.top/dns-query|:heavy_check_mark:|
| **0-9**
|[0ms.dev](https://0ms.dev)|https://0ms.dev/dns-query|:heavy_check_mark:|Block ads
|l6.ee|https://dns.l6.ee/dns-query|:heavy_check_mark:|Block ads
|0x55|https://dns.0x55.net/dns-query|:heavy_check_mark:|
|52306.org|https://dns.52306.org/dns-query|:heavy_check_mark:|
|9999.sg|https://dns.9999.sg/dns-query|:heavy_check_mark:|
| **Others**
| [@null31](https://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | :heavy_check_mark: | Based in Brazil / doh-server (nginx - unbound) / dot-server (unbound) / DNSSEC / QNAME minimization / Uncensored / no logging, no ECS, hosted on Oracle Cloud VPS by [null31](https://gitlab.com/null31/DoT-DoH-public-config). |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query | :heavy_check_mark: | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), Unbound with DNSSEC, No ECS, and No logs|


*: Tested via `curl --doh-url <RESOLVER_URI> http://google.com`.

Download a recent snapshot of the above list as JSON from [here](https://github.com/cslev/encrypted_dns_resolvers).

# Private DNS Server with DoH setup examples
| Base | Source | Comment |
|-------------|----------|---------|
| Docker | https://github.com/satishweb/docker-doh | Complete Docker stack using Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) and [Docker Flow Proxy](https://github.com/docker-flow/docker-flow-proxy)
| Docker | https://github.com/coolquasar/dnsproxy | Complete DoH, DoT, and DoQ stack in docker based on Adguard home dnsproxy project. Could host DoH, DoT and DoQ quickly in a cloud server, and run respective clients in local Docker env. It has been tested in Raspberry PI as well

# Supported in browsers and clients

|Name|Version|Comments|
|----|-------|----|
|Firefox|62| [Firefox DNS-over-HTTPS](https://support.mozilla.org/en-US/kb/dns-over-https#w_configure-doh-protection-settings) |
|[Bromite](https://www.bromite.org/)|67.0.3396.88|[How to enable DoH](https://github.com/bromite/bromite/wiki/Enabling-DNS-over-HTTPS)|
|curl| 7.62.0 | See [DOH-implementation](DOH-implementation) |
|[OkHttp](https://github.com/square/okhttp/tree/master/okhttp-dnsoverhttps)| 3.11 | See [Providers](https://github.com/square/okhttp/blob/master/okhttp-dnsoverhttps/src/test/java/okhttp3/dnsoverhttps/DohProviders.java) |
| [curl-doh](https://github.com/curl/doh) | n/a | basic stand-alone DoH client that uses curl |
| Chrome | 66 | https://support.google.com/chrome/answer/10468685#zippy=%2Cuse-a-secure-connection-to-look-up-sites-ip-addresses |
| Windows | 11 | https://learn.microsoft.com/en-us/windows-server/networking/dns/doh-client-support |
| iOS & macOS | iOS 14 & macOS 11 | https://dns.notjakob.com/ | 
| Android || [Intra](https://github.com/Jigsaw-Code/Intra) & [Nebulo](https://github.com/Ch4t4r/Nebulo)

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
|[FDNS](https://github.com/netblue30/fdns)|netblue30|Firejail DNS-over-HTTPS Proxy Server|
|[godnsbench](https://github.com/ameshkov/godnsbench) | Andrey Meshkov | Benchmark DoH, Do53, DoT and DoQ servers.
|[h2odoh](https://github.com/xm74/h2odoh)|Max Kostikov| an implementation with H2O HTTP/2 server using embedded mruby.|
|[Intra](https://github.com/Jigsaw-Code/Intra) | Jigsaw | DoH client for Android
|[jDnsProxy](https://github.com/moparisthebest/jDnsProxy)|Travis Burtrum| DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)|
|[kdig](https://gitlab.nic.cz/knot/knot-dns)|CZ.NIC|Utility that sends one or more DNS queries to a nameserver. Each query can have individual settings, or it can be specified globally via common settings, which must precede query specification. This utility supports DoH.
|[Nebulo](https://github.com/Ch4t4r/Nebulo) | [Daniel Wolf](https://github.com/Ch4t4r) | DoH client for Android
|[nss-tls](https://github.com/dimkr/nss-tls)|Dima Krasner| a daemon that makes gethostbyname(), getaddrinfo(), etc. happen through DoH, without any change to applications, thus transparently migrating all applications that don't use their own resolver (like some browsers) from DNS to DoH.|
|[quart-doh](https://github.com/treussart/quart-doh)|Matthieu Treussart| HTTP/2 server who serves a DOH proxy written in Python, with [Quart](https://pgjones.gitlab.io/quart/index.html) Python web microframework.|
|[RouteDNS](https://github.com/folbricht/routedns)|Frank Olbricht| a flexible stub resolver, proxy, and router with support for DoH, DoT, and plain DNS written in Go.|
|[serverless-dns](https://github.com/serverless-dns/serverless-dns)|[RethinkDNS](https://rethinkdns.com/)| Host your own RethinkDNS instance on Cloudflare Worker, support customizable filter from URL parameter
|[Technitium DNS Server](https://github.com/TechnitiumSoftware/DnsServer)|Technitium|A FOSS, cross-platform DNS Server written in C# that can consume as well as host DNS-over-HTTPS (DoH) and DNS-over-TLS (DoT) services.
# Other

* [Script to parse DoH provider URLs from this wiki page](https://gist.github.com/kimbo/dd65d539970e3a28a10628f15398247b)
* [DNSCrypt.info: Interactive list of public DNS servers:](https://dnscrypt.info/public-servers/)