# DoH - DNS over HTTPS

DoH queries resolve over HTTPS for privacy, performance, and security. DoH also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Working*| Comment** |
|-------------|----------|---------|---------|
| **A**
|[ABD](https://abd.ong/)|https://adguard.abd.ong/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream with malware filtering. Also support DoT & DoQ
|[Absolight](https://www.absolight.fr/)|https://resolver1.absolight.net/dns-query<br>https://resolver2.absolight.net/dns-query<br>https://resolver3.absolight.net/dns-query|:heavy_check_mark:|Also support DoT
|[AdFilter](https://adfilter.net/)|Perth: https://per.adfilter.net/dns-query<br>Sydney: https://syd.adfilter.net/dns-query<br>Adelaide: https://adl.adfilter.net/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking, aggregated statistics kept for 30 days. Also support DoT
|adfiltro.fun|https://adfiltro.fun/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream. Also support DoT & DoQ
|Adfreedns|https://adfreedns.top/dns-query|:heavy_check_mark:|Adblocking. Also support DoT & DoQ
| [AdGuard](https://adguard-dns.io/en/public-dns.html)     | Default: https://dns.adguard-dns.com/dns-query <br> Family protection: https://family.adguard-dns.com/dns-query <br> Uncensored: https://unfiltered.adguard-dns.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: <br> :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. DNSSEC enabled and TLS 1.3. Also support DoT & DoQ | 
|aerodrorne|https://aerodrorne.vip/dns-query|:heavy_check_mark:|
|affcdn.net|https://affcdn.net/dns-query|:heavy_check_mark:|
|affsoft.cc|https://affsoft.cc/dns-query|:heavy_check_mark:|
|[AhaDNS Blitz](https://ahadns.com/blitz/)| Uncensored : https://blitz.ahadns.com <br> OISD filter : https://blitz.ahadns.com/1:1 | :heavy_check_mark: <br> :heavy_check_mark:| [Customizable](https://blitz-setup.ahadns.com/) globally distributed DoH-only server with no logging |
| [AhaDNS](https://ahadns.com) | Netherland:<br> https://doh.nl.ahadns.net/dns-query | :heavy_check_mark: | Also support DoT through `dot.nl.ahadns.net`. Deprecated in favor of AhaDNS Blitz |
|[Ahoj Mail](https://ahoj.email) |https://ahoj.email/dns-query|:heavy_check_mark:|
|[Alan Pearce](https://alanpearce.eu)|https://dns.alanpearce.eu/dns-query|:heavy_check_mark:|Also support DoT
|[AliDNS](https://alidns.com)|https://dns.alidns.com/dns-query|:heavy_check_mark:|Also support DoT & DoQ
|[André Kelpe](https://kel.pe)|https://doh.kel.pe|:heavy_check_mark:|Block ads, also support DoT
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/)), also support DoT|
|[Angry.im](https://angry.im)|https://doh.angry.im/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, OpenNIC
| [Anudeep](https://anudeep.me) | https://secure.anudeep.me/dns-query | :heavy_check_mark: | Adblocking, use Cloudflare upstream and AdGuard browsing security web service, also support DoT
|[Apollinaria](https://hypercute.eu/)|https://dns.hypercute.eu/dns-query| :heavy_check_mark: |Use Cloudflare upstream, also support DoT
|applewebkit.dev|https://dns.applewebkit.dev/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, also support DoT
|[arnor.org](https://arnor.org)|https://nsec.arnor.org/dns-query|:heavy_check_mark:|Block ads, support DoT & DoQ
| [Artikel10](https://dns.artikel10.org/) | https://dns.artikel10.org/dns-query | :heavy_check_mark: | Non-logging service based in Germany, also support DoT
|aslk685qwda.com|https://dns.aslk685qwda.com/dns-query|:heavy_check_mark:|
|Asteri Moon|https://dns.asterimoon.com/dns-query| :heavy_check_mark: | Adblocking, also support DoT
|att.net|https://dohtrial.att.net|:heavy_check_mark:|Also support DoT
| [Awan.ftp.sh](https://awan.ftp.sh/) | Ads and gambling blocking : https://awan.ftp.sh/dns-query <br> Ads, gambling, drug, tobacco block : https://awan.ftp.sh/no-vice <br> Porn, ads, gambling, drug, tobacco block : https://awan.ftp.sh/noporn-cl <br> Unblocked : https://awan.ftp.sh/unblocked | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Japan, use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service. Also support DoT & DoQ
|ayasesayuki.shop|https://ayasesayuki.shop/dns-query|:heavy_check_mark:|Block ads & gambling, also support DoT & DoQ
|a47.me|https://dns.a47.me/dns-query|:heavy_check_mark:|
| **B**
|backschues.net|https://dns.backschues.net/dns-query|:heavy_check_mark:|Block ads, also support DoT
|bahopir188.dnshome.de|https://bahopir188.dnshome.de/dns-query|:heavy_check_mark:|Block ads, also support DoT
|baishiyuan.cn|https://dns.baishiyuan.cn/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream, also support DoT
|bazooki-infra.dev|https://bazooki-infra.dev/dns-query|:heavy_check_mark:|
|[BebasDNS](https://github.com/bebasid/bebasdns/blob/main/README.en.md)|https://dns.bebasid.com/dns-query|:heavy_check_mark:|Block ads, also support DoT
|[Belnet](https://dns.belnet.be)|https://dns.belnet.be/dns-query|:heavy_check_mark:|
|[Ben Hocking](https://bmwhocking.com)|https://dns.bmwhocking.com/dns-query|:heavy_check_mark:|
|[Benoît](https://benoit.jp.net) |https://dns.benoit.jp.net/dns-query|:heavy_check_mark:|Block ads & porn, use AdGuard parental control web service, also support DoT
|bermeitinger.eu|https://dns.bermeitinger.eu/dns-query|:heavy_check_mark:|Block ads, also support DoT
|bestwon203.com|https://bestwon203.com/dns-query|:heavy_check_mark:|
| Bitdefender | https://dns.bitdefender.net/dns-query | :heavy_check_mark: |Also support DoT
|[BITServices](https://www.bitservices.io/)|https://dns.bitservices.io/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream, also support DoT & DoQ
|biying.flymlc.com|https://biying.flymlc.com/dns-query|:heavy_check_mark:|Block ads
|[Blahdns](https://blahdns.com)|Germany: https://doh-de.blahdns.com/dns-query<br>Singapore: https://doh-sg.blahdns.com/dns-query|:heavy_check_mark:|Block ads, non-logging, no ECS, DNSSEC ready, support OpenNIC & ENS, also support DoT
|[BlissDNS](https://blissdns.net)|https://us1.blissdns.net/dns-query|:heavy_check_mark:|Block ads, also support DoT & DoQ
|[Blogs SL](https://blogssl.com) |https://adguard.blogssl.com/dns-query|:heavy_check_mark:|
| [Blokada DNS](https://community.blokada.org/t/the-benefits-of-blokada-dns/6646) | https://dns.blokada.org/dns-query | :heavy_check_mark: | No logging, also support DoT
|[Blue Mountain](https://linngde.com)|https://doh.linngde.com/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|[Blue Shield Umbrella](https://blue-shield.at)|https://rfree1.blue-shield.at/dns-query<br>https://rfree2.blue-shield.at/dns-query|:heavy_check_mark:|Also support DoT
|bonis.de|https://adguard.bonis.de/dns-query|:heavy_check_mark:|Use AdGuard browsing security web service, also support DoT
| [Brahma World](https://dns.brahma.world/home.html) | https://dns.brahma.world/dns-query | :heavy_check_mark: | No logging • Blocks Ads + Trackers + Malware + Phishing domains, DNSSEC ready • QNAME Minimization • No EDNS Client-Subnet • Also support DoT
|[Bravoc.one](https://bravoc.one/en/)|https://dns.bravoc.one/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, AdGuard browsing security web service
|[Brian Wee](https://dns.brian-wee.com) |https://dns.brian-wee.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, also support DoT & DoQ 
|[BT](https://bt.com)|https://doh.bt.com|:heavy_check_mark:|
|bth.dance|https://bth.dance/dns-query|:heavy_check_mark:|Block ads
|bugz.fr|https://stratus.bugz.fr/dns-query|:heavy_check_mark:|Ad & porn blocking, use AdGuard browsing security and parental control web service, also support DoT & DoQ
|[bunny.net](https://bunny.net/)|https://doh1.b-cdn.net/dns-query|:heavy_check_mark:|
|[busold.ws](https://busold.ws)|https://dns.busold.ws/dns-query|:heavy_check_mark:|Block ads, also support DoT
|b612.me|https://dns.b612.me/dns-query|:heavy_check_mark:|Use Cloudflare upstream, also support DoT
| **C**
|[Canarypwn](https://aaaab3n.moe/networks) | https://doh.aaaab3n.moe/dns-query-114514 | :heavy_check_mark: | Use Cloudflare upstream
|[Carestyle](https://console.carestyle.org)|https://console.carestyle.org/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|carter.me|https://dns.carter.me/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
|catdns.org|https://catdns.org/dns-query|:heavy_check_mark:|
|[CERT Estonia](https://www.ria.ee/en/news/application-developed-cert-ee-protects-against-phishing-and-malware)|https://dns.cert.ee/dns-query|:heavy_check_mark:|Block phishing, malware, porn & gambling
|cfdjb.org|https://cfdjb.org/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream, AdGuard browsing security and parental control web service
|[Charter](https://corporate.charter.com/)|https://doh-01.spectrum.com/dns-query<br>https://doh-02.spectrum.com/dns-query|:heavy_check_mark:|
|[chenu.ch](https://chenu.ch/)|https://dns.chenu.ch/dns-query|:heavy_check_mark:|Adblocking
|[chrisdooks](https://dooks.uk)|https://dns.dooks.uk/dns-query|:heavy_check_mark:|Block ads
|[Christer Warén](https://christerwaren.fi) |https://dns.christerwaren.fi|:heavy_check_mark:|
|chriswservers.com|https://dns.chriswservers.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare and ControlD upstream
|cicitt.ch|https://c.cicitt.ch/dns-query|:heavy_check_mark:|Block ads
|cippapp.com|https://doh.cippapp.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: <br>https://private.canadianshield.cira.ca/dns-query <br> Protected: <br>https://protected.canadianshield.cira.ca/dns-query <br> Family: <br>https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
| [CIRCL](https://www.circl.lu/) | https://dns.circl.lu/dns-query  | :heavy_check_mark:| Adblocking
| [Cisco Umbrella (OpenDNS)](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query <br> Umbrella: https://doh.umbrella.com/dns-query | :heavy_check_mark: <br>:heavy_check_mark:<br> :heavy_check_mark:| DNSSEC, Anycast
| [CleanBrowsing](https://cleanbrowsing.org/help/docs/dnsoverhttps/) | https://doh.cleanbrowsing.org/doh/family-filter/ <br><br> Filter that allows some mixed-content sites: https://doh.cleanbrowsing.org/doh/adult-filter/ <br><br> Malware blocking only: https://doh.cleanbrowsing.org/doh/security-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br><br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br><br> Block Malware: https://security.cloudflare-dns.com/dns-query <br><br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br><br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports both -04 and -13 content-types
|comff.net|https://dns.comff.net/dns-query|:heavy_check_mark:|Block ads
|[Comss](https://www.comss.ru/)|https://dns.comss.one/dns-query|:heavy_check_mark:|Block ads
|contentwritingservice.tech|https://contentwritingservice.tech/dns-query|:heavy_check_mark:|
| [Control D](https://controld.com/free-dns) | Unfiltered: <br> https://freedns.controld.com/p0 <br> Malware (Block Malware): <br> https://freedns.controld.com/p1 <br> Ads & Tracking (Block Malware + Ads & Tracking): <br> https://freedns.controld.com/p2 <br> Social (Block Malware + Ads & Tracking + Social Networks): <br> https://freedns.controld.com/p3 <br> Family Friendly (Block Malware + Ads & Tracking + Adult Content + Drugs): <br> https://freedns.controld.com/family <br> Uncensored (Unblock censored domains from various countries) <br> https://freedns.controld.com/uncensored <br><br> - 3rd Party Filters - <br><br> OISD - Full: <br> https://freedns.controld.com/x-oisd <br> OISD - Basic: <br> https://freedns.controld.com/x-oisd-basic <br> StevenBlack Unified: <br> https://freedns.controld.com/x-stevenblack <br> Dev Dan's Hosts: <br> https://freedns.controld.com/x-devdan <br> 1Hosts - Mini: <br> https://freedns.controld.com/x-1hosts-mini <br> 1Hosts - Lite: <br> https://freedns.controld.com/x-1hosts-lite <br> 1Hosts - Pro: <br> https://freedns.controld.com/x-1hosts-pro <br> Hagezi's DNS - Light <br> https://freedns.controld.com/x-hagezi-light <br> Hagezi's DNS - Normal: <br> https://freedns.controld.com/x-hagezi-normal <br> Hagezi's DNS - Pro: <br> https://freedns.controld.com/x-hagezi-pro <br> Hagezi's DNS - Pro Plus: <br> https://freedns.controld.com/x-hagezi-proplus <br> Hagezi's DNS - Ultimate: <br> https://freedns.controld.com/x-hagezi-ultimate <br> Hagezi's DNS - TIF (Threat Intelligence Feeds) <br> https://freedns.controld.com/x-hagezi-tif <br> GoodbyeAds: <br> https://freedns.controld.com/x-goodbyeads <br> AdGuard Filter: <br> https://freedns.controld.com/x-adguard <br> | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | ControlD is a fully customizable anycast DNS service that allows you to not only block annoyances like malware, tracking, ads, IoT telemetry, and more but also unblock over 180 services through a network of proxies in over 100 cities.
|cornes.me|https://doh.cornes.me/dns-query|:heavy_check_mark:|Block ads
|[Cooluc's DNS](https://dns.cooluc.com)|Non-filtering: https://dns.cooluc.com/dns-query<br>Adblocking: https://dns.cooluc.com/dns-query-ad|:heavy_check_mark:|
|criena.net|https://dns.criena.net/dns-query|:heavy_check_mark:|
|csa-rz.de|https://dns.csa-rz.de/dns-query|:heavy_check_mark:|
|[CubeDNS](https://cubedns.com/)|https://cubedns.com/dns-query|:heavy_check_mark:|
|[CynthiaLabs](https://cynthialabs.net/dns/)|https://dns.cynthialabs.net/dns-query|:heavy_check_mark:|Adblocking
| [CZ.NIC](https://www.nic.cz/odvr/) | https://odvr.nic.cz/dns-query | :heavy_check_mark:| Runs on [Knot Resolver](https://www.knot-resolver.cz/) (`doh2`), supports DNSSEC, provided by `.cz` TLD operator
| **D**
| [Danielle McLean](https://00dani.me/) | https://ns.00dani.me/dns-query | :heavy_check_mark: |
|dantynes.cyou|https://adguard.dantynes.cyou/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| [data.haus](https://data.haus/) | https://ns.data.haus/dns-query | :heavy_check_mark: | Adblocking, non-logging
|ddasdka678asdsa.com|https://dns.ddasdka678asdsa.com/dns-query|:heavy_check_mark:|
|delegated-ipfs.dev|https://delegated-ipfs.dev/dns-query|:heavy_check_mark:| Also resolves ENS domain, use Cloudflare upstream
|[denypradana.com](https://doh.denypradana.com)|https://doh.denypradana.com/dns-query|:heavy_check_mark:|
|[derailer](https://olpploiopkuyhiopsfrt.info) |https://dns.olpploiopkuyhiopsfrt.info/dns-query|:heavy_check_mark:|
|dev-umbrellagov|https://dns.dev-umbrellagov.com/dns-query| :heavy_check_mark: | 
|[Dict Xiong](https://beardic.cn) |https://dns.beardic.cn/dns-query|:heavy_check_mark:|
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/dns/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
|dilli.dev|https://eka.dilli.dev/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| Disconnect.app | https://doh.disconnect.app/dns-query | :heavy_check_mark: | Use Cloudflare upstream
| [dns.digitalsize.net](https://dns.digitalsize.net/) | https://dns.digitalsize.net/dns-query | :heavy_check_mark: | A public, non-tracking, non-filtering DNS resolver with DNSSEC enabled and hosted in Germany |
|dns.expert|https://dns.expert/dns-query| :heavy_check_mark: |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query <br> https://doh.sb/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| DNSSEC & QNAME minimization enabled, no logging |
| [dns0.eu](https://www.dns0.eu/) | Non-blocking: https://open.dns0.eu<br>Malware blocking: https://dns0.eu<br>Hardened security: https://zero.dns0.eu<br>Child safe: https://kids.dns0.eu | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Non-logging, GDPR compliant
|[DNS4all](https://dns4all.eu/)|https://doh.dns4all.eu/dns-query|:heavy_check_mark:| Non-logging
|[dns4me](https://dns4me.net)|https://ca01.dns4me.net<br>https://ca02.dns4me.net<br>https://us01.dns4me.net<br>https://us02.dns4me.net<br>https://sg01.dns4me.net<br>https://sa01.dns4me.net<br>https://au01.dns4me.net<br>https://au02.dns4me.net<br>https://uk01.dns4me.net<br>https://nz01.dns4me.net<br>https://ie01.dns4me.net<br>https://de01.dns4me.net<br>https://jp01.dns4me.net|:heavy_check_mark:|
| [dnscry.pt](https://www.dnscry.pt/) |Allentown, US: https://abe01.dnscry.pt/dns-query<br>Amsterdam, Netherlands: https://ams01.dnscry.pt/dns-query<br>Ashburn, US: https://abn01.dnscry.pt/dns-query<br>Athens, Greece: https://ath01.dnscry.pt/dns-query<br>Atlanta, US: https://atl01.dnscry.pt/dns-query<br>Bratislava, Slovakia: https://bts01.dnscry.pt/dns-query<br>Chicago, US: https://ord01.dnscry.pt/dns-query<br>Chișinău, Moldova: https://kiv01.dnscry.pt/dns-query<br>Coeur d'Alene, US: https://coe01.dnscry.pt/dns-query<br>Copenhagen, Norway: https://cph01.dnscry.pt/dns-query<br>Coventry, UK: https://cvt01.dnscry.pt/dns-query<br>Dallas, US: https://dfw02.dnscry.pt/dns-query<br>Denver, US: https://den01.dnscry.pt/dns-query<br>Detroit, US: https://dtw01.dnscry.pt/dns-query<br>Dublin, Ireland: https://dub01.dnscry.pt/dns-query<br>Durham, US: https://rdu01.dnscry.pt/dns-query<br>Düsseldorf, Germany: https://dus01.dnscry.pt/dns-query<br>Ebène, Mauritius: https://mru01.dnscry.pt/dns-query<br>Eygelshoven, Netherlands: https://eyg01.dnscry.pt/dns-query<br>Flint, US: https://fnt01.dnscry.pt/dns-query<br>Frankfurt, Germany: https://fra01.dnscry.pt/dns-query<br>Fremont, US: https://fet01.dnscry.pt/dns-query<br>Fujairah, UAE: https://fjr01.dnscry.pt/dns-query<br>Geneva, Switzerland: https://gva01.dnscry.pt/dns-query<br>Hanoi, Vietnam: https://han01.dnscry.pt/dns-query<br>Helsinki, Finland: https://hel01.dnscry.pt/dns-query<br>Ho-Chi-Minh City, Vietnam: https://sgn01.dnscry.pt/dns-query<br> Hong Kong: https://hkg02.dnscry.pt/dns-query<br>Istanbul, Turkey: https://ist01.dnscry.pt/dns-query<br>Jakarta, Indonesia: https://jkt01.dnscry.pt/dns-query<br>Kharkiv, Ukraine: https://hrk01.dnscry.pt/dns-query<br>Las Vegas, US: https://las01.dnscry.pt/dns-query<br>Liberty Lake, US: https://llk01.dnscry.pt/dns-query<br>Lima, Colombia: https://lim01.dnscry.pt/dns-query<br>London, UK: https://lon01.dnscry.pt/dns-query<br>Los Angeles Webhosting24, US: https://lax01.dnscry.pt/dns-query<br>Los Angeles CrownCloud, US: https://lax02.dnscry.pt/dns-query<br>Madrid, Spain: https://mad01.dnscry.pt/dns-query<br>Miami, US: https://mia01.dnscry.pt/dns-query<br>Milan, Italy: https://mil01.dnscry.pt/dns-query<br>Mumbai, India: https://bom01.dnscry.pt/dns-query<br>Munich, Germany: https://muc01.dnscry.pt/dns-query<br>New York, US: https://nyc01.dnscry.pt/dns-query<br>Nuremberg, Germany: https://nue01.dnscry.pt/dns-query<br>Oradea, Romania: https://omr01.dnscry.pt/dns-query<br>Paris, France: https://par01.dnscry.pt/dns-query<br>Philadelphia, US: https://phl01.dnscry.pt/dns-query<br>Phoenix, US: https://phx01.dnscry.pt/dns-query<br>Portland, US: https://pdx01.dnscry.pt/dns-query<br>Salt Lake City, US: https://slc01.dnscry.pt/dns-query<br>Sandefjord, Norway: https://trf01.dnscry.pt/dns-query<br>Santa Clara, US: https://sjc01.dnscry.pt/dns-query<br>São Paulo, Brazil: https://gru01.dnscry.pt/dns-query<br>Seattle, US: https://sea01.dnscry.pt/dns-query<br>Singapore Kuroit: https://sin03.dnscry.pt/dns-query<br>Singapore WebHorizon: https://sin02.dnscry.pt/dns-query<br>Sofia: https://sof01.dnscry.pt/dns-query<br>Spokane, US: https://geg01.dnscry.pt/dns-query<br>Stockholm, Sweden: https://sto01.dnscry.pt/dns-query<br>Sydney, Australia: https://syd01.dnscry.pt/dns-query<br>Tallinn, Estonia: https://tll01.dnscry.pt/dns-query<br>Tampa, US: https://tpa01.dnscry.pt/dns-query<br>Taos, US: https://tsm01.dnscry.pt/dns-query<br>Tokyo, Japan: https://tyo02.dnscry.pt/dns-query<br>Toronto, Canada: https://yyz01.dnscry.pt/dns-query<br>Vancouver, Canada: https://yvr01.dnscry.pt/dns-query<br>Vienna, Austria: https://vie01.dnscry.pt/dns-query<br>Vilnius, Lithuania: https://vno01.dnscry.pt/dns-query<br>Warsaw, Poland: https://waw02.dnscry.pt/dns-query| :heavy_check_mark:| Support IPv4+IPv6, uncensored, unfiltered, encrypted, DNSSEC, no logging.
|[dnscrypt.ca](https://dnscrypt.ca/)|https://dns1.dnscrypt.ca/dns-query|:heavy_check_mark:|
| [dnsforge.de](https://dnsforge.de/) | Adblocking : https://dnsforge.de/dns-query <br> Ads and pornblocking : https://clean.dnsforge.de/dns-query |:heavy_check_mark:<br>:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|Use AdGuard browsing security and parental control web service
|[dnsHome.de](https://www.dnshome.de/doh-dot-public-resolver.php)|https://dns.dnshome.de/dns-query|:heavy_check_mark:|
| [dnslow.me](https://dnslow.me/) | https://dnslow.me/dns-query | :heavy_check_mark: | A protective DNS that blocks Ads, Malware, Trackers, Phishing and Newly Registered Domains. Randomly forward requests to different upstreams for enhanced privacy. |
| [DNSPod](https://docs.dnspod.cn/public-dns/dot-doh/) | https://dns.pub/dns-query | :heavy_check_mark: | Operated by Tencent Cloud
| [dnswarden](https://dnswarden.com)| Adblock - <br> https://dns.dnswarden.com/adblock <br><br> Uncensored -<br> https://dns.dnswarden.com/uncensored <br><br> AdultFilter - <br>  https://dns.dnswarden.com/adultfilter | <br>:heavy_check_mark:<br><br><br> :heavy_check_mark:<br><br><br>:heavy_check_mark: | A zero logging DNS with support for DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) & Dnscrypt. Supports DNSSEC, TLS 1.3, QNAME minimization, OpenNIC and does own Recursion. EDNS Client Subnet is disabled.<br> Provides 4 different types of filtering options.<br> Adblock - Blocks ads, trackers, viruses, and telemetry.<br> Adultfilter - Blocks adult content, enforces safe search, and includes all the features from adblock. <br> Uncensored - Unrestricted access/no filtering.<br>[Custom Filter](https://dnswarden.com/customfilter.html) where you can choose your own filter lists! <br>For more information look [here](https://github.com/bhanupratapys/dnswarden) or [here](https://dnswarden.com). |
|doh.beauty|https://doh.beauty|:heavy_check_mark:|
|doh.best|https://doh.best/dns-query|:heavy_check_mark:|Adblocking
|doh.buzz|https://doh.buzz/dns-query|:heavy_check_mark:|
|doh.pink|https://doh.pink/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|doh.xyz|https://doh.xyz/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|[Dom!nic](https://dom1nic.eu/)|https://3dns.eu/dns-query|:heavy_check_mark:|
|[domreg.lt](https://domreg.lt)|https://doh.domreg.lt/dns-query|:heavy_check_mark:|Block porn & gambling
|[DoTLS](https://dotls.org/)|https://ns1.dotls.org|:heavy_check_mark:|Block ads
|dshubham.xyz|https://agh.dshubham.xyz/dns-query|:heavy_check_mark:|Block ads
| [Dukun.de](https://dukun.de/) |https://dukun.de/dns-query | :heavy_check_mark: |
|[duröhre.de](https://xn--durhre-yxa.de)|https://xn--durhre-yxa.de/dns-query|:heavy_check_mark:|
|d96.info|https://dns.d96.info/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| **E**
|easez.net|https://adguard.easez.net/dns-query|:heavy_check_mark:|Block ads
|[EasyMosdns](https://doh.apad.pro/)|https://doh.apad.pro/dns-query|:heavy_check_mark:|
|[EDDI](https://eddi.net)|https://doh.eddi.net/dns-query|:heavy_check_mark:|Block ads
| [Edgy DNS](https://edgy.network/dns) | https://edgy-dns.com/dns-query | :heavy_check_mark: | Adblocking
|edison42.dev|https://dns.edison42.dev/dns-query|:heavy_check_mark:|Block ads
|editechstudio|https://dns.editechstudio.com/dns-query|:heavy_check_mark:|Block ads & gambling
|[Egor Glukhikh](https://henek.ovh/)|https://dns.henek.ovh/dns-query|:heavy_check_mark:|Adblocking
|elbschloss.xyz|https://hole.elbschloss.xyz/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|eliatofani.ovh|https://eliatofani.ovh/dns-query|:heavy_check_mark:|Block ads
|[ELIV DNS](https://dns.eliv.kr)|https://dns.eliv.kr/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, Fast Cloudflare (priority IP) connection
| [Emiliyan Parvanov](https://emiliyan.com/) | https://dns.emiliyan.com/dns-query | :heavy_check_mark: | Adblocking
|engineer.web.id|https://dns.engineer.web.id/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|eren.homes|https://ad.eren.homes/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service 
|ero-sayhi.com|https://agh.ero-sayhi.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|esnube.es|https://dns.esnube.es/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[Etath SkyDragoness](https://skydragoness.com)|https://skydragoness.com/dns-query|:heavy_check_mark:|
|[EthLink](https://eth.link)|https://eth.link/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|excdn.eu.org|https://doh.excdn.eu.org|:heavy_check_mark:|Use Cloudflare upstream 
| **F**
|faked.org|https://dns.faked.org/dns-query|:heavy_check_mark:|Block ads
|familiamv.net|https://dnsvps.familiamv.net/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
| Fancyorg.at | https://dns.fancyorg.at/dns-query |  :heavy_check_mark: | Adblocking
|[FBI NICS E-Check](https://nicsezcheckfbi.gov) |https://nicsezcheckfbi.gov|:heavy_check_mark:| Use Cloudflare upstream with malware filtering 
| [FDN](https://www.fdn.fr/) - French Data Network | https://ns0.fdn.fr/dns-query <br> https://ns1.fdn.fr/dns-query |:heavy_check_mark:| No log, no filter, DNSSEC, … ([more informations in French](https://www.fdn.fr/ouverture-des-services-dot-doh/)) |
|[Feroz](https://padlock.argh.in/2019/07/11/dns-over-https.html)|https://doh.li/dns-query|:heavy_check_mark:|Use Cloudflare upstream
| [ffmuc.net](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, OpenNIC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
|[Fizz Studio](https://fizz.studio)|https://dns.fizz.studio/dns-query|:heavy_check_mark:|
|[Flight Space](https://flightspace.net) |https://dns.flightspace.net/dns-query|:heavy_check_mark:|
| [Foundation for Applied Privacy](https://applied-privacy.net/services/dns/) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198 |
| [Froth.zone](https://dns.froth.zone/resolver) | https://dns.froth.zone/dns-query | :heavy_check_mark: | OpenNIC
|frutuozo.com.br|https://adguard.frutuozo.com.br/dns-query|:heavy_check_mark:|Block ads
|fullaccesstointernet.jp.eu.org|https://dns.fullaccesstointernet.jp.eu.org/dns-query|:heavy_check_mark:|
|funil.de|https://doh.funil.de/dns-query|:heavy_check_mark:|
|[FutaDNS](https://site.futa.gg/)|https://doh.futa.gg/dns-query<br>https://doh.futa.app/dns-query|:heavy_check_mark:|Block ads
| **G**
|[Gamban](https://gamban.com/)|https://dns.gamban.com/dns-query|:heavy_check_mark:|
|gambini.org|https://adguard.gambini.org/dns-query|:heavy_check_mark:|Block ads
|[Gay Analysing](https://gayanalysing.co.uk) |https://dns.gayanalysing.co.uk/dns-query|:heavy_check_mark:|Block ads
|[Gensokyo](https://freyja.pw/)|https://dns.freyja.pw/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
|gifino.fr|https://adguard.maison.gifino.fr/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, and AdGuard browsing security web service
|[girino.org](https://girino.org)|https://dns.girino.org/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|gloom.nexus|https://agh.gloom.nexus/dns-query|:heavy_check_mark:|Block ads
| [Google](https://developers.google.com/speed/public-dns/docs/doh) | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query <br> https://8888.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Full RFC 8484 support, EDNS, DNSSEC, no filtering.
|[Gorgeous](https://so-gorgeo.us.kg/)|https://nana-is.so-gorgeo.us.kg/dns-query<br>https://tetty-is.so-gorgeo.us.kg/dns-query<br>https://luna-is.so-gorgeo.us.kg/dns-query|:heavy_check_mark:| Adblocking, use Cloudflare upstream with malware filtering and AdGuard browsing security web service
|[Guardio](https://guard.io/)|https://dns.guard.io/dns-query|:heavy_check_mark:|
| **H**
|[Hakase](https://haka.se)|https://dns.haka.se/dns-query|:heavy_check_mark:|Block ads
|hartley.cloud|https://adguard.hartley.cloud/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
|[HiNet](https://hinet.net)|https://dns.hinet.net/dns-query|:heavy_check_mark:|
|[Hongjun Li](https://lihj.me)|https://dns.lihj.me/dns-query|:heavy_check_mark:|Use Cloudflare upstream 
|huas.me|https://dns.huas.me/dns-query|:heavy_check_mark:|Block ads
| Huque | https://doth.huque.com/dns-query | :heavy_check_mark: | 
|[Hurricane Electric](https://forums.he.net/index.php?topic=3996.0)|https://ordns.he.net|:heavy_check_mark:|
|[h3zjp](https://h3z.jp)|https://dns.h3z.jp/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
| **I**
|[Ian ROCKS](https://blog.ian.rocks)|https://dns.ian.rocks/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream and AdGuard browsing security web service
|[ibksturm](https://github.com/ibksturm)|https://ibksturm.synology.me/dns-query|:heavy_check_mark:| OpenNIC
|ihctw.synology.me|https://ihctw.synology.me/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
|ikarosalpha.xyz|https://ikarosalpha.xyz/dns-query|:heavy_check_mark:|Adblocking and AdGuard browsing security web service
|[ikataruto](https://ikataruto.com)|https://dns.ikataruto.com/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|immanuelschaffer.de|https://dns.immanuelschaffer.de/dns-query|:heavy_check_mark:|Block ads
|[immerda.ch](https://docs.immerda.ch/de/services/doh/)|https://doh.immerda.ch/dns-query|:heavy_check_mark:|Block ads
| [In-Berlin](https://wiki.in-berlin.de/dns) | https://dns1.in-berlin.de/dns-query | :heavy_check_mark: |
|[Inclusio](https://inclusioproject.com)|https://dns.inclusioproject.com/dns-query|:heavy_check_mark:|
|indybanipal.com|https://dns.indybanipal.com/dns-query|:heavy_check_mark:|Ad & porn blocking, use AdGuard parental control web service
|[Inforlogia](https://inforlogia.com)|https://dns.inforlogia.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| [Institut national de recherche en sciences et technologies du numérique](https://www.inria.fr/fr) | https://qlf-doh.inria.fr/dns-query | :heavy_check_mark: |
| [Internet Initiative Japan](https://public.dns.iij.jp/) | https://public.dns.iij.jp/dns-query | :heavy_check_mark: | Planned to run until March 2027 
|[Inter-University Computation Center](https://iucc.ac.il/en/)|https://doh.iucc.ac.il/dns-query|:heavy_check_mark:|
|ionutl.ro|https://dns.cloud.ionutl.ro/dns-query|:heavy_check_mark:|Block ads
|[ipoac.nl](https://ipoac.nl)|https://dns.ipoac.nl/dns-query|:heavy_check_mark:|
|is.my.waifu.cz|https://megumin.is.my.waifu.cz/dns-query<br>https://darkness.is.my.waifu.cz/dns-query|:heavy_check_mark:|
|[Ivankin](https://ivnkn.xyz)|https://ivnkn.xyz/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|izapi4.fr|https://adguard.izapi4.fr/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
| **J**
|janl.eu|https://dns.janl.eu/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
|jhangy.us|https://dns.jhangy.us/dns-query|:heavy_check_mark:|Block ads & gambling, use Cloudflare upstream
|jichi.io|https://dns.jichi.io/dns-query|:heavy_check_mark:|Block ads
|jkdns.me|https://jkdns.me/dns-query|:heavy_check_mark:|Block ads
|johanliebert.top|https://adguard.johanliebert.top/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service 
|[Jupitr DNS](https://jupitrdns.com)|https://dns.jupitrdns.com/dns-query|:heavy_check_mark:|Block ads
|[Justin Counts](https://justincounts.com/)|https://ad.justincounts.com/dns-query|:heavy_check_mark:|Use AdGuard browsing security web service
| **K**
|kaiwu.xyz|https://kaiwu.xyz/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[Kamil Szczepański](https://kamilszczepanski.com/)|https://dns.kamilszczepanski.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, use AdGuard browsing security web service
|kapite.in|https://dns.kapite.in/dns-query|:heavy_check_mark:|Block ads & gambling, use Cloudflare upstream with malware filtering and AdGuard browsing security web service
|kawa.tf|https://dns.kawa.tf/dns-query|:heavy_check_mark:|OpenNIC, block ads
|Kerekes|https://dns.kerekes.xyz/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
|[Kernel Error](https://kernel-error.de)|https://dns.kernel-error.de/dns-query|:heavy_check_mark:| 
|[kescher](https://dns.kescher.at)|https://dns.kescher.at/dns-query|:heavy_check_mark:|DNSSEC-validating
|ketan.dev|https://pihole.aws.ketan.dev/dns-query|:heavy_check_mark:|Block ads
|[keviland](https://keviland.com) |https://dns.keviland.com/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|khon.dev|https://adg.khon.dev/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[Kidzonet](https://kidzonet.io)|https://doh.kidzonet.io/dns-query|:heavy_check_mark:|
|[Kishore](https://avdkishore.dev/)|https://adguard.avdkishore.dev/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|[Koala](https://koala.us.to)|https://dns.koala.us.to/dns-query|:heavy_check_mark:|Adblocking
|kooman|https://doh.kooman.org/dns-query|:heavy_check_mark:|
|Konikoni428|https://adguard.konikoni428.com/dns-query|:heavy_check_mark:|Adblocking
|konpetr6.site|https://konpetr6.site/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
|korzhyk.pp.ua|https://dns.korzhyk.pp.ua/dns-query|:heavy_check_mark:|Block ads
|[Kosan](https://kosan.moe)|https://dns.kosan.moe/dns-query|:heavy_check_mark:|Block ads
|kpsn.org|https://dart.kpsn.org/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|kugoapps|https://dns.kugoapps.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|kuuhaku.moe|https://dns.kuuhaku.moe/dns-query|:heavy_check_mark:| OpenNIC
|kyusang.win|https://agh.kyusang.win/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream, and AdGuard browsing security web service
| **L**
| [La Contre-Voie](https://lacontrevoie.fr/en/services/doh/) | https://doh.lacontrevoie.fr/dns-query | :heavy_check_mark: | Supports DNSSEC and IPv6, not logging queries' content, uses [unbound](https://github.com/NLnetLabs/unbound/). Commits for net neutrality, hosted in France.
|[Lars Lehmann](https://larsl.net/)|https://dns.lars-lehmann.net/dns-query|:heavy_check_mark:|
| [LavaDNS](https://dns.lavate.ch/) | Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in Finland. OpenNIC, no logging, no filtering, no ECS, DNSSEC support. |
|[Levonet](https://www.levonet.sk/)|https://dns.levonet.sk/dns-query|:heavy_check_mark:|
|[LibreDNS](https://libredns.gr/) | Non-filtering: https://doh.libredns.gr/dns-query <br> Adblocking: https://doh.libredns.gr/noads| :heavy_check_mark: <br> :heavy_check_mark: | Non-logging, OpenNIC.
| [Lindung](https://lindung.pp.ua/) | Adblocking: https://lindung.pp.ua/dns-query <br> Ad & porn blocking: https://lindung.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |Use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service
|[Liquid Intelligent Technologies](https://liquid.tech/)|https://africadns1.liquidtelecom.net/dns-query<br>https://africadns2.liquidtelecom.net/dns-query|:heavy_check_mark:|
|[Lista](https://lista.my.id/dns-lista-sudah-online-untuk-publik/)|https://dns.lista.my.id/dns-query|:heavy_check_mark:|Block ads
|loadlow.me|https://loadlow.me/dns-query|:heavy_check_mark:|
|[LobbyGod](https://lobbygod.com/)|https://dns.lobbygod.com/dns-query|:heavy_check_mark:|
|lothuscorp.com.br|https://dns1.lothuscorp.com.br/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| **M**
|maherhost.uk|https://maherhost.uk/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|maskab|https://doh.maskab.com/dns-query|:heavy_check_mark:|
| [Masters of Cloud](https://www.masters-of-cloud.de/) | https://masters-of-cloud.de/dns-query | :heavy_check_mark: | OpenNIC 
|mateo.ovh|https://dns.mateo.ovh/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream, AdGuard browsing security web service
|[Max Philipp Wriefdt](https://wriedts.de)|https://home.wriedts.de/dns-query|:heavy_check_mark:|Block ads & gambling
|[Mayx](https://mayx.eu.org)|https://dns.mayx.eu.org/dns-query|:heavy_check_mark:|
|[MC Host](https://mchost.no)|https://doh.serverhost.no/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream with malware filtering
|meddy94.de|https://adguard.meddy94.de/dns-query|:heavy_check_mark:|Adblocking
|mendozasdelivery.com|https://mendozasdelivery.com/dns-query|:heavy_check_mark:|
|[MERCURY](https://mtsoln.com/)|https://ns.mtsoln.com/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
|meshkov.info|https://testaghome.meshkov.info/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[Meta Dallin](https://dallinbryce.com)|https://dns.dallinbryce.com/dns-query|:heavy_check_mark:|
|mikeliu.org|https://dns.mikeliu.org/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[mikrotikrumahan](https://mikrotikrumahan.my.id/)|https://dns.mikrotikrumahan.my.id/dns-query|:heavy_check_mark:|Block ads
|mismat.ch|https://netcup.mismat.ch/dns-query|:heavy_check_mark:|Block ads
|mmmalia.com|https://doh.mmmalia.com/dns-query|:heavy_check_mark:|Block ads & porn, use AdGuard parental control web service
|mnet-online.de|https://dns.mnet-online.de/dns-query|:heavy_check_mark:|
|mnrv.trade|https://mnrv.trade/dns-query|:heavy_check_mark:|
|moderateinfra.net|https://nue2.moderateinfra.net/dns-query|:heavy_check_mark:|Block ads
|momokko.moe|https://naganohara-yoimiya.momokko.moe/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|mtoo.vip|https://dns.mtoo.vip/dns-query|:heavy_check_mark:|Block ads
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | Non-blocking https://dns.mullvad.net/dns-query <br> Adblocking https://adblock.dns.mullvad.net/dns-query <br> Ad & malware blocking https://base.dns.mullvad.net/dns-query <br> Ad, malware, social media blocking https://extended.dns.mullvad.net/dns-query <br> Ad, malware, social media, adult content and gamble blocking https://all.dns.mullvad.net/dns-query <br> Ad, malware, adult content and gamble blocking https://family.dns.mullvad.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Public DoH server in US, DE, GB, SG, and SE with QNAME minimization, audited by [Assured](https://www.assured.se/wp-content/uploads/2021/03/Assured_Mullvad_DoH_server_audit_report.pdf)
| [mydns.network](https://mydns.network) | Uncensored: https://freedom.mydns.network/dns-query <br> Paranoia (no Google/Cloudflare): https://paranoia.mydns.network/dns-query <br> Adblocking: https://adblock.mydns.network/dns-query <br> Family: https://family.mydns.network/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Public DoH server powered by Cloudflare Workers. Uniquely disguises your queries by relaying queries your behalf to upstream DoH servers with no IP address information. [Open source](https://github.com/matthewgall/doh-proxy), deploy your own instance at any time!
|my-private-cdn.com|https://my-private-cdn.com/dns-query|:heavy_check_mark:|
| **N**
|[nako.kr](https://nako.kr)|https://dns.nako.kr/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|narl.app|https://dns.narl.app/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
|nashkan.net|https://ae-fuj-w-p-1.nashkan.net/dns-query<br>https://ae-fuj-w-p-2.nashkan.net/dns-query<br>https://ae-fuj-w-p-3.nashkan.net/dns-query<br>https://at-wie-w-p-1.nashkan.net/dns-query<br>https://au-syd-w-f-1.nashkan.net/dns-query<br>https://au-syd-w-p-1.nashkan.net/dns-query<br>https://de-fra-w-p-1.nashkan.net/dns-query<br>https://de-fsn-w-p-1.nashkan.net/dns-query<br>https://fi-hel-w-f-2.nashkan.net/dns-query<br>https://fr-gra-w-f-1.nashkan.net/dns-query<br>https://fr-gra-w-p-1.nashkan.net/dns-query<br>https://gb-cov-w-f-1.nashkan.net/dns-query<br>https://gb-cov-w-p-1.nashkan.net/dns-query<br>https://gb-lon-w-f-1.nashkan.net/dns-query<br>https://gb-lon-w-p-1.nashkan.net/dns-query<br>https://gb-lon-w-p-2.nashkan.net/dns-query<br>https://jp-tyo-w-p-1.nashkan.net/dns-query<br>https://kz-pav-w-p-1.nashkan.net/dns-query<br>https://nl-dro-w-f-1.nashkan.net/dns-query<br>https://nl-dro-w-p-1.nashkan.net/dns-query<br>https://pl-waw-w-f-1.nashkan.net/dns-query<br>https://pl-waw-w-p-2.nashkan.net/dns-query<br>https://ro-buc-w-f-1.nashkan.net/dns-query<br>https://ro-buc-w-p-1.nashkan.net/dns-query<br>https://sg-w-f-1.nashkan.net/dns-query<br>https://sg-w-p-1.nashkan.net/dns-query<br>https://us-chi-w-f-1.nashkan.net/dns-query<br>https://us-chi-w-p-1.nashkan.net/dns-query<br>https://us-hil-w-f-1.nashkan.net/dns-query<br>https://us-hil-w-p-1.nashkan.net/dns-query<br>https://us-jac-w-f-1.nashkan.net/dns-query<br>https://us-jac-w-p-1.nashkan.net/dns-query<br>https://us-kan-w-f-1.nashkan.net/dns-query<br>https://us-kan-w-p-1.nashkan.net/dns-query<br>https://us-nyc-w-f-1.nashkan.net/dns-query<br>https://us-nyc-w-p-1.nashkan.net/dns-query<br>https://us-saj-w-f-1.nashkan.net/dns-query<br>https://us-saj-w-p-1.nashkan.net/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream with malware filtering
|nekomiya-sama.top|https://nekomiya-sama.top/dns-query|:heavy_check_mark:|Use Cloudflare upstream 
|[Neowutran](https://neowutran.ovh)|https://dns.neowutran.ovh|:heavy_check_mark:|
|[NetVPN](https://netvpn.net) |https://dns.netvpn.net/dns-query|:heavy_check_mark:|
| [NextDNS](https://nextdns.io) | https://dns.nextdns.io | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free with non-filtering afterward until the end of the month. Granular dashboard, Each account can create multiple configurations, which can be used for multiple devices with prefixes to track activities on the dashboard. [Create a config ID](https://my.nextdns.io/start)
|nhtsky|https://dns.nhtsky.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[Nick Slowinski](https://nick-slowinski.de)|https://dns.nick-slowinski.de/dns-query|:heavy_check_mark:|Block ads
| [NIC.LV](https://doh.lv/) | https://doh.lv/dns-query <br> https://doh.nic.lv/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run by .lv TLD registry 
|[Nico Franke](https://zernico.de)|https://adguard-kartoffel.zernico.de/dns-query|:heavy_check_mark:|
| [Nightly Moon](https://nightlymoon.us.kg/) | Adblocking https://nightlymoon.us.kg/dns-query <br> Adblocking & porn blocking https://nightlymoon.us.kg/family | :heavy_check_mark: <br> :heavy_check_mark: |Use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service
| [NiYaWe](https://www.niyawe.de/) | https://doh.niyawe.de/dns-query | :heavy_check_mark: |
| [Njalla](https://dns.njal.la/) | https://dns.njal.la/dns-query | :heavy_check_mark: | Non logging, based in Sweden
|[nonexiste.net](https://nonexiste.net)|https://kiri.nonexiste.net/dns-query|:heavy_check_mark:|Block porn & gambling
| [NordVPN](https://nordvpn.com)|https://dns1.nordvpn.com/dns-query <br> https://dns2.nordvpn.com/dns-query| :heavy_check_mark: |
|[Noridev](https://adblock.noridev.moe/html/dns_android.html) | https://1.dns.noridev.moe/dns-query<br>Cloudflare upstream with DNSSEC: https://2.dns.noridev.moe/dns-query |:heavy_check_mark:|Adblocking
|novali.date|https://dns.novali.date/dns-query|:heavy_check_mark:|Block ads
|novg.net|https://dns.novg.net/dns-query|:heavy_check_mark:|
|n23.io|https://dns.n23.io/dns-query|:heavy_check_ use Cloudflare upstream
| **O**
|[Odin](https://dns.odinpl.com)|https://dns.odinpl.com/dns-query|:heavy_check_mark:|Block ads
|ofdoom.net|https://dns.ofdoom.net/dns-query|:heavy_check_mark:|Block ads
|olgui.net|https://dns.olgui.net/dns-query|:heavy_check_mark:|Block ads
|oliviertv|https://dns.oliviertv.co.za/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream with malware filtering
|[OpenLoop](https://openloophealth.com/)|https://ag.apollohct.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[opennameserver.org](https://opennameserver.org)|Baden-Baden, Germany: https://ns1.opennameserver.org/dns-query<br>Sandefjord, Norway: https://ns4.opennameserver.org/dns-query|:heavy_check_mark:|DNSSEC enabled, non-logging, OpenNIC support
|ourvau.lt|https://dns.ourvau.lt/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|o0o.re|https://5g.o0o.re/dns-query|:heavy_check_mark:|Use Cloudflare upstream with DNSSEC
| **P**
| [PaesaDNS](https://milgradesec.github.io/paesadns/) | https://dns.paesa.es/dns-query | :heavy_check_mark: | Adblocking, non-logging, use Cloudflare upstream with malware filtering
|[PanSzelescik](https://panszelescik.pl)|https://dns.panszelescik.pl/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|pashagame456.com|https://pashagame456.com/dns-query|:heavy_check_mark:|
|[Paulo](https://paulo.nom.za)|https://paulo.nom.za/dns-query| :heavy_check_mark: | Adblocking, use Cloudflare upstream with malware filtering and AdGuard browsing security web service
|[Pavol Decky](https://decky.eu)|https://dns.decky.eu/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[pggns](https://pggns.de)|https://adguard.pggns.de/dns-query|:heavy_check_mark:|Block ads
|phillipjberry.net|https://dns.phillipjberry.net/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security and parental controlr web service
|pietjacobs.be|https://dns1.pietjacobs.be/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream with malware filtering
|[plan9-dns](https://github.com/jlongua/plan9-dns)|New Jersey: https://kronos.plan9-dns.com/dns-query<br>Mexico: https://helios.plan9-dns.com/dns-query<br>Florida: https://pluton.plan9-dns.com/dns-query|:heavy_check_mark:|
|[PlumeDNS](https://plumedns.com)|https://privacy.plumedns.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|pooblet.co.za|https://pooblet.co.za/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
|[PragmaSEC](https://pragmasec.nl/)|https://dns.pragmasec.nl/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
|princex.net|https://dns.princex.net/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[Privex](https://www.privex.io/articles/public-infra/#standard-dns-servers)|Germany: https://de.dns.privex.io<br>Netherlands: https://nl.dns.privex.io|:heavy_check_mark:|
|psociety.de|https://dns.psociety.de/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[Pubhole](https://pubhole.archuser.org/)|https://doh.archuser.org/dns-query|:heavy_check_mark:|Block ads, also resolves OpenNIC
|puregeni.us|https://dns-privacy.puregeni.us/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
| **Q**
|[Quadrant](https://quadrantsec.com/blog/quadrants-public-dns-resolver-tls-https-support)|https://doh.qis.io/dns-query|:heavy_check_mark:|
| [Quad9](https://quad9.net) | 9.9.9.9 (Secure): A threat-blocking, privacy-first recursive DNS service. <br> https://dns.quad9.net/dns-query <br><br> 9.9.9.10 (No Threat Blocking): For users who want to take advantage of privacy-first recursive DNS service, but do not want threat blocking. <br> https://dns10.quad9.net/dns-query <br><br> 9.9.9.11 (Secure + ECS): For users who do not route to the closest-possible Quad9 location, use 9.9.9.11 for better CDN performance. <br> https://dns11.quad9.net/dns-query <br><br> 9.9.9.12 (No Threat Blocking + ECS): For users who do not route to the closest-possible Quad9 location, and also do not want threat blocking, use 9.9.9.12 for better CDN performance. <br> https://dns12.quad9.net/dns-query | ✔️ <br> ✔️ <br> ✔️ <br> ✔️ | 9.9.9.9 - Malware blocking, DNSSEC validation <br> 9.9.9.10 - No malware blocking, no DNSSEC validation <br> 9.9.9.11 - Malware blocking, DNSSEC validation, ECS enabled <br> 9.9.9.12 - No malware blocking, no DNSSEC validation, ECS enabled
| **R**
|[Rabbit DNS](https://rabbitdns.org/install)|Non filtering: https://dns.rabbitdns.org/dns-query<br>Malware filtering: https://security.rabbitdns.org/dns-query<br>Malware and adult filtering: https://family.rabbitdns.org/dns-query|:heavy_check_mark:|Use Cloudflare upstream with malware and family filtering
|[RAL9005](https://ral9005.org/)|https://ns.ral9005.org/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
|redvau.lt|https://dns.redvau.lt/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|reitmeier.me|https://dns.reitmeier.me/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
|renardyre.com|https://dns.renardyre.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|reckoningslug.name|https://dns.reckoningslug.name/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|relskor.com|https://adguard.relskor.com/dns-query|:heavy_check_mark:|Block ads
|[repinger](https://dns.repinger.com)|https://dns.repinger.com/dns-query|:heavy_check_mark:|Block ads & gambling, use Cloudflare upstream
|[repomansd](https://falkenthal.org)|https://dns.falkenthal.org/dns-query|:heavy_check_mark:|
|[Restena](https://www.restena.lu/en/document/190-configuring-your-server-public-dns-resolver)|https://dnspub.restena.lu/dns-query|:heavy_check_mark:|DNSSEC validation
|[RetakeCS](https://retakecs.com/)|https://dns.retakecs.com/dns-query|:heavy_check_mark:|Adblocking, use AdGuard browsing security web service
| [RethinkDNS](https://www.rethinkdns.com/) | Non-filtering: https://sky.rethinkdns.com/dns-query <br> OISD: https://sky.rethinkdns.com/1:IAAgAA== | :heavy_check_mark: <br> :heavy_check_mark: | [An open-source stub resolver](https://github.com/serverless-dns/serverless-dns) running in 200+ locations world-wide on Cloudfare's network. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logs. [code](https://github.com/celzero/rethink-app). [Configure custom blocklists](https://rethinkdns.com/configure)
|rjls.me|https://dns.rjls.me/dns-query|:heavy_check_mark:|Block ads & porn, use AdGuard parental control web service
|[RobinGroppe.de](https://www.robingroppe.de/serverzeug/dns-server)|https://dns.rbn.gr/dns-query|:heavy_check_mark:| Malware blocking, DNSSEC validation
| [RoTunneling](https://www.rotunneling.net/rotunneling-doh-free/) | https://dns.rotunneling.net/dns-query/public | :heavy_check_mark: | Adblocking, use Cloudflare upstream with malware filtering
|[Ruby.ci](https://ruby.ci/)|https://adguard.ruby.ci/dns-query|:heavy_check_mark:|Adblocking
| **S**
| [SafeServe](https://www.namecheap.com/dns/free-public-dns/) | https://safeservedns.com/dns-query | :heavy_check_mark: | Operated by Namecheap
|sarak.as|https://dns.sarak.as/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service
|[Sari](https://sarilouis.com/)|https://dns.sarilouis.com/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|sec511.com|https://dns.sec511.com/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|senthil.us|https://adguard.senthil.us/dns-query|:heavy_check_mark:|Block ads & porn
|scarx.net|https://dns.scarx.net/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|sc-lezhi.com|https://ns1.sc-lezhi.com/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream and AdGuard browsing security web service
|scott-smith.us|https://dns.scott-smith.us/dns-query|:heavy_check_mark:|
|seiffert.me|https://dns.seiffert.me/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[sev.monster](https://dns.sev.monster)|https://dns.sev.monster/dns-query|:heavy_check_mark:|OpenNIC
|[Shaft Inc](https://www.shaftinc.fr/dns-shaftinc.html)|https://dns.shaftinc.fr/|:heavy_check_mark:|
|shareworx.net|https://dns.shareworx.net/dns-query|:heavy_check_mark:|
|[Sheggi](https://sheggi.ch/)|https://dns.sheggi.ch/dns-query|:heavy_check_mark:|Porn blocking, use Cloudflare upstream with malware and family filtering
|[Shimul](https://shimul.me)|https://dns.shimul.me/dns-query|:heavy_check_mark:|Block ads & gambling
|shoupperuser.com|https://adguard.shoupperuser.com/dns-query|:heavy_check_mark:|Ad & porn blocking, use AdGuard browsing security and parental control web service
|shutgaming.net|https://adguard.shutgaming.net/dns-query|:heavy_check_mark:|Adblocking
|silen.org|https://dns.silen.org/dns-query|:heavy_check_mark:|Block ads
|[sindominio.net](https://sindominio.net/ayuda/#dns-mediante-https)|https://dns.sindominio.net/dns-query|:heavy_check_mark:|
|siudzinski.net|https://adg.siudzinski.net/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|skrep.eu|https://dns.skrep.eu/dns-query|:heavy_check_mark:|OpenNIC, block ads
|[Silentlybren](https://silentlybren.com/)|https://dns.silentlybren.com/dns-query|:heavy_check_mark:|Adblocking
| Slinkyman.net | https://dns.slinkyman.net/dns-query | :heavy_check_mark: | Adblocking, use Cloudflare upstream
|[SmartGuard](https://www.smartguard.io/en#server)|https://dns.smartguard.io/dns-query|:heavy_check_mark:|Customizable policy and filtering
|[smilence](https://geili.me)|https://adg.geili.me/dns-query|:heavy_check_mark:|
|[spacedns.org](https://spacedns.org/index.html)| https://spacedns.org/dns-query | :heavy_check_mark: | Adblocking, hosted in Poland, use Cloudflare upstream
|[Sparsh Bajaj](https://sparshbajaj.me)|https://adguard.sparshbajaj.me/dns-query|:heavy_check_mark:|Block ads & gambling, use Cloudflare upstream
|[Startup Stack](https://startupstack.tech)|https://dns.startupstack.tech/dns-query|:heavy_check_mark:|
|[stevenz](https://www.stevenz.blog/dns/)|https://dns.stevenz.net/dns-query|:heavy_check_mark:|Block ads
|stirringphoto.com|https://dns.stirringphoto.com/dns-query|:heavy_check_mark:|
|[StuSta](https://www.stusta.de/en/)|https://muli.stusta.mhn.de/dns-query|:heavy_check_mark:|
|[suche.org](https://suche.org)|https://doh.suche.org/dns-query|:heavy_check_mark:|
|suhaila.dev|https://dns.suhaila.dev/dns-query|:heavy_check_mark:|Block ads
| [Sundalandia](https://sundalandia.pp.ua) | Adblock https://sundalandia.pp.ua/dns-query <br> Family filter https://sundalandia.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |Use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service
|[Sunet DNS](https://wiki.sunet.se/display/DNS/Sunet+DNS) | https://resolver.sunet.se/dns-query |:heavy_check_mark:|
|sunnygyl.com|https://sunnygyl.com/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
|superstefan.win|https://dns.superstefan.win/dns-query|:heavy_check_mark:|Adblocking, use Cloudflare upstream
|[Svoi](https://svoi.dev/)|https://dns.svoi.dev/dns-query| :heavy_check_mark: | 
|[Switch](https://www.switch.ch/en/switch-public-dns)|https://dns.switch.ch/dns-query|:heavy_check_mark:|Block porn & gambling
| [Syshero](https://syshero.org/) | https://doh.syshero.org/dns-query | :heavy_check_mark: |Use Cloudflare upstream
| **T**
| t53.de | https://dns.t53.de/dns-query | :heavy_check_mark: |
|technicule.info|https://vpn.technicule.info/dns-query|:heavy_check_mark:|
| [Telekom Deutschland](https://telekomhilft.telekom.de/t5/Offentliche-Tests-Umfragen/Telekom-hilft-Labor-Testet-mit-uns-DNS-over-HTTPS/m-p/5008054) | https://dns.telekom.de/dns-query | :heavy_check_mark: | 
|tesem.dog|https://dns.tesem.dog/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
|thebuckners.org|https://dns.thebuckners.org/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|tierradeayala.com|https://dns.tierradeayala.com/dns-query|:heavy_check_mark:|Block ads
|[TipsyCoffee](https://tipsy.coffee)|https://dns.tipsy.coffee/dns-query|:heavy_check_mark:|Block ads & gambling
| Tls-data.de | https://dns.tls-data.de/dns-query | :heavy_check_mark: |
|[Torsten Tributh](https://tributh.net) |https://tributh.net/dns-query|:heavy_check_mark:|
|[Trash.net](https://www.trash.net/doh/)|Nonblocking: https://resolv1.trash.net/trash-dns<br>https://resolv2.trash.net/trash-dns<br>Adblocking: https://resolv3.trash.net/trash-dns|:heavy_check_mark: |
|[TrcNeTin](https://ns1.trcnet.fi)|https://ns.trcnet.fi/dns-query|:heavy_check_mark:|
|[truta](https://helio.loureiro.eng.br/index.php/todas-categorias/70-networking/19-apache/463-criando-um-servico-de-relay-de-dns-over-https)|https://truta.org/dns-query|:heavy_check_mark:|
|tsc.gov|https://tsc.gov|:heavy_check_mark:|Use Cloudflare upstream with malware filtering 
|tshost.no|https://adg.tshost.no/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|tuskythehusky.tech|https://tuskythehusky.tech/dns-query|:heavy_check_mark:|
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
| **U**
|[UncensoredDNS](https://blog.uncensoreddns.org/dns-servers/)|https://anycast.uncensoreddns.org/dns-query|:heavy_check_mark:|
| [Unstoppable Domains](https://docs.unstoppabledomains.com/d-websites/resolving-dwebsites-in-a-browser/) | https://resolver.unstoppable.io/dns-query | :heavy_check_mark: | Also resolve `.crypto` TLD of Unstoppable Domains, use Cloudflare upstream
| **V**
|vaioswolke.xyz|https://dns.vaioswolke.xyz/dns-query|:heavy_check_mark:|
|[Vasili Sviridov](https://vasi.li)|https://tor.vasi.li/dns-query|:heavy_check_mark:|
|[Vault 81](https://vault81.de)|https://dns.vault81.de/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|[Velyn DNS](https://dns.velyn.my.id)|https://dns.velyn.my.id/query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| [Virga DNS](https://virga.pp.ua) | Adblocking https://virga.pp.ua/dns-query <br> Adblocking & porn blocking https://virga.pp.ua/porn | :heavy_check_mark: <br> :heavy_check_mark: | Server in Japan, use Cloudflare upstream with malware and family filtering, AdGuard browsing security and parental control web service
|[Vojtěch Trunda](https://vojtat.cz)|https://dns.vojtat.cz/dns-query|:heavy_check_mark:|
|vorlif.org|https://vorlif.org/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|vuhai.de|https://bigora2.vuhai.de/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
| **W**
|[Wang Art](https://wang.art/)|https://dns.wang.art/dns-query|:heavy_check_mark:|Adblocking
|waringer-atg.de|https://abel.waringer-atg.de/dns-query|:heavy_check_mark:|
|webnmail.de|https://doh.webnmail.de/dns-query|:heavy_check_mark:|
|webpotato.nl|https://dns.webpotato.nl/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|[WEG B72](https://b72.com)|https://dns.b72.com/dns-query|:heavy_check_mark:|OpenNIC, block ads, gambling & porn
|wehao.net|https://resov.wehao.net/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
|[Wheezy Notes](https://wheezy.naftalie.net/)|https://doh-ca.naftalie.net/dns-query|:heavy_check_mark:|
|[Wikimedia DNS](https://wikitech.wikimedia.org/wiki/Wikimedia_DNS)|https://wikimedia-dns.org/dns-query|:heavy_check_mark:|No filtering, no ECS except for Wikimedia-run servers, QNAME minimization enabled, DNSSEC validation enforced. Requests are served by the nearest Wikimedia data center.
|wil.cloud|https://dns-1.wil.cloud/dns-query<br>https://dns-2.wil.cloud/dns-query|:heavy_check_mark:|Use Cloudflare upstream
|workfordemo.co.in|https://agh.workfordemo.co.in/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream with malware filtering
|[W3C TAG](https://w3ctag.org)|https://dns.w3ctag.org/dns-query|:heavy_check_mark:|
| **X**
|[XiuMu](https://xiumu.org/note/dns.shtml)|https://dns.xiumu.org|:heavy_check_mark:|Use Cloudflare upstream with malware filtering
|xlion.tw|https://dns.xlion.tw/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
|xuming.studio|https://dns.xuming.studio/dns-query|:heavy_check_mark:|Use Cloudflare upstream 
|xusqui.com|https://dns.xusqui.com/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
| **Y**
| [Yarp](https://yarp.lefolgoc.net/) | https://yarp.lefolgoc.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted in France, no logging.
|[yatima](https://yatima.tv/)|https://dns.yatima.tv/dns-query|:heavy_check_mark:|Adblocking
|yingroad.top|https://dns.yingroad.top/dns-query|:heavy_check_mark:|Block ads
|[your-dns](https://github.com/yegle/your-dns)|https://your-dns.run/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|yovbak.com|https://yovbak.com/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service
|yumenashyi.com|https://dns.yumenashyi.com/dns-query|:heavy_check_mark:|Block ads
| **Z**
|[Zakaria](https://zakaria.website)|https://zakaria.website/dns-query<br>https://princez.uk/dns-query|:heavy_check_mark:|
|zburger.top|https://www.zburger.top/dns-query|:heavy_check_mark:|
|[zdn.ro](https://zdn.ro)|https://zdn.ro/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream and AdGuard browsing security web service
|zebrzydowa110.eu|https://blocker.zebrzydowa110.eu/dns-query|:heavy_check_mark:|Block ads
|zemows.industries|https://dns.zemows.industries/dns-query|:heavy_check_mark:|Block ads
|[ZT Browser](https://ztbro.com)|https://doh.ztbro.com/dns-query|:heavy_check_mark:|
|[zxilly](https://learningman.top) |https://dns.learningman.top/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
| **0-9**
|0ooo.icu|https://dns.0ooo.icu/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|0rz.ing|https://dns.0rz.ing/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream 
|0x55|https://dns.0x55.net/dns-query|:heavy_check_mark:|
|003153.xyz|https://003153.xyz/dns-query|:heavy_check_mark:|
|123000123.xyz|https://123000123.xyz/dns-query|:heavy_check_mark:|Block ads, use AdGuard browsing security web service 
|3dcosas.xyz|https://3dcosas.xyz/dns-query|:heavy_check_mark:|
|[3456KR](https://3456.kr)|https://dhlifeus-micro1.dns.3456.kr/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|351242444.xyz|https://351242444.xyz/dns-query|:heavy_check_mark:|Block ads
|[4NetGuides](https://4netguides.org)|https://ns2.4netguides.org/dns-query|:heavy_check_mark:|Block ads
|[5ososea](https://5ososea.com)|Family: https://family.5ososea.com/dns-query<br>Children: https://kids.5ososea.com/dns-query|:heavy_check_mark:|Block ads & porn, use Cloudflare upstream with family filtering and AdGuard browsing security web service
|52306.org|https://dns.52306.org/dns-query|:heavy_check_mark:|
|978159.xyz|https://doh.978159.xyz/dns-query|:heavy_check_mark:|Block ads, use Cloudflare upstream
|9999.sg|https://dns.9999.sg/dns-query|:heavy_check_mark:|
| **Others**
| [@null31](https://ibuki.cgnat.net)| https://ibuki.cgnat.net/dns-query | :heavy_check_mark: | Based in Brazil / doh-server (nginx - unbound) / dot-server (unbound) / DNSSEC / QNAME minimization / Uncensored / no logging, no ECS, hosted on Oracle Cloud VPS by [null31](https://gitlab.com/null31/DoT-DoH-public-config). |
| @publicarray [dns.seby.io](https://dns.seby.io) | https://doh-2.seby.io/dns-query | :heavy_check_mark: | Australian server that runs [@m13253's Go implementation](https://github.com/m13253/dns-over-https), OpenNIC, Unbound with DNSSEC, No ECS, and No logs|


*: Tested via `curl --doh-url <RESOLVER_URI> http://google.com`.
<br>**: Cloudflare upstream means Cloudflare can see the queries' content and the DoH's IP, but usually not the client's IP unless the DoH server forwards it.<br>False positives or negatives from Cloudflare filtering can be reported through [Cloudflare Radar](https://radar.cloudflare.com/).<br>AdGuard's web service receives [hash prefixes](https://adguard.com/kb/general/browsing-security/#in-apps) of the requested domain.<br>[DoT](https://en.wikipedia.org/wiki/DNS_over_TLS) is the primary protocol for Android's Private DNS.<br>[DoQ](https://datatracker.ietf.org/doc/html/rfc9250) send raw DNS query through QUIC stream, skipping HTTP overhead of DoH3

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