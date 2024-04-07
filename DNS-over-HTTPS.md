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
|[AdFilter](https://adfilter.net/)|Perth: https://per.adfilter.net/dns-query<br>Sydney: https://syd.adfilter.net/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking, aggregated statistics kept for 30 days
| [AdGuard](https://adguard-dns.io/en/public-dns.html)     | Default: https://dns.adguard-dns.com/dns-query <br> Family protection: https://family.adguard-dns.com/dns-query <br> Uncensored: https://unfiltered.adguard-dns.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: <br> :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. DNSSEC enabled and TLS 1.3 | 
|[Adrian Lam](https://adrianlam.com/)|https://dns.adrianlam.com/dns-query|:heavy_check_mark:|Adblocking
|[AhaDNS Blitz](https://ahadns.com/blitz/)| Uncensored : https://blitz.ahadns.com <br> OISD filter : https://blitz.ahadns.com/1:1 | :heavy_check_mark: <br> :heavy_check_mark:| [Customizable](https://blitz-setup.ahadns.com/) globally distributed DoH-only server with no logging |
| [AhaDNS](https://ahadns.com) | Netherland:<br> https://doh.nl.ahadns.net/dns-query | :heavy_check_mark: | Deprecated in favor of AhaDNS Blitz |
|[Andrew](https://andrewnw.xyz/)|https://dns.andrewnw.xyz/dns-query|:heavy_check_mark:|Ad & porn blocking
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))|
| [Anudeep](https://anudeep.me) | https://secure.anudeep.me/dns-query | :heavy_check_mark: | Adblocking
| [Artikel10](https://dns.artikel10.org/) | https://dns.artikel10.org/dns-query | :heavy_check_mark: | Non-logging service based in Germany
| [Avast](https://www.avast.com/dns) | https://secure.avastdns.com/dns-query | :heavy_check_mark: | Non-logging
| [Awan.ftp.sh](https://awan.ftp.sh/) | Ads and gambling blocking : https://awan.ftp.sh/dns-query <br> Ads, gambling, drug, tobacco block : https://awan.ftp.sh/no-vice <br> Porn, ads, gambling, drug, tobacco block : https://awan.ftp.sh/noporn-cl <br> Unblocked : https://awan.ftp.sh/unblocked | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Japan
|aws.ketan.dev|https://pihole.aws.ketan.dev/dns-query|:heavy_check_mark:|Adblocking
| **B**
|baishiyuan.cn|https://dns.baishiyuan.cn/dns-query|:heavy_check_mark:|Adblocking
| [Bancuh](https://blog.bancuh.com/adblock-dns/) | Singapore:<br> https://sg-dns1.bancuh.com/dns-query <br> France:<br> https://fr-dns1.bancuh.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Adblocking, porn blocking, log available for originating IP
| Bitdefender | https://dns.bitdefender.net/dns-query | :heavy_check_mark: |
|[Blaze-sk](https://blaze-sk.ru/)|https://dns.blaze-sk.ru/dns-query|:heavy_check_mark:|Adblocking
| [Blokada DNS](https://community.blokada.org/t/the-benefits-of-blokada-dns/6646) | https://dns.blokada.org/dns-query | :heavy_check_mark: | No logging.
|bonis.de|https://adguard.bonis.de/dns-query|:heavy_check_mark:|
| [Brahma World](https://dns.brahma.world/home.html) | https://dns.brahma.world/dns-query | :heavy_check_mark: | No logging • Blocks Ads + Trackers + Malware + Phishing domains, DNSSEC ready • QNAME Minimization • No EDNS Client-Subnet
|bugz.fr|https://stratus.bugz.fr/dns-query|:heavy_check_mark:|Ad & porn blocking
| **C**
|callies-online|https://callies-online.site/dns-query|:heavy_check_mark:|Adblocking
|[Canarypwn](https://aaaab3n.moe/networks) | Cloudflare upstream: https://doh.aaaab3n.moe/dns-query-114514 | :heavy_check_mark: | 
|[Carestyle](https://carestyle.org/)|https://console.carestyle.org/dns-query|:heavy_check_mark:|Adblocking
|[carson-family.com](https://carson-family.com/)|https://dns.carson-family.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|carter.me|https://dns.carter.me/dns-query|:heavy_check_mark:|Adblocking
|catdns.org|https://catdns.org/dns-query|:heavy_check_mark:|
|chadeyron.fr|https://dns.chadeyron.fr/dns-query|:heavy_check_mark:|Adblocking
| Charter | California: <br>https://doh-01.spectrum.com/dns-query <br> Texas: <br>https://doh-02.spectrum.com/dns-query |:heavy_check_mark:<br>:heavy_check_mark:| Trial - Testing multiple platforms
|[chenu.ch](https://chenu.ch/)|https://dns.chenu.ch/dns-query|:heavy_check_mark:|Adblocking
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: <br>https://private.canadianshield.cira.ca/dns-query <br> Protected: <br>https://protected.canadianshield.cira.ca/dns-query <br> Family: <br>https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
| [CIRCL](https://www.circl.lu/) | https://dns.circl.lu/dns-query  | :heavy_check_mark:| Adblocking
|circumitor.de|https://circumitor.de/dns-query|:heavy_check_mark:|Adblocking
| [Cisco Umbrella (OpenDNS)](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query <br> Umbrella: https://doh.umbrella.com/dns-query | :heavy_check_mark: <br>:heavy_check_mark:<br> :heavy_check_mark:| DNSSEC, Anycast
| [CleanBrowsing](https://cleanbrowsing.org/help/docs/dnsoverhttps/) | https://doh.cleanbrowsing.org/doh/family-filter/ <br><br> Filter that allows some mixed-content sites: https://doh.cleanbrowsing.org/doh/adult-filter/ <br><br> Malware blocking only: https://doh.cleanbrowsing.org/doh/security-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
|[Cloud88](https://cloud88.com.au/)|https://dns.cloud88.com.au/dns-query|:heavy_check_mark:|Adblocking
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br><br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br><br> Block Malware: https://security.cloudflare-dns.com/dns-query <br><br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br><br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports both -04 and -13 content-types
|cloudku.technology|https://voyage-s01.cloudku.technology/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Control D](https://controld.com/free-dns) | Unfiltered: <br> https://freedns.controld.com/p0 <br> Malware (Block Malware): <br> https://freedns.controld.com/p1 <br> Ads & Tracking (Block Malware + Ads & Tracking): <br> https://freedns.controld.com/p2 <br> Social (Block Malware + Ads & Tracking + Social Networks): <br>https://freedns.controld.com/p3 <br> Family Friendly (Block Malware + Ads & Tracking + Adult Content + Drugs): <br> https://freedns.controld.com/family <br> Uncensored (Unblock censored domains from various countries) <br> https://freedns.controld.com/uncensored <br><br> - 3rd Party Filters - <br><br> OISD - Full: <br> https://freedns.controld.com/x-oisd <br> OISD - Basic: <br> https://freedns.controld.com/x-oisd-basic <br> StevenBlack Unified: <br> https://freedns.controld.com/x-stevenblack <br> Dev Dan's Hosts: <br> https://freedns.controld.com/x-devdan <br> 1Hosts - Mini: <br> https://freedns.controld.com/x-1hosts-mini <br> 1Hosts - Lite: <br> https://freedns.controld.com/x-1hosts-lite <br> 1Hosts - Pro: <br> https://freedns.controld.com/x-1hosts-pro <br> Hagezi's DNS - Light <br> https://freedns.controld.com/x-hagezi-light <br> Hagezi's DNS - Normal: <br> https://freedns.controld.com/x-hagezi-normal <br> Hagezi's DNS - Pro: <br> https://freedns.controld.com/x-hagezi-pro <br> Hagezi's DNS - Pro Plus: <br> https://freedns.controld.com/x-hagezi-proplus <br> Hagezi's DNS - Ultimate: <br> https://freedns.controld.com/x-hagezi-ultimate <br> Hagezi's DNS - TIF (Threat Intelligence Feeds) <br> https://freedns.controld.com/x-hagezi-tif <br> GoodbyeAds: <br> https://freedns.controld.com/x-goodbyeads <br> AdGuard Filter: <br> https://freedns.controld.com/x-adguard <br> | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark:<br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | ControlD is a fully customizable anycast DNS service that allows you to not only block annoyances like malware, tracking, ads, IoT telemetry, and more but also unblock over 180 services through a network of proxies in over 100 cities.
|[CubeDNS](https://cubedns.com/)|https://cubedns.com/dns-query|:heavy_check_mark:|
|[CynthiaLabs](https://cynthialabs.net/dns/)|https://dns.cynthialabs.net/dns-query|:heavy_check_mark:|Adblocking
| [CZ.NIC](https://www.nic.cz/odvr/) | https://odvr.nic.cz/dns-query | :heavy_check_mark:| Runs on [Knot Resolver](https://www.knot-resolver.cz/) (`doh2`), supports DNSSEC, provided by `.cz` TLD operator
| **D**
|daemon.za.net|https://dns.daemon.za.net/dns-query|:heavy_check_mark:|
| [Danielle McLean](https://00dani.me/) | https://ns.00dani.me/dns-query | :heavy_check_mark: |
| [data.haus](https://data.haus/) | https://ns.data.haus/dns-query | :heavy_check_mark: | Adblocking, non-logging
| [Dekedin](https://dekedin.me/dns/) | https://dns.dekedin.me/dns-query | :heavy_check_mark: | 
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/dns/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
| Disconnect.app | https://doh.disconnect.app/dns-query | :heavy_check_mark: | 
| [DNS Free](https://dns-free.link/) | Adblocking: https://dns-free.link/dns-query <br> Ad & porn blocking: https://dns-free.link/family | :heavy_check_mark: <br> :heavy_check_mark: |
|[dns-ga.de](https://dns-ga.de/server-info.html)|https://doh.dns-ga.de/dns-query|:heavy_check_mark:|
| [dns.digitalsize.net](https://dns.digitalsize.net/) | https://dns.digitalsize.net/dns-query | :heavy_check_mark: | A public, non-tracking, non-filtering DNS resolver with DNSSEC enabled and hosted in Germany |
|dns.expert|https://dns.expert/dns-query| :heavy_check_mark: |
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query <br> https://doh.sb/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| DNSSEC & QNAME minimization enabled, no logging |
| [dns0.eu](https://www.dns0.eu/) | Non-blocking: https://open.dns0.eu<br>Malware blocking: https://dns0.eu<br>Hardened security: https://zero.dns0.eu<br>Child safe: https://kids.dns0.eu | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Non-logging, GDPR compliant
|[DNS4all](https://dns4all.eu/)|https://doh.dns4all.eu/dns-query|:heavy_check_mark:| Non-logging
| [dnscry.pt](https://www.dnscry.pt/) | Allentown: https://abe01.dnscry.pt/dns-query<br>Amsterdam Terrahost: https://ams01.dnscry.pt/dns-query<br>Chicago: https://ord01.dnscry.pt/dns-query<br>Coeur d'Alene: https://coe01.dnscry.pt/dns-query<br>Coventry: https://cvt01.dnscry.pt/dns-query<br>Dallas: https://dfw01.dnscry.pt/dns-query<br>Durham: https://rdu01.dnscry.pt/dns-query<br>Frankfurt: https://fra01.dnscry.pt/dns-query<br>Fujairah: https://fjr01.dnscry.pt/dns-query<br>Liberty Lake: https://llk01.dnscry.pt/dns-query<br>London: https://lon01.dnscry.pt/dns-query<br>Los Angeles Webhosting24: https://lax01.dnscry.pt/dns-query<br>Miami: https://mia01.dnscry.pt/dns-query<br>Munich: https://muc01.dnscry.pt/dns-query<br>New York: https://nyc01.dnscry.pt/dns-query<br>Philadelphia: https://phl01.dnscry.pt/dns-query<br>Phoenix: https://phx01.dnscry.pt/dns-query<br>Salt Lake City: https://slc01.dnscry.pt/dns-query<br>Sandefjord: https://trf01.dnscry.pt/dns-query<br>Singapore: https://sin01.dnscry.pt/dns-query<br>Sofia: https://sof01.dnscry.pt/dns-query<br>Spokane: https://geg01.dnscry.pt/dns-query<br>Stockholm: https://sto01.dnscry.pt/dns-query<br>Tallinn: https://tll01.dnscry.pt/dns-query<br>Tampa: https://tpa01.dnscry.pt/dns-query<br>Warsaw Skhron: https://waw02.dnscry.pt/dns-query| :heavy_check_mark:| Support IPv4+IPv6, uncensored, unfiltered, encrypted, DNSSEC, no logging.
| [dnsforge.de](https://dnsforge.de/) | Adblocking : https://dnsforge.de/dns-query <br> Ads and pornblocking : https://clean.dnsforge.de/dns-query |:heavy_check_mark:<br>:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|
| [dnslow.me](https://dnslow.me/) | https://dnslow.me/dns-query | :heavy_check_mark: | A protective DNS that blocks Ads, Malware, Trackers, Phishing and Newly Registered Domains. Randomly forward requests to different upstreams for enhanced privacy. |
| [DNSPod](https://docs.dnspod.cn/public-dns/dot-doh/) | https://dns.pub/dns-query | :heavy_check_mark: | Operated by Tencent Cloud
| [dnswarden](https://dnswarden.com)| Adblock - <br> https://dns.dnswarden.com/adblock <br><br> Uncensored -<br> https://dns.dnswarden.com/uncensored <br><br> AdultFilter - <br>  https://dns.dnswarden.com/adultfilter | <br>:heavy_check_mark:<br><br><br> :heavy_check_mark:<br><br><br>:heavy_check_mark: | A zero logging DNS with support for DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) & Dnscrypt. Supports DNSSEC, TLS 1.3, QNAME minimization and does own Recursion. EDNS Client Subnet is disabled.<br> Provides 4 different types of filtering options.<br> Adblock - Blocks ads, trackers, viruses, and telemetry.<br> Adultfilter - Blocks adult content, enforces safe search, and includes all the features from adblock. <br> Uncensored - Unrestricted access/no filtering.<br>[Custom Filter](https://dnswarden.com/customfilter.html) where you can choose your own filter lists! <br>For more information look [here](https://github.com/bhanupratapys/dnswarden) or [here](https://dnswarden.com). |
|dnswebvsn.com|https://dnswebvsn.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|doh.best|https://dns.doh.best/dns-query|:heavy_check_mark:|Adblocking
|doh.xyz|https://doh.xyz/dns-query|:heavy_check_mark:|
|domotik.us|https://dnsfilter.domotik.us/dns-query|:heavy_check_mark:|Adblocking
|[Domyah](https://domyah.net/)|https://takhtakh.domyah.net/dns-query|:heavy_check_mark:|
|dotnet.win|https://dns.dotnet.win/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Dukun.de](https://dukun.de/) |https://dukun.de/dns-query | :heavy_check_mark: |
| **E**
|[EasyMosdns](https://doh.apad.pro/)|https://doh.apad.pro/dns-query|:heavy_check_mark:|
| [Edgy DNS](https://edgy.network/dns) | https://edgy-dns.com/dns-query | :heavy_check_mark: | Adblocking
|[Egor Glukhikh](https://henek.ovh/)|https://dns.henek.ovh/dns-query|:heavy_check_mark:|Adblocking
| [Emiliyan Parvanov](https://emiliyan.com/) | https://dns.emiliyan.com/dns-query | :heavy_check_mark: | Adblocking
|esnube.es|https://dns.esnube.es/dns-query|:heavy_check_mark:|
|[Extrawdw](https://extrawdw.net/)|https://dns.extrawdw.net/dns-query|:heavy_check_mark:|Adblocking
|ezyss.id|https://dns.ezyss.id/dns-query|:heavy_check_mark:|
| **F**
|familiamv.net|https://dnsvps.familiamv.net/dns-query|:heavy_check_mark:|Adblocking
| Fancyorg.at | https://dns.fancyorg.at/dns-query |  :heavy_check_mark: | Adblocking
| [FDN](https://www.fdn.fr/) - French Data Network | https://ns0.fdn.fr/dns-query <br> https://ns1.fdn.fr/dns-query |:heavy_check_mark:| No log, no filter, DNSSEC, … ([more informations in French](https://www.fdn.fr/ouverture-des-services-dot-doh/)) |
|felipefalcao.ninja|https://felipefalcao.ninja/dns-query|:heavy_check_mark:|Ad & porn blocking
| [ffmuc.net](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
| Flm9.net | https://dns01.flm9.net/dns-query |  :heavy_check_mark: |
|flylcc.cc|https://life.flylcc.cc/dns-query|:heavy_check_mark:|
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| [Froth.zone](https://dns.froth.zone/resolver) | https://dns.froth.zone/dns-query | :heavy_check_mark: | OpenNIC
|fullaccesstointernet.jp.eu.org|https://dns.fullaccesstointernet.jp.eu.org/dns-query|:heavy_check_mark:|
| **G**
|[Gensokyo](https://freyja.pw/)|https://dns.freyja.pw/dns-query|:heavy_check_mark:|Adblocking
| [Google](https://developers.google.com/speed/public-dns/docs/doh) | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query <br> https://8888.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Full RFC 8484 support, EDNS, no filtering.
|[Guardio](https://guard.io/)|https://dns.guard.io/dns-query|:heavy_check_mark:|
|guidocioni.it|https://dns2.guidocioni.it/dns-query|:heavy_check_mark:|Adblocking
| [Gustavus Adolphus College](https://gustavus.edu/) | https://cluster-0.gac.edu/dns-query <br> https://cluster-1.gac.edu/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| 
| **H**
|hanniel.tech|https://hanniel.tech/dns-query|:heavy_check_mark:|Adblocking
|hostme.co.il|https://ag.hostme.co.il/dns-query|:heavy_check_mark:|Adblocking
| [Hostux.net](https://dns.hostux.net) |  Adblocking DNS: <br> https://dns.hostux.net/ads | :heavy_check_mark: |DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
| Huque | https://doth.huque.com/dns-query | :heavy_check_mark: | 
|huseynov.work|https://dns.huseynov.work/dns-query|:heavy_check_mark:|
| **I**
|ikarosalpha.xyz|https://ikarosalpha.xyz/dns-query|:heavy_check_mark:|Adblocking
| [In-Berlin](https://wiki.in-berlin.de/dns) | https://dns1.in-berlin.de/dns-query | :heavy_check_mark: |
|indybanipal.com|https://dns.indybanipal.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Institut national de recherche en sciences et technologies du numérique](https://www.inria.fr/fr) | https://qlf-doh.inria.fr/dns-query | :heavy_check_mark: |
| [Institute of Operating Systems and Computer Networks](https://wiki.ibr.cs.tu-bs.de/en/services) | https://doh.ibr.cs.tu-bs.de/dns-query | :heavy_check_mark: |
| [Internet Initiative Japan](https://public.dns.iij.jp/) | https://public.dns.iij.jp/dns-query | :heavy_check_mark: | Planned to run until March 2027 
|is.my.waifu.cz|https://aqua.is.my.waifu.cz/dns-query<br>https://megumin.is.my.waifu.cz/dns-query<br>https://yunyun.is.my.waifu.cz/dns-query<br>https://darkness.is.my.waifu.cz/dns-query|:heavy_check_mark:|
|isakula.space|https://isakula.space/dns-query|:heavy_check_mark:|Adblocking
| **J**
| Jackyes.ovh | https://jackyes.ovh/dns-query | :heavy_check_mark: | Adblocking
|jnraptor.net|https://green2.jnraptor.net/dns-query|:heavy_check_mark:|Adblocking
| [Jonas Hahnfeld](https://www.hahnjo.de/) | https://dns.hahnjo.de/dns-query | :heavy_check_mark: |
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query | :heavy_check_mark: | No Censorship, No Logging, No ECS, support DNSSEC in Japan |
|[Justin Counts](https://justincounts.com/)|https://ad.justincounts.com/dns-query|:heavy_check_mark:|
| **K**
| [Kernel-error](https://www.kernel-error.de/2022/03/18/bind-9-18-mit-doh-und-dot/) | https://dns.kernel-error.de/dns-query | :heavy_check_mark: |
|[Kishore](https://avdkishore.dev/)|https://adguard.avdkishore.dev/dns-query|:heavy_check_mark:|
|Konikoni428|https://adguard.konikoni428.com/dns-query|:heavy_check_mark:|Adblocking
| Krnl.eu | https://xray.krnl.eu/dns-query | :heavy_check_mark: | Adblocking
| **L**
| [La Contre-Voie](https://lacontrevoie.fr/en/services/doh/) | https://doh.lacontrevoie.fr/dns-query | :heavy_check_mark: | Supports DNSSEC and IPv6, not logging queries' content, uses [unbound](https://github.com/NLnetLabs/unbound/). Commits for net neutrality, hosted in France.
| [LavaDNS](https://dns.lavate.ch/) | Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in Finland. No logging, no filtering, no ECS, DNSSEC support. |
|[LeadSeason.eu](https://leadseason.eu/)|https://adguard.leadseason.eu/dns-query|:heavy_check_mark:|
|lezainski.com|https://dns2.lezainski.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|[LibreDNS](https://libredns.gr/) | Non-filtering: https://doh.libredns.gr/dns-query <br> Adblocking: https://doh.libredns.gr/noads| :heavy_check_mark: <br> :heavy_check_mark: | Non-logging, OpenNIC.
| [Lindung](https://lindung.pp.ua/) | Adblocking: https://lindung.pp.ua/dns-query <br> Ad & porn blocking: https://lindung.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |
| [Lista](https://lista.my.id/dns-lista-sudah-online-untuk-publik/) | https://dns.lista.my.id/dns-query | :heavy_check_mark: | Adblocking
|londonwebnerd.cloud|https://adguard.londonwebnerd.cloud/dns-query|:heavy_check_mark:|
|[loNET](https://dns.lonet.org/) | Germany 1: https://doh.phdns1.lonet.org/dns-query <br>Germany 2: https://doh.phdns2.lonet.org/dns-query <br>Spain: https://doh.phdns4.lonet.org/dns-query <br>United Kingdom: https://doh.phdns5.lonet.org/dns-query <br>  | :heavy_check_mark:|Adblocking
| **M**
|mandre.dev|https://dns.mandre.dev/dns-query|:heavy_check_mark:|Adblocking
|[Marschi](https://marschi.de/)|https://ag.marschi.de/dns-query|:heavy_check_mark:|Adblocking
| [Masters of Cloud](https://www.masters-of-cloud.de/) | https://masters-of-cloud.de/dns-query | :heavy_check_mark: | 
|meddy94.de|https://adguard.meddy94.de/dns-query|:heavy_check_mark:|Adblocking
|meexx.de|https://testguard.meexx.de/dns-query|:heavy_check_mark:|Adblocking
| [MegaNerd](https://meganerd.nl/encrypted-dns-server) | https://snoke.meganerd.nl/dns-query | :heavy_check_mark: | No logging, no filtering, DNSSEC, based in the Netherlands
|[MERCURY](https://mtsoln.com/)|https://ns.mtsoln.com/dns-query|:heavy_check_mark:|Adblocking
|moderateinfra.net|https://nue2.moderateinfra.net/dns-query|:heavy_check_mark:|Adblocking
|[modr.club](https://modr.club/)|https://ps1.modr.club/dns-query|:heavy_check_mark:|
|[moesite.top](https://moesite.top/)|https://dns.moesite.top/dns-query|:heavy_check_mark:|Adblocking
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | Non-blocking https://dns.mullvad.net/dns-query <br> Adblocking https://adblock.dns.mullvad.net/dns-query <br> Ad & malware blocking https://base.dns.mullvad.net/dns-query <br> Ad, malware, social media blocking https://extended.dns.mullvad.net/dns-query <br> Ad, malware, social media, adult content and gamble blocking https://all.dns.mullvad.net/dns-query <br> Ad, malware, adult content and gamble blocking https://family.dns.mullvad.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Public DoH server in US, DE, GB, SG, and SE with QNAME minimization, audited by [Assured](https://www.assured.se/wp-content/uploads/2021/03/Assured_Mullvad_DoH_server_audit_report.pdf)
| [mydns.network](https://mydns.network) | Uncensored: https://freedom.mydns.network/dns-query <br> Paranoia (no Google/Cloudflare): https://paranoia.mydns.network/dns-query <br> Adblocking: https://adblock.mydns.network/dns-query <br> Family: https://family.mydns.network/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Public DoH server powered by Cloudflare Workers. Uniquely disguises your queries by relaying queries your behalf to upstream DoH servers with no IP address information. [Open source](https://github.com/matthewgall/doh-proxy), deploy your own instance at any time!
| **N**
|narl.app|https://dns.narl.app/dns-query|:heavy_check_mark:|Adblocking
|nenam.eu|https://nenam.eu/dns-query|:heavy_check_mark:|
| Nexific.it | https://doh.luigi.nexific.it/dns-query | :heavy_check_mark:|
| [NextDNS](https://nextdns.io) | https://dns.nextdns.io | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free with non-filtering afterward until the end of the month. Granular dashboard, Each account can create multiple configurations, which can be used for multiple devices with prefixes to track activities on the dashboard. [Create a config ID](https://my.nextdns.io/start)
| [NIC.LV](https://doh.lv/) | https://doh.lv/dns-query <br> https://doh.nic.lv/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run by .lv TLD registry 
|nielsdb.be|https://dns1.nielsdb.be/dns-query|:heavy_check_mark:|Adblocking
| [NiYaWe](https://www.niyawe.de/) | https://doh.niyawe.de/dns-query | :heavy_check_mark: |
| [Njalla](https://dns.njal.la/) | https://dns.njal.la/dns-query | :heavy_check_mark: | Non logging, based in Sweden
| [No Ad DNS](https://noaddns.com/) | https://resolver.noaddns.com/dns-query | :heavy_check_mark: | Adblocking
| [Node15](https://node15.com/) | https://pi1.node15.com/dns-query | :heavy_check_mark: | Block ads and porn
|[Noridev](https://adblock.noridev.moe/html/dns_android.html) | https://1.dns.noridev.moe/dns-query |:heavy_check_mark:|Adblocking
|[NP Solution](https://npsolution.it/)|https://dns.npsolution.it/dns-query|:heavy_check_mark:|Ad & porn blocking
| **O**
|[ofdoom.net](https://ofdoom.net/)|https://dns.ofdoom.net/dns-query|:heavy_check_mark:|Adblocking
|[Omada](https://omada.cafe/)|https://nydns.omada.cafe/dns-query|:heavy_check_mark:|Adblocking
|[OpenBLD.net](https://openbld.net/) | Adapted: https://ada.openbld.net/dns-query <br> Strict: https://ric.openbld.net/dns-query |:heavy_check_mark: <br> :heavy_check_mark:|Adblocking
|orangepipc|https://fwgw.orangepipc.mywire.org/dns-query|:heavy_check_mark:|Adblocking
|[OSZX DNS](https://dns.oszx.co/)|https://dns.oszx.co/dns-query|:heavy_check_mark:|Adblocking
| **P**
| [PaesaDNS](https://milgradesec.github.io/paesadns/) | https://dns.paesa.es/dns-query | :heavy_check_mark: | Adblocking, non-logging
|[PanSzelescik](https://panszelescik.pl/)|https://dns-ovh.panszelescik.pl/dns-query|:heavy_check_mark:|Adblocking
| Path of Grace | https://doh.gcp.pathofgrace.com/dns-query | :heavy_check_mark: | Adblocking
|[Paulo](https://paulo.nom.za)|https://paulo.nom.za/dns-query| :heavy_check_mark: | Adblocking
|[PC Coach](https://pccoach.nl/)|https://dns.pccoach.nl/dns-query|:heavy_check_mark:|Adblocking
|[PersianNIT](https://persiannit.net/)|https://darya.persiannit.net/dns-query|:heavy_check_mark:|Adblocking
|pietjacobs.be|https://dns1.pietjacobs.be/dns-query|:heavy_check_mark:|Adblocking
|pooblet.co.za|https://pooblet.co.za/dns-query|:heavy_check_mark:|Adblocking
|[PragmaSEC](https://pragmasec.nl/)|https://dns.pragmasec.nl/dns-query|:heavy_check_mark:|Adblocking
|puregeni.us|https://dns-privacy.puregeni.us/dns-query|:heavy_check_mark:|Adblocking
| **Q**
| [qquackDNS](https://qquack.org/nameserver) | https://ns1.qquack.org/dns-query | :heavy_check_mark: | Adblocking, non-logging
| [Quad9](https://quad9.net) | https://dns.quad9.net/dns-query | ✔️ | Blocks malware
|[quydang.name.vn](https://quydang.name.vn/)|https://adguard.quydang.name.vn/dns-query|:heavy_check_mark:|
| **R**
|[RAL9005](https://ral9005.org/)|https://ns.ral9005.org/dns-query|:heavy_check_mark:|Adblocking
|[Renardyre](https://renardyre.com/)|https://dns.renardyre.com/dns-query|:heavy_check_mark:|
|[Repinger](https://dns.repinger.my.id/) | https://dns.repinger.my.id/dns-query|:heavy_check_mark:|Adblocking
| [Restena](https://www.restena.lu/en/service/public-dns-resolver) | https://kaitain.restena.lu/dns-query | :heavy_check_mark: | Based in Luxembourg, DNSSEC, minimal logging for technical functions
|[RetakeCS](https://retakecs.com/)|https://dns.retakecs.com/dns-query|:heavy_check_mark:|Adblocking
| [RethinkDNS](https://www.rethinkdns.com/) | Non-filtering: https://sky.rethinkdns.com/dns-query <br> OISD: https://sky.rethinkdns.com/1:IAAgAA== | :heavy_check_mark: <br> :heavy_check_mark: | [An open-source stub resolver](https://github.com/serverless-dns/serverless-dns) running in 200+ locations world-wide on Cloudfare's network. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logs. [code](https://github.com/celzero/rethink-app). [Configure custom blocklists](https://rethinkdns.com/configure)
| [Rezhajul](https://doh.rezhajul.io/) | https://doh.rezhajul.io/dns-query | :heavy_check_mark: | No Logging, DNSSEC enabled, 1.7M+ hosts filtered (ads, tracker, malware, spam, coinminer and phising).
| Rin.sh | https://dns.rin.sh/dns-query | :heavy_check_mark: |
|rootlab.top|https://dns.rootlab.top/dns-query|:heavy_check_mark:|Adblocking
| [RoTunneling](https://www.rotunneling.net/rotunneling-doh-free/) | https://dns.rotunneling.net/dns-query/public | :heavy_check_mark: | Adblocking
|[rslvr.eu](https://rslvr.eu/) |US: https://us.rslvr.eu/dns-query <br>The Netherlands: https://nl.rslvr.eu/dns-query<br>Bulgaria: https://bg.rslvr.eu/dns-query <br>Japan: https://jp.rslvr.eu/dns-query<br>Hong Kong: https://hk.rslvr.eu/dns-query<br>Singapore: https://sg.rslvr.eu/dns-query<br>Australia: https://au.rslvr.eu/dns-query|:heavy_check_mark:|Adblocking
| **S**
| [Safe Surfer](https://safesurfer.io/) | https://doh.safesurfer.io/dns-query | :heavy_check_mark: | Filter porn sites, enforce safe search
|saferbfc.org|https://dns1.saferbfc.org/dns-query<br>https://dns2.saferbfc.org/dns-query|:heavy_check_mark:|Adblocking
| [SafeServe](https://www.namecheap.com/dns/free-public-dns/) | https://safeservedns.com/dns-query | :heavy_check_mark: | Operated by Namecheap
| sarak.as | https://dns.sarak.as/dns-query | :heavy_check_mark:| Ad & porn blocking
|[Sari](https://sarilouis.com/)|https://dns.sarilouis.com/dns-query|:heavy_check_mark:|
|sc-lezhi.com|https://ns1.sc-lezhi.com/dns-query|:heavy_check_mark:|Adblocking
|schlagheck.berlin|https://dns.schlagheck.berlin/dns-query|:heavy_check_mark:|Adblocking
|serdcebolit.ru|https://dns.serdcebolit.ru/dns-query|:heavy_check_mark:|
|shoupperuser.com|https://adguard.shoupperuser.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|shutgaming.net|https://adguard.shutgaming.net/dns-query|:heavy_check_mark:|Adblocking
| Silen.org | https://dns.silen.org/dns-query | :heavy_check_mark: | Adblocking
|[Silentlybren](https://silentlybren.com/)|https://dns.silentlybren.com/dns-query|:heavy_check_mark:|Adblocking
|skrep.eu|https://dns.skrep.eu/dns-query|:heavy_check_mark:|Adblocking
| Slinkyman.net | https://dns.slinkyman.net/dns-query | :heavy_check_mark: | Adblocking
|[spacedns.org](https://spacedns.org/index.html)| https://spacedns.org/dns-query | :heavy_check_mark: | Adblocking, hosted in Poland
|[Spirio.fr](https://spirio.fr/dns/)|https://dns.spirio.fr/dns-query|:heavy_check_mark:|Adblocking
|sscw.win|https://adguard.sscw.win/dns-query|:heavy_check_mark:|Adblocking
|strassmair.org|https://dns.strassmair.org/dns-query|:heavy_check_mark:|
|[StreamVine](https://streamvine.app/)|https://dns.streamvine.app/dns-query|:heavy_check_mark:|
|sukidayo.eu.org|https://sukidayo.eu.org/dns-query|:heavy_check_mark:|
| [Sundalandia](https://sundalandia.pp.ua) | Adblock https://sundalandia.pp.ua/dns-query <br> Family filter https://sundalandia.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |
|[Sunet DNS](https://wiki.sunet.se/display/DNS/Sunet+DNS) | https://resolver.sunet.se/dns-query |:heavy_check_mark:|
|sunnygyl.com|https://sunnygyl.com/dns-query|:heavy_check_mark:|Adblocking
|superstefan.win|https://dns.superstefan.win/dns-query|:heavy_check_mark:|Adblocking
| [Syshero](https://syshero.org/) | https://doh.syshero.org/dns-query | :heavy_check_mark: | 
| **T**
| t53.de | https://dns.t53.de/dns-query | :heavy_check_mark: |
|technicule.info|https://vpn.technicule.info/dns-query|:heavy_check_mark:|
| [Telekom Deutschland](https://telekomhilft.telekom.de/t5/Offentliche-Tests-Umfragen/Telekom-hilft-Labor-Testet-mit-uns-DNS-over-HTTPS/m-p/5008054) | https://dns.telekom.de/dns-query | :heavy_check_mark: | 
|thebuckners.org|https://dns.thebuckners.org/dns-query|:heavy_check_mark:|
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
|tigrons.ru|https://tigrons.ru/dns-query|:heavy_check_mark:|Adblocking
| Tls-data.de | https://dns.tls-data.de/dns-query | :heavy_check_mark: |
|[truta](https://helio.loureiro.eng.br/index.php/todas-categorias/70-networking/19-apache/463-criando-um-servico-de-relay-de-dns-over-https)|https://truta.org/dns-query|:heavy_check_mark:|
|tryk.app|https://dns.tryk.app/dns-query|:heavy_check_mark:|Adblocking
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
|[TXQ](https://txq.life/)|https://dns.txq.life/dns-query|:heavy_check_mark:|Adblocking
| **U**
| [Unstoppable Domains](https://docs.unstoppabledomains.com/d-websites/resolving-dwebsites-in-a-browser/) | https://resolver.unstoppable.io/dns-query | :heavy_check_mark: | Also resolve `.crypto` TLD of Unstoppable Domains.
|unx.io|https://dns.unx.io/dns-query|:heavy_check_mark:|
| **V**
| [Virga DNS](https://virga.pp.ua) | Adblocking https://virga.pp.ua/dns-query <br> Adblocking & porn blocking https://virga.pp.ua/porn | :heavy_check_mark: <br> :heavy_check_mark: | Server in Japan
|vtcuong.site|https://vtcuong.site/dns-query|:heavy_check_mark:|Ad & porn blocking
| **W**
|wahr.top|https://dns.wahr.top/dns-query|:heavy_check_mark:|
|[Wang Art](https://wang.art/)|https://dns.wang.art/dns-query|:heavy_check_mark:|Adblocking
|[Wikimedia DNS](https://wikitech.wikimedia.org/wiki/Wikimedia_DNS)|https://wikimedia-dns.org/dns-query|:heavy_check_mark:|No filtering, no ECS except for Wikimedia-run servers, QNAME minimization enabled, DNSSEC validation enforced. Requests are served by the nearest Wikimedia data center.
| **Y**
| [Yarp](https://yarp.lefolgoc.net/) | https://yarp.lefolgoc.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted in France, no logging.
|[yatima](https://yatima.tv/)|https://dns.yatima.tv/dns-query|:heavy_check_mark:|Adblocking
|yumenashyi.com|https://dns.yumenashyi.com/dns-query|:heavy_check_mark:|
| **Z**
zburger.top|https://www.zburger.top/dns-query|:heavy_check_mark:|
| **0-9**
|4-the.win|https://dns.4-the.win/dns-query|:heavy_check_mark:|
|52306.org|https://dns.52306.org/dns-query|:heavy_check_mark:|
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
|Firefox|62| [Firefox DNS-over-HTTPS](https://support.mozilla.org/en-US/kb/firefox-dns-over-https) |
|[Bromite](https://www.bromite.org/)|67.0.3396.88|[How to enable DoH](https://github.com/bromite/bromite/wiki/Enabling-DNS-over-HTTPS)|
|curl| 7.62.0 | See [DOH-implementation](DOH-implementation) |
|[OkHttp](https://github.com/square/okhttp/tree/master/okhttp-dnsoverhttps)| 3.11 | See [Providers](https://github.com/square/okhttp/blob/master/okhttp-dnsoverhttps/src/test/java/okhttp3/dnsoverhttps/DohProviders.java) |
| [curl-doh](https://github.com/curl/doh) | n/a | basic stand-alone DoH client that uses curl |
| Chrome | 66 | https://support.google.com/chrome/answer/10468685 |
| Windows | 11 | https://learn.microsoft.com/en-us/windows-server/networking/dns/doh-client-support |
| iOS & macOS | iOS 14 & macOS 11 | https://dns.notjakob.com/ | 

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