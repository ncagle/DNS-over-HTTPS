# DoH - DNS over HTTPS

DoH queries resolve over HTTPS for privacy, performance, and security. DoH also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

[RFC 8484 - DNS Queries over HTTPS (DoH)](https://tools.ietf.org/html/rfc8484)

# Publicly available servers

| Who runs it | Base URL | Working*| Comment |
|-------------|----------|---------|---------|
| **A**
|[aaflalo.me](https://www.aaflalo.me/2019/01/dns-over-https-server-aaflalo-me/) | Server US: <br>https://dns-nyc.aaflalo.me/dns-query | :heavy_check_mark:  | Runs on Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https) <br> Checks for DNSSEC and block advertising |
|aattwwss|https://aattwwss.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|[Aavesh Kumar Sinha](https://aavesh.tech/)|https://adguard.aavesh.tech/dns-query|:heavy_check_mark:|Adblocking
|aaytorr.com|https://dns.aaytorr.com/dns-query|:heavy_check_mark:|Adblocking
| abel.waringer-atg.de | https://abel.waringer-atg.de/dns-query | :heavy_check_mark:| 
| [Absolight](https://www.absolight.fr/) | https://res-acst1.absolight.net/dns-query <br> https://res-acst2.absolight.net/dns-query <br> https://res-acst3.absolight.net/dns-query <br> https://resolver1.absolight.net/dns-query <br> https://resolver2.absolight.net/dns-query <br> https://resolver3.absolight.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | 
|abstergo.it|https://block.abstergo.it/dns-query|:heavy_check_mark:|Adblocking
|adblocker.eu.org|https://dns.adblocker.eu.org/dns-query|:heavy_check_mark:|Adblocking
|[AdFilter](https://adfilter.net/)|Adelaide: https://adl.adfilter.net/dns-query<br>Perth: https://per.adfilter.net/dns-query<br>Sydney: https://syd.adfilter.net/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking, aggregated statistics kept for 30 days
| adguard-server.cf | https://adguard-server.cf/dns-query | :heavy_check_mark: | Adblocking
|adguard.myddns.me|https://adguard.myddns.me/dns-query|:heavy_check_mark:|
|adguard.myddns.org|https://adguard.myddns.org/dns-query|:heavy_check_mark:|Adblocking
| [AdGuard](https://adguard.com/en/adguard-dns/overview.html)     | Default: https://dns.adguard.com/dns-query <br> Family protection: https://dns-family.adguard.com/dns-query <br> Uncensored: https://unfiltered.adguard-dns.com/dns-query <br> | :heavy_check_mark: <br>  :heavy_check_mark: <br> :heavy_check_mark: |Default provides ad-blocking at DNS level, while Family protection adds adult site blocking. DNSSEC enabled and TLS 1.3 | 
|adguardh.ga|https://adguardh.ga/dns-query|:heavy_check_mark:|Adblocking
|[Adrian Lam](https://adrianlam.com/)|https://dns.adrianlam.com/dns-query|:heavy_check_mark:|Adblocking
|adrianion.eu|https://dns1.adrianion.eu/dns-query|:heavy_check_mark:|Adblocking
|afastserver.com|https://dns2.afastserver.com/dns-query|:heavy_check_mark:|Adblocking
|[aFixer](https://afixer.app/)|https://shield.afixer.app/dns-query|:heavy_check_mark:|Adblocking
|aflr.io|https://blackhole.aflr.io/dns-query|:heavy_check_mark:|Adblocking
|agafon.space|https://www.agafon.space/dns-query|:heavy_check_mark:|Adblocking
|[AhaDNS Blitz](https://ahadns.com/blitz/)| Uncensored : https://blitz.ahadns.com <br> OISD filter : https://blitz.ahadns.com/1:1 <br> OISD & Energized Porn filter : https://blitz.ahadns.com/1:1.12 | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| [Customizable](https://blitz-setup.ahadns.com/) globally distributed DoH-only server with no logging |
| [AhaDNS](https://ahadns.com) | Netherland:<br> https://doh.nl.ahadns.net/dns-query <br> Los Angeles:<br> https://doh.la.ahadns.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | A zero-logging DNS with support for DNS-over-HTTPS (DoH) & DNS-over-TLS (DoT). Blocks ads, malware, trackers, viruses, and telemetry. DNSSEC, TLS 1.3, Open Source. Uses OISD list |
| Aihe | https://aihe.app/dns-query | :heavy_check_mark: | 
|airmaxcloud|https://airmaxcloud.ml/dns-query|:heavy_check_mark:|Adblocking
|[Ajraspi](https://ajraspi.xyz/)|https://rdjdns.ajraspi.xyz/dns-query|:heavy_check_mark:|Adblocking
| [alekberg](https://alekberg.net) | Amsterdam Non-filtering: https://dnsnl.alekberg.net/dns-query <br> Sweden Non-filtering: https://dnsse.alekberg.net/dns-query <br> Amsterdam Adblocking: https://dnsnl-noads.alekberg.net/dns-query <br> Sweden Non-filtering: https://dnsse-noads.alekberg.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| DoH Servers in Spain, Holland and Sweden. No logging, DNSSEC support.|
|[Alibaba Public DNS](https://www.alidns.com/)| https://dns.alidns.com/dns-query | :heavy_check_mark:| [DoH/DoT/DNS Json API](https://www.alidns.com/faqs/#dns-safe), Best DoH/DoT server in China |
|alloxr.info|https://dns.alloxr.info/dns-query|:heavy_check_mark:|
| Almir1904 | https://dns.almir1904.eu/dns-query | :heavy_check_mark: | Adblocking
|alpo.pp.ua|https://2.alpo.pp.ua/dns-query|:heavy_check_mark:|Adblocking
|altairzone.it|https://dns.altairzone.it/dns-query|:heavy_check_mark:|Adblocking
|[Aman](https://aman.ltd/)|https://dns.aman.ltd/dns-query|:heavy_check_mark:|Adblocking
| Ambiya | https://adguard.ambiya.net/dns-query | :heavy_check_mark: | Adblocking
|amigo-mgn.ru|https://dns.amigo-mgn.ru/dns-query|:heavy_check_mark:|Adblocking
|amlegion.org|https://mailer.amlegion.org/dns-query|:heavy_check_mark:|Adblocking
|[Andrew](https://andrewnw.xyz/)|https://dns.andrewnw.xyz/dns-query|:heavy_check_mark:|Ad & porn blocking
|[Andrews & Arnold](https://aa.net.uk/dns) | https://dns.aa.net.uk/dns-query | :heavy_check_mark: | no logging (see [DNS Disclaimer](https://www.aa.net.uk/legal/dohdot-disclaimer/))|
| Anggityuls | https://anggityuls.my.id/dns-query | :heavy_check_mark: | Adblocking
|[Animesh Roy](https://anir0y.in/)|https://dot.anir0y.in/dns-query|:heavy_check_mark:|Adblocking
|anixlab|https://anixlab.com/dns-query|:heavy_check_mark:|Adblocking
|anoogohost.net|https://dns.anoogohost.net/dns-query|:heavy_check_mark:|Adblocking
| Apem Legit | https://d.apemlegit.my.id/dns-query | :heavy_check_mark: | Adblocking
|applewebkit.dev|https://dns.applewebkit.dev/dns-query|:heavy_check_mark:|Adblocking
| [Aquilenet](https://www.aquilenet.fr) | https://dns.aquilenet.fr/dns-query | :heavy_check_mark: | French non profit Internet service provider http://dns.aquilenet.fr|
|armorrush|https://armorrush.eu.org/dns-query|:heavy_check_mark:|Adblocking
| [Arnor.org](https://arnor.org) | https://nsec.arnor.org/dns-query | :heavy_check_mark: | Adblocking
|[Art-Shpiller](https://art-nas.pp.ua/)|https://dns2.art-nas.pp.ua/dns-query|:heavy_check_mark:|Adblocking
| [Artikel10](https://dns.artikel10.org/) | https://dns.artikel10.org/dns-query | :heavy_check_mark: | Non-logging service based in Germany
|asf1992labs.tk|https://dns.asf1992labs.tk/dns-query|:heavy_check_mark:|Adblocking
| [Asteroid B612](https://b612.me/) | https://dns.b612.me/dns-query | :heavy_check_mark: |
|[AT&T](http://att.net)|https://dohtrial.att.net|:heavy_check_mark:|
|atlantic.dyn1.de|https://atlantic.dyn1.de/dns-query|:heavy_check_mark:|Adblocking
|audet.cloud|https://dns.audet.cloud/dns-query|:heavy_check_mark:|Adblocking
| [Avast](https://www.avast.com/dns) | https://secure.avastdns.com/dns-query | :heavy_check_mark: | Non-logging
| [Avengers Infosec](https://infosec.xyz/blog/2019/new-dns-service/) | https://dns.infosec.xyz/dns-query | :heavy_check_mark: | Adblocking, blocked queries logged, others aren't, forwarded to Google/Cloudflare/Quad.
|[Aviontex](https://keweon.center/)|https://dns.keweon.center/dns-query|:heavy_check_mark:|Adblocking
| [Awan.ftp.sh](https://awan.ftp.sh/) | Ads and gambling blocking : https://awan.ftp.sh/dns-query <br> Ads, gambling, drug, tobacco block : https://awan.ftp.sh/no-vice <br> Porn, ads, gambling, drug, tobacco block : https://awan.ftp.sh/noporn-cl <br> Unblocked : https://awan.ftp.sh/unblocked | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Japan
|aws.ketan.dev|https://pihole.aws.ketan.dev/dns-query|:heavy_check_mark:|Adblocking
|axaxa|https://axaxa.fun/dns-query|:heavy_check_mark:|Adblocking
|azcom.dev|https://dns.azcom.dev/dns-query|:heavy_check_mark:|Ad & porn blocking
| [AzSoPro](https://dns.azsopro.net/) | https://dns.azsopro.net/dns-query | :heavy_check_mark: | Non filtering, non logging, DNSSEC enabled 
| **B**
|b33|https://dns.b33.space/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Bancuh](https://blog.bancuh.com/adblock-dns/) | Singapore:<br> https://sg-dns1.bancuh.com/dns-query <br> France:<br> https://fr-dns1.bancuh.com/dns-query <br> Tokyo:<br> https://jp-dns1.bancuh.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Adblocking, porn blocking, log available for originating IP
|bcandrade|https://bcandrade.ml/dns-query|:heavy_check_mark:|Adblocking
| [BebasDNS](https://github.com/bebasid/bebasdns) | Singapore:<br> https://dns.bebasid.com/dns-query | :heavy_check_mark: | DNS-based ad-blocking service
|beliefanx.cn|https://adguard.beliefanx.cn/dns-query|:heavy_check_mark:|Adblocking
| [Belnet](https://dns.belnet.be/) | https://dns.belnet.be/dns-query | :heavy_check_mark: | IP, response code, protocol, and response time are logged for performance & statistic purposes. Hosted in Belgium by the Belgian National Research and Education Network.
|[BenDiom](https://ilker.se/)|https://dns.ilker.se/dns-query|:heavy_check_mark:|Adblocking
|[benpro](https://benpro.fr/)|https://dns.benpro.fr/dns-query|:heavy_check_mark:|Ad & porn blocking
|betamax65.de|https://adguard.betamax65.de/dns-query|:heavy_check_mark:|Adblocking
|bielperes.me|https://mydns.bielperes.me/dns-query|:heavy_check_mark:|Ad & porn blocking
|bin.st|https://dns.bin.st/dns-query|:heavy_check_mark:|Ad & porn blocking
|bissnes.org|https://goga7777777.bissnes.org/dns-query|:heavy_check_mark:|Ad & porn blocking
|bit-trail.nl|https://ns3.bit-trail.nl/dns-query|:heavy_check_mark:|Adblocking
| Bitdefender | https://dns.bitdefender.net/dns-query | :heavy_check_mark: |
|bitteeinbyte.de|https://adguard.bitteeinbyte.de/dns-query|:heavy_check_mark:|Adblocking
| [Blahdns](https://blahdns.com/) | Switzerland: <br>https://doh-ch.blahdns.com/dns-query <br> Singapore: <br>https://doh-sg.blahdns.com/dns-query <br> Finland: <br>https://doh-fi.blahdns.com/dns-query <br> Japan: <br>https://doh-jp.blahdns.com/dns-query <br> Germany: <br>https://doh-de.blahdns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based on [Go implementation](https://github.com/m13253/dns-over-https), HAProxy + Dnsdist + Knot-resolver with DNSSEC, No ECS, No logs, Adblock
| [BlissDNS](https://github.com/BlissDNS) | https://us1.blissdns.net/dns-query | :heavy_check_mark: | Adblocking, queries logged for 24 hours
| [Blokada DNS](https://community.blokada.org/t/the-benefits-of-blokada-dns/6646) | https://dns.blokada.org/dns-query | :heavy_check_mark: | No logging.
|[bluemeda.cf](https://bluemeda.cf/)|https://dns.bluemeda.cf/dns-query|:heavy_check_mark:|Adblocking
|bluemood|https://bluemood.me/dns-query|:heavy_check_mark:|Adblocking
|bluestarnc.com|https://dns.bluestarnc.com/dns-query|:heavy_check_mark:|Adblocking
|[Bob Strecansky](https://bobstrecansky.com/)|https://dns.bobstrecansky.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|boje8.me|https://doh.boje8.me/dns-query|:heavy_check_mark:|Adblocking
| Borjalopez | https://adblock.borjalopez.eu/dns-query | :heavy_check_mark: | Adblocking
| [Bortzmeyer](https://www.bortzmeyer.org/doh-bortzmeyer-fr-policy.html) | https://doh.bortzmeyer.fr | :heavy_check_mark: | French-based, non-logging. 
|bosco.ovh|https://cloudns.bosco.ovh/dns-query|:heavy_check_mark:|Adblocking
| [Brahma World](https://dns.brahma.world/home.html) | https://dns.brahma.world/dns-query | :heavy_check_mark: | No logging • Blocks Ads + Trackers + Malware + Phishing domains, DNSSEC ready • QNAME Minimization • No EDNS Client-Subnet
|brian-hong.tech|https://dns.brian-hong.tech/dns-query|:heavy_check_mark:|Adblocking
|[BrightestTV](https://brightesttv.com/)|https://dns.brightesttv.com/dns-query|:heavy_check_mark:|Adblocking
|[BroSena](https://brosena.xyz/)|https://home3.brosena.xyz/dns-query|:heavy_check_mark:|Adblocking
|bruckmoser.it|https://home.bruckmoser.it/dns-query|:heavy_check_mark:|Adblocking
|[BT](https://bt.com)|https://doh.bt.com|:heavy_check_mark:|
|buck.ovh|https://block.buck.ovh/dns-query|:heavy_check_mark:|Adblocking
| [Bunny](https://bunny.net/) | https://doh1.b-cdn.net/dns-query | :heavy_check_mark: | Adblocking
|bw.i81.ru|https://dns.bw.i81.ru/dns-query|:heavy_check_mark:|Adblocking
| **C**
| C-dns | https://www.c-dns.com/dns-query | :heavy_check_mark: | 
|cachitopetshop.com|https://dns.cachitopetshop.com/dns-query|:heavy_check_mark:|Adblocking
|[carson-family.com](https://carson-family.com/)|https://dns.carson-family.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|cbio.top|https://dns2.cbio.top/dns-query|:heavy_check_mark:|Adblocking
| Ccb-net | https://doh.ccb-net.it | :heavy_check_mark: | Adblocking 
|cdzopi|https://cdzopi.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| Ceai | https://dns.ceai.com.tw/dns-query | :heavy_check_mark: | Adblocking 
|cearhome.top|https://dns.cearhome.top/dns-query|:heavy_check_mark:|
|cepheus0.com|https://oracle.cepheus0.com/dns-query|:heavy_check_mark:|Adblocking
|cgmzdd|https://cgmzdd.com/dns-query|:heavy_check_mark:|Adblocking
| Chaos System | https://chaos-system.de/dns-query | :heavy_check_mark: | Adblocking
| Charter | California: <br>https://doh-01.spectrum.com/dns-query <br> Texas: <br>https://doh-02.spectrum.com/dns-query |:heavy_check_mark:<br>:heavy_check_mark:| Trial - Testing multiple platforms
|[chenu.ch](https://chenu.ch/)|https://dns.chenu.ch/dns-query|:heavy_check_mark:|Adblocking
| Chromeina | https://dns.chromeina.top/dns-query | :heavy_check_mark: | Adblocking 
|[Chungyu](https://chungyu.com/)|https://oraclejp2.chungyu.com/dns-query|:heavy_check_mark:|
| Cicitt | https://c.cicitt.ch/dns-query | :heavy_check_mark: | Adblocking 
|cintra|https://cintra.ml/dns-query|:heavy_check_mark:|Adblocking
| [CIRA Canadian Shield](https://www.cira.ca/cybersecurity-services/canadian-shield) | Private: <br>https://private.canadianshield.cira.ca/dns-query <br> Protected: <br>https://protected.canadianshield.cira.ca/dns-query <br> Family: <br>https://family.canadianshield.cira.ca/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports DNSSEC, keeps DNS traffic inside Canada. <br> Private: DNS resolution service that keeps your DNS data private from third-parties. <br> Protected: Includes Private features and adds malware and phishing blocking. <br> Family: Includes Protected and Private features and blocks pornographic content. |
|cirruscloud|https://cirruscloud.it/dns-query|:heavy_check_mark:|Adblocking
| [Cisco Umbrella (OpenDNS)](https://support.opendns.com/hc/en-us/articles/360038086532-Using-DNS-over-HTTPS-DoH-with-OpenDNS) | Standard: https://doh.opendns.com/dns-query <br> FamilyShield (blocks adult content):  https://doh.familyshield.opendns.com/dns-query | :heavy_check_mark: <br><br> :heavy_check_mark:| DNSSEC, Anycast
| Clanless.ovh | https://dns.clanless.ovh/dns-query | :heavy_check_mark:| Adblocking
|clawsucht.nrw|https://adguard.clawsucht.nrw/dns-query|:heavy_check_mark:|Adblocking
| [CleanBrowsing](https://cleanbrowsing.org/help/docs/dnsoverhttps/) | https://doh.cleanbrowsing.org/doh/family-filter/ <br><br> Filter that allows some mixed-content sites: https://doh.cleanbrowsing.org/doh/adult-filter/ <br><br> Malware blocking only: https://doh.cleanbrowsing.org/doh/security-filter/ | :heavy_check_mark: | anycast DoH server with parental control (restricts access to adult content + enforces safe search)
|[CLEARVIEW](https://clearviewtechnology.net/)|https://cvt-ic-us-adns-001.clearviewtechnology.net/dns-query|:heavy_check_mark:|Adblocking
|cloud-sekeng.com|https://doh.cloud-sekeng.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Cloudflare](https://developers.cloudflare.com/1.1.1.1/)  | https://cloudflare-dns.com/dns-query <br><br> Mozilla: https://mozilla.cloudflare-dns.com/dns-query <br><br> Block Malware: https://security.cloudflare-dns.com/dns-query <br><br> Block Malware and Adult Content: https://family.cloudflare-dns.com/dns-query <br><br> DNS64: https://dns64.cloudflare-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Supports both -04 and -13 content-types
|cloudlinz.de|https://dns.cloudlinz.de/dns-query|:heavy_check_mark:|Adblocking
|[Cloudmini](https://cloudmini.net/)|https://adguard.cloudmini.net/dns-query|:heavy_check_mark:|Adblocking
|cloudnx.cloud|https://dns-secondary.cloudnx.cloud/dns-query|:heavy_check_mark:|
|cloudseriousshit|https://cloudseriousshit.com/dns-query|:heavy_check_mark:|Adblocking
| [COLA16K](https://cola16.app/) | https://jpdns.cola16.app/dns-query | :heavy_check_mark: | Adblocking
| Colorfreedom | https://dns.colorfreedom.org/dns-query | :heavy_check_mark: | Adblocking
| Comcast | https://doh.xfinity.com/dns-query | :heavy_check_mark:| DNSSEC Validation, [DNS Privacy Policy](https://www.xfinity.com/privacy/policy/dns) |
|[comeonjames.club](https://comeonjames.club/)|https://dns.comeonjames.club/dns-query|:heavy_check_mark:|Adblocking
| [Computer Incident Response Center Luxembourg](https://circl.lu/) | https://dns.circl.lu/dns-query | :heavy_check_mark:| 
| [Comss](https://www.comss.ru/page.php?id=7315) | https://dns.comss.one/dns-query | :heavy_check_mark: | Block ads, tracker, phishing and malware
|connect.fail|https://dns.connect.fail/dns-query|:heavy_check_mark:|Adblocking
| [ControlD](https://controld.com/) | Unfiltered: <br>https://freedns.controld.com/p0 <br> Block Malware: <br>https://freedns.controld.com/p1 <br> Block Malware + Ads: <br>https://freedns.controld.com/p2 <br> Block Malware + Ads + Social: <br>https://freedns.controld.com/p3 <br> Block Malware, Ads, Adult content: <br>https://freedns.controld.com/family <br> OISD: <br>https://freedns.controld.com/x-oisd | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | ControlD is a fully customizable anycast DNS service that allows you to not only block annoyances like malware, tracking, ads, IoT telemetry, and more but also unblock over 180 services through a network of proxies in over 100 cities.
|cossxiu|https://cossxiu.ga/dns-query|:heavy_check_mark:|Adblocking
|[CryptoMize](https://privacy.cm/)|https://dns.privacy.cm/dns-query|:heavy_check_mark:|Adblocking
| Cryptroute | https://dotdns.cryptroute.com/dns-query | :heavy_check_mark:| Adblocking
|cwlys.com|https://dns.cwlys.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Cybershell](https://blog.cybershell.xyz/page/services-6367519a3e34207f1d323d5a) | https://dns.cybershell.xyz/dns-query | :heavy_check_mark:| Block ads and porn, client IP and queries logged for 24 hours
| [CZ.NIC](https://www.nic.cz/odvr/) | https://odvr.nic.cz/dns-query | :heavy_check_mark:| Runs on [Knot Resolver](https://www.knot-resolver.cz/) (`doh2`), supports DNSSEC, provided by `.cz` TLD operator
| **D**
|d365.in|https://dns.d365.in/dns-query|:heavy_check_mark:|Adblocking
|d94.xyz|https://dns.d94.xyz/dns-query|:heavy_check_mark:|Adblocking
|d96.info|https://dns.d96.info/dns-query|:heavy_check_mark:|Adblocking
|[Daegan Nesselrode](https://dtness.com/)|https://adguard.dtness.com/dns-query|:heavy_check_mark:|Adblocking
| [Daniel Woffinden](https://daw.dev/) | https://dns.daw.dev/dns-query | :heavy_check_mark: | Adblocking
| [Danielle McLean](https://00dani.me/) | https://ns.00dani.me/dns-query | :heavy_check_mark: |
|dankatapich.eu.org|https://adg.dankatapich.eu.org/dns-query|:heavy_check_mark:|Adblocking
|darkness.is.my.waifu|https://darkness.is.my.waifu.cz/dns-query|:heavy_check_mark:|
|[DarkNET](https://darknet.bg/)|https://firewall.darknet.bg/dns-query|:heavy_check_mark:|Adblocking
| [data.haus](https://data.haus/) | https://mail.data.haus/dns-query | :heavy_check_mark: | Adblocking, non-logging
| [DataCore](https://datacore.ch/website/page/frontpage) | https://doh.datacore.ch/dns-query | :heavy_check_mark: | Adblocking
| [Datahata.by](https://doh.datahata.by/) | https://doh.datahata.by/dns-query | :heavy_check_mark: |
|datamatter.co.za|https://pihole.datamatter.co.za/dns-query|:heavy_check_mark:|Adblocking
|[David Ruhmann](https://davidruhmann.com/)|https://dns.davidruhmann.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Decloudus](https://decloudus.com/) |  https://dns.decloudus.com/dns-query | :heavy_check_mark: | Based in Germany. Adblocking
|deekshith.in|https://dns.deekshith.in/dns-query|:heavy_check_mark:|Adblocking
| Dekonix.ru | https://adguard.dekonix.ru/dns-query | :heavy_check_mark: | Adblocking
|depieri.net|https://adguard.depieri.net/dns-query|:heavy_check_mark:|Ad & porn blocking
|dessoi.cloud|https://adguard.dessoi.cloud/dns-query|:heavy_check_mark:|Adblocking
| [Detoxify Porn Blocker](https://detoxifypornblocker.com/) | https://doh-primary-pool.detoxifypornblocker.com/dns-query | :heavy_check_mark: | Block ads and porn
|deus-server|https://deus-server.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|dewed.de|https://mainframe.dewed.de/dns-query|:heavy_check_mark:|Adblocking
|dgca.myds.me|https://dgca.myds.me/dns-query|:heavy_check_mark:|Adblocking
|dgea.fr|https://dns.dgea.fr/dns-query|:heavy_check_mark:|Adblocking
|[DIGI](https://go.ro/)|https://colean.go.ro/dns-query|:heavy_check_mark:|Adblocking
|[Digital Evergarden](https://hee.ink/)|https://dns.hee.ink/dns-query|:heavy_check_mark:|Adblocking
| [Digitale Gesellschaft](https://www.digitale-gesellschaft.ch/) |  https://dns.digitale-gesellschaft.ch/dns-query | :heavy_check_mark: | No query/IP logging, no filtering, QNAME minimization, TLS 1.3, DNSSEC; https://www.digitale-gesellschaft.ch/dns/ |
|dionysus.beauty|https://v2.dionysus.beauty/dns-query|:heavy_check_mark:|Adblocking
|diplo.es|https://a11.diplo.es/dns-query|:heavy_check_mark:|Adblocking
| Disconnect.app | https://doh.disconnect.app/dns-query | :heavy_check_mark: | 
|dlcea|https://dlcea.com/dns-query|:heavy_check_mark:|Adblocking
|dmr.pw|https://dns.dmr.pw/dns-query|:heavy_check_mark:|Adblocking
| [DNS For Family](https://dnsforfamily.com/#DNS_Servers_DNS_Over_HTTPS) | https://dns-doh.dnsforfamily.com/dns-query | :heavy_check_mark: | Filter websites for family use, and enforces safe search in Google, YouTube, Bing, DuckDuckGo and Yandex. DNSSEC-ready, non-logging
| [dns-ga.de](https://servers.opennic.org/edit.php?srv=ns5.de.dns.opennic.glue) | https://dns2.dns-ga.de/dns-query <br> https://dns3.dns-ga.de/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | OpenNIC, logged for 6 hours
| [dns.digitalsize.net](https://dns.digitalsize.net/) | https://dns.digitalsize.net/dns-query | :heavy_check_mark: | A public, non-tracking, non-filtering DNS resolver with DNSSEC enabled and hosted in Germany |
|dns.ikataruto.com|https://jp.dns.ikataruto.com/dns-query|:heavy_check_mark:|Adblocking
|[dns.ipoac.nl](https://dns.ipoac.nl/)|https://dns.ipoac.nl/dns-query|:heavy_check_mark:|
| dns.linkr.ninja | https://dns.linkr.ninja/dns-query | :heavy_check_mark: | Adblocking
|dns.nomu.pw|https://ttag.dns.nomu.pw/dns-query|:heavy_check_mark:|Adblocking
| [DNS.SB](https://dns.sb/doh/) | https://doh.dns.sb/dns-query <br> https://doh.sb/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| DNSSEC & QNAME minimization enabled, no logging |
|dns.terumi.club|https://apne1.dns.terumi.club/dns-query|:heavy_check_mark:|Adblocking
|[DNS4all](https://dns4all.eu/)|https://doh.dns4all.eu/dns-query|:heavy_check_mark:|
| [dns4me](https://dns4me.net/) | https://nz01.dns4me.net <br> https://au01.dns4me.net <br> https://au02.dns4me.net <br> https://sg01.dns4me.net <br> https://uk01.dns4me.net <br> https://us01.dns4me.net <br> https://us02.dns4me.net <br> https://sa01.dns4me.net <br> https://ca01.dns4me.net <br> https://ca02.dns4me.net | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: |
|dns9999|https://dns9999.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|dnsadguard.co.uk|https://www.dnsadguard.co.uk/dns-query|:heavy_check_mark:|Adblocking
| [dnscrypt.ca](https://dnscrypt.ca/) | https://dns1.dnscrypt.ca:453/dns-query | :heavy_check_mark:| Canadian, uncensored, no-logs, encrypted, and DNSSEC
| [dnscrypt.uk](https://dnscrypt.uk/) | Digital Ocean: <br>https://doh.dnscrypt.uk/dns-query <br> Vultr: <br>https://v.dnscrypt.uk/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | UK-based
| dnsenc.com | https://dnsenc.com/dns-query | :heavy_check_mark:| Adblocking
|dnsfish.com|https://gpchubjk.dnsfish.com/dns-query|:heavy_check_mark:|Adblocking
| [dnsforge.de](https://dnsforge.de/) | https://dnsforge.de/dns-query |:heavy_check_mark:|  No logging. Support DNSSEC. Hosted in Germany|
| [dnsHome.de](https://www.dnshome.de/doh-dot-public-resolver.php) |  https://dns.dnshome.de/dns-query | :heavy_check_mark:| DoH Server in Germany. No logging, No filtering, DNSSEC and own DNS Resolver |
| [dnslow.me](https://dnslow.me/) | https://dnslow.me/dns-query | :heavy_check_mark: | A protective DNS that blocks Ads, Malware, Trackers, Phishing and Newly Registered Domains. Randomly forward requests to different upstreams for enhanced privacy. |
| [DNSPod](https://www.dnspod.com/Products/Public.DNS) | https://dns.pub/dns-query | :heavy_check_mark: | Operated by Tencent Cloud
|dnsuser.info|https://bilidon.dnsuser.info/dns-query|:heavy_check_mark:|Adblocking
| [dnswarden](https://dnswarden.com)| Adblock - <br> https://dns.dnswarden.com/adblock <br><br> Uncensored -<br> https://dns.dnswarden.com/uncensored <br><br> AdultFilter - <br>  https://dns.dnswarden.com/adultfilter | <br>:heavy_check_mark:<br><br><br>:heavy_check_mark:<br><br><br>:heavy_check_mark: | A zero logging DNS with support for DNS-over-HTTPS (DoH), DNS-over-TLS (DoT) & Dnscrypt. Supports DNSSEC, TLS 1.3, QNAME minimization and does own Recursion. EDNS Client Subnet is disabled.<br> Provides 4 different types of filtering options.<br> Adblock - Blocks ads, trackers, viruses, and telemetry.<br> Adultfilter - Blocks adult content, enforces safe search, and includes all the features from adblock. <br> Uncensored - Unrestricted access/no filtering.<br>[Custom Filter](https://dnswarden.com/customfilter.html) where you can choose your own filter lists! <br>For more information look [here](https://github.com/bhanupratapys/dnswarden) or [here](https://dnswarden.com). |
|dog|https://beacon.dog/dns-query|:heavy_check_mark:|Adblocking
| [doh.li](https://doh.li)| https://doh.li/dns-query | :heavy_check_mark: | Runs on [dns-over-https](https://github.com/m13253/dns-over-https), no logging, EDNS Client Subnet enabled, based in DigitalOcean London. DNSSEC and adblock are not currently enabled. |
|[DoTLS](https://dotls.org/)|https://admin.dotls.org/dns-query|:heavy_check_mark:|Adblocking
|douglaster|https://douglaster.com/dns-query|:heavy_check_mark:|Adblocking
|dr-adguard.de|https://dr-adguard.de/dns-query|:heavy_check_mark:|Ad & porn blocking
|druta.me|https://dns.druta.me/dns-query|:heavy_check_mark:|Adblocking
|dscloud.me|https://doh.dscloud.me/dns-query|:heavy_check_mark:|Adblocking
| [Dukun.de](https://dukun.de/) |https://dukun.de/dns-query | :heavy_check_mark: |
|dupatruwi22.fun|https://www.dupatruwi22.fun/dns-query|:heavy_check_mark:|Adblocking
|dupatruwi22|https://dupatruwi22.fun/dns-query|:heavy_check_mark:|Adblocking
|[DutchWhite](https://dutchwhite.nl/)|https://dns.dutchwhite.nl/dns-query|:heavy_check_mark:|Adblocking
| Dyn1.de | https://dns.dyn1.de/dns-query | :heavy_check_mark: | Adblocking
| **E**
| [e-utp.net](https://fido.e-utp.net/display/EUTPNET/Recursive+DNS) | https://dnscache.e-utp.net/dns-query | :heavy_check_mark: | IPv6 only
|e2ee.li|https://dns1.e2ee.li/dns-query|:heavy_check_mark:|Adblocking
| [Easyhandshake](https://easyhandshake.com/) | https://easyhandshake.com:8053/dns-query | :heavy_check_mark: | Also resolve Handshake domains
| [Edgy DNS](https://edgy.network/dns) | https://edgy-dns.com/dns-query | :heavy_check_mark: | Adblocking
|edison42.dev|https://dns.edison42.dev/dns-query|:heavy_check_mark:|Adblocking
|ef67daisuki.club|https://adguard.ef67daisuki.club/dns-query|:heavy_check_mark:|Adblocking
|[ekipapi.com](https://ekipapi.com/)|https://dns.ekipapi.com/dns-query|:heavy_check_mark:|Adblocking
|elbschloss.xyz|https://hole.elbschloss.xyz/dns-query|:heavy_check_mark:|Adblocking
|[Electron decomposer](https://jpr.space/)|https://addns.jpr.space/dns-query|:heavy_check_mark:|Adblocking
|[Element](https://unerror.network/)|https://dns.unerror.network/dns-query|:heavy_check_mark:|Adblocking
| [Elemental Software](https://elemental.software/) | https://dns.elemental.software/dns-query | :heavy_check_mark: |
|[Elia Tofani](https://eliatofani.it/)|https://dns.eliatofani.it/dns-query|:heavy_check_mark:|Adblocking
|[Elli's Corner](https://ellichua.com/)|https://dns.ellichua.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|elshad-adgh-dns.ru|https://www.elshad-adgh-dns.ru/dns-query|:heavy_check_mark:|Adblocking
| [Emiliyan Parvanov](https://emiliyan.com/) | https://dns.emiliyan.com/dns-query | :heavy_check_mark: | Adblocking
|emozee.cf|https://emozee.cf/dns-query|:heavy_check_mark:|Adblocking
|erw.cc|https://hk.erw.cc/dns-query|:heavy_check_mark:|
| [eSeGeCe](https://www.esegece.com/) | Adblocking: https://dns.esegece.com/dns-query <br> Ad & porn blocking: https://dns-family.esegece.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | 
| [ETH-Services](https://www.eth-services.de/) | https://opennic1.eth-services.de:853/ | :heavy_check_mark: | Run by Germany hosting company
|eweyo|https://eweyo.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|[Extrawdw](https://extrawdw.net/)|https://dns.extrawdw.net/dns-query|:heavy_check_mark:|Adblocking
|eyecay.xyz|https://fra1.eyecay.xyz/dns-query|:heavy_check_mark:|Adblocking
| **F**
| [FAELIX](https://faelix.net/) | https://rdns.faelix.net/ <br> Adblocking: https://pdns.faelix.net/ | :heavy_check_mark: <br> :heavy_check_mark: | No logging, based on dnsdist-doh RC querying our powerdns-recursor resolvers, multiple nodes in UK and CH, [more info](https://faelix.net/ref/dns/#resolving-nameservers) |
|[Familia](https://familiamv.ml/)|https://dnsvps.familiamv.ml/dns-query|:heavy_check_mark:|Adblocking
|familiamichels.com.br|https://dns.familiamichels.com.br/dns-query|:heavy_check_mark:|Ad & porn blocking
| Fancyorg.at | https://dns.fancyorg.at/dns-query |  :heavy_check_mark: | Adblocking
|fatucloud.gosprout.org|https://ociamd1.fatucloud.gosprout.org/dns-query|:heavy_check_mark:|Adblocking
|faze.dev|https://dns.faze.dev/dns-query|:heavy_check_mark:|Adblocking
|feiyuyu.net|https://dns.feiyuyu.net/dns-query|:heavy_check_mark:|Adblocking
|felipefalcao|https://felipefalcao.me/dns-query|:heavy_check_mark:|Ad & porn blocking
|[ff0x](https://ff0x.ca/)|https://ag.ff0x.ca/dns-query|:heavy_check_mark:|Adblocking
| [ffmuc.net](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | https://doh.ffmuc.net/dns-query | :heavy_check_mark:| DoH-Server of Freifunk München. No logging, no filter, DNSSEC, own recursion. More in our [wiki](https://ffmuc.net/wiki/doku.php?id=knb:dohdot_en) | 
|[FilipCCz.eu](https://filipccz.eu/)|https://dns.filipccz.eu/dns-query|:heavy_check_mark:|Adblocking
|findmethedns|https://findmethedns.info/dns-query|:heavy_check_mark:|Adblocking
|firestrike-services.de|https://adguard.firestrike-services.de/dns-query|:heavy_check_mark:|Adblocking
| Flm9.net | https://dns01.flm9.net/dns-query |  :heavy_check_mark: |
| [floDNS](https://www.flodns.com/get-started/) | https://ns1.flodns.net/dns-query <br> https://ns2.flodns.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | All queries are logged for statistical analysis by [TalkDNS](https://www.talkdns.com/)
|[Florian Stosse](https://harvester.fr/)|https://dns.harvester.fr/dns-query|:heavy_check_mark:|Adblocking
|flymc.cc|https://dns.flymc.cc/dns-query|:heavy_check_mark:|Adblocking
|[fmipauns](https://mipauns.com/)|https://dns.mipauns.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|fomichev.cloud|https://gateway.fomichev.cloud/dns-query|:heavy_check_mark:|Adblocking
| [Foundation for Applied Privacy](https://applied-privacy.net) | https://doh.applied-privacy.net/query | :heavy_check_mark:| No query/IP logging, no filtering, QNAME minimization, no EDNS client subnet, TLS 1.3, DNSSEC, RFC7706, RFC8198; https://applied-privacy.net/services/dns/ |
| [Frank Ruan](https://frank-ruan.com/) | https://dns.frank-ruan.com/dns-query | :heavy_check_mark: | Adblocking
|frankslabs.org|https://dns.frankslabs.org/dns-query|:heavy_check_mark:|Adblocking
|frece.de|https://adguard.frece.de/dns-query|:heavy_check_mark:|Adblocking
|free.svipss.top|https://ds.free.svipss.top/dns-query|:heavy_check_mark:|Ad & porn blocking
|freeboxos.fr|https://pcornet.freeboxos.fr/dns-query|:heavy_check_mark:|Adblocking
|[freegod.ml](https://freegod.ml/)|https://doh.freegod.ml/dns-query|:heavy_check_mark:|Adblocking
|[Freequensi](https://freequensi.com/)|https://dns.freequensi.com/dns-query|:heavy_check_mark:|Adblocking
|frontpace.co.uk|https://frontpace.co.uk/dns-query|:heavy_check_mark:|Adblocking
| [Froth.zone](https://dns.froth.zone/resolver) | https://dns.froth.zone/dns-query | :heavy_check_mark: | OpenNIC
| Fuchur | https://fuchur.pentament.de/dns-query | :heavy_check_mark: |
| Funil.de | https://doh.funil.de/dns-query | :heavy_check_mark: |
| Funtopia.tv | https://doh.funtopia.tv/dns-query | :heavy_check_mark: | Adblocking
| [FutaDNS](https://site.futa.gg/) | https://doh.futa.gg/dns-query | :heavy_check_mark: | Based in Taiwan, query logged for 24 hours, adblocking.
|[FuzzyNG](https://khanhtran.me/)|https://dns.khanhtran.me/dns-query|:heavy_check_mark:|Adblocking
| **G**
|gando.fr|https://dns.gando.fr/dns-query|:heavy_check_mark:|Adblocking
|gbrossi.com.br|https://adguard.gbrossi.com.br/dns-query|:heavy_check_mark:|Adblocking
|gclouddns|https://gclouddns.com/dns-query|:heavy_check_mark:|Adblocking
|ggdns.club|https://ggdns.club/dns-query|:heavy_check_mark:|Adblocking
|ggrbb.xyz|https://www.ggrbb.xyz/dns-query|:heavy_check_mark:|Adblocking
|[Gho$t](https://ghost.pm/)|https://dns.ghost.pm/dns-query|:heavy_check_mark:|Adblocking
| Ginovs.nl | https://dns.ginovs.nl/dns-query | :heavy_check_mark: | Adblocking
| [Gnb09](https://www.gnb09.id/) | https://dns.gnb09.id/dns-query | :heavy_check_mark: | Ad & porn blocking
|goitoi|https://goitoi.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [Goodbye Gambling](https://goodbyegambling.com) | https://doh-primary-pool.goodbyegambling.com/dns-query | :heavy_check_mark: | Block ads and gambling
| [Google](https://developers.google.com/speed/public-dns/docs/doh) | https://dns.google/dns-query <br> DNS64: https://dns64.dns.google/dns-query <br> https://8888.google/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Full RFC 8484 support, EDNS, no filtering.
|grantbruneau.com|https://adguard.grantbruneau.com/dns-query|:heavy_check_mark:|Adblocking
|groupy.ga|https://groupy.ga/dns-query|:heavy_check_mark:|Adblocking
| Grqu.de | https://dns.grqu.de/dns-query | :heavy_check_mark: | Adblocking
|gslb2.xfinity.com|https://doh2.gslb2.xfinity.com/dns-query|:heavy_check_mark:|
|[GugaInfo](https://gugainfo.com.br/)|https://blackhole.gugainfo.com.br/dns-query|:heavy_check_mark:|Adblocking
|gunag|https://gunag.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|guoyingwei.top|https://www.guoyingwei.top/dns-query|:heavy_check_mark:|Adblocking
|gusald|https://gusald.com/dns-query|:heavy_check_mark:|Adblocking
|gustamadh|https://gustamadh.dynv6.net/dns-query|:heavy_check_mark:|Adblocking
| [Gustavus Adolphus College](https://gustavus.edu/) | https://cluster-0.gac.edu/dns-query <br> https://cluster-1.gac.edu/dns-query | :heavy_check_mark: <br> :heavy_check_mark:| 
|gztech|https://gztech.me/dns-query|:heavy_check_mark:|Adblocking
| **H**
| ha-dvin.pp.ua | https://dns.ha-dvin.pp.ua/dns-query | :heavy_check_mark: | Adblocking
| [HafidzRadhivalDNS](https://server.hafidzradhival.my.id/) | https://dns.hafidzradhival.my.id/dns-query | :heavy_check_mark: |
| hakutakucn | https://dns.hakutakucn.com/dns-query | :heavy_check_mark: | Adblocking 
| [HaNeulo](https://haneulo.com/) | https://adguard.haneulo.com/dns-query | :heavy_check_mark: | Adblocking
| Hanmey.de | https://dns.hanmey.de/dns-query | :heavy_check_mark: | Adblocking
|haoxuan.xyz|https://dns.haoxuan.xyz/dns-query|:heavy_check_mark:|Adblocking
|harrache.info|https://dns.harrache.info/dns-query|:heavy_check_mark:|Adblocking
|harriganhome.ga|https://hgns.harriganhome.ga/dns-query|:heavy_check_mark:|Adblocking
| [HDNS](https://docs.namebase.io/guides-1/resolving-handshake-1/hdns.io) | https://query.hdns.io/dns-query | :heavy_check_mark: | Also resolve Handshake domains
| [HeliumCloud](https://servers.opennic.org/edit.php?srv=ns2.nj.us.dns.opennic.glue) | https://us-ny-alula.heliumcloud.cc/dns-query | :heavy_check_mark: | OpenNIC
|[Herkhof](https://herkhof.nl/)|https://dns.herkhof.nl/dns-query|:heavy_check_mark:|Adblocking
|[heronet](https://heronet.nl/)|https://ad1.heronet.nl/dns-query|:heavy_check_mark:|Adblocking
| Himedns | https://himedns.com/dns-query | :heavy_check_mark: | Adblocking
| [Hinet](https://hinet.net/) | https://dns.hinet.net/dns-query | :heavy_check_mark: | Run by Taiwanese ISP
| [hitian.me](https://hitian.me/) | https://hitian.me/dns-query | :heavy_check_mark: | Hosted in Singapore
|hm3.day|https://jp.hm3.day/dns-query|:heavy_check_mark:|
| [Hoerli.NET](https://hoerli.net/hoerlis-pi-holes-fuers-internet/) | Falkenstein <br> https://pihole1.hoerli.net/dns-query <br> Frankfurt <br> https://pihole2.hoerli.net/dns-query <br> New Jersey <br> https://pihole3.hoerli.net/dns-query <br> Baden-Baden <br> https://pihole4.hoerli.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Adblocking, no logging
|home.dlinkddns.com|https://home.dlinkddns.com/dns-query|:heavy_check_mark:|Adblocking
|home27|https://home27.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|hooliganska|https://hooliganska.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|hoover.eu.org|https://doh-dns.hoover.eu.org/dns-query|:heavy_check_mark:|Adblocking
|[hopper.org.uk](https://hopper.org.uk/)|https://dns.hopper.org.uk/dns-query|:heavy_check_mark:|Adblocking
| [Hostux.net](https://dns.hostux.net) |  Uncensored DNS: <br> https://dns.hostux.net/dns-query <br> Adblocking DNS: <br> https://dns.hostux.net/ads | :heavy_check_mark: <br> :heavy_check_mark: |DNSSEC, no EDNS Client-Subnet, not logging queries' content, hosted in Luxembourg.
| Hotta.page | https://dns.hotta.page/dns-query | :heavy_check_mark: | Adblocking
| Hottis.de | https://doh.hottis.de/dns-query | :heavy_check_mark: | Adblocking
|[Howard Luan](https://luan.contact/)|https://dns1.luan.contact/dns-query|:heavy_check_mark:|Adblocking
| Huque | https://doth.huque.com/dns-query | :heavy_check_mark: | 
| [Hurricane Electric (he.net)](https://he.net)  | https://ordns.he.net/dns-query | :heavy_check_mark:| Also supports DoT and TLS 1.3, Does NOT support DNSSEC. Anycast servers. |
| **I**
| [i2pd](https://opennic.i2pd.xyz/) | https://opennic.i2pd.xyz/dns-query | :heavy_check_mark: | OpenNIC
| [ibksturm](https://ibksturm.synology.me/?p=33) | https://ibksturm.synology.me/dns-query | :heavy_check_mark: | Adblocking
|ibytex.systems|https://muc-ns01.ibytex.systems/dns-query|:heavy_check_mark:|
|[ihatemy.live](https://ihatemy.live/)|https://adguard.ihatemy.live/dns-query|:heavy_check_mark:|Adblocking
| ihaveacloud | https://dns.ihaveacloud.com/dns-query | :heavy_check_mark: | Adblocking
| ihctw | https://ihctw.synology.me/dns-query | :heavy_check_mark: | Adblocking
|ikataruto.com|https://dns.ikataruto.com/dns-query|:heavy_check_mark:|Adblocking
| [iKuuu VPN](https://ikuuu.co/) | https://doh.buzz/dns-query <br> https://doh.beauty/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | 
|imaicool.com|https://dns.imaicool.com/dns-query|:heavy_check_mark:|Adblocking
| [In-Berlin](https://www.in-berlin.de/) | https://dns1.in-berlin.de/dns-query | :heavy_check_mark: |
| Indus.me | https://dns.indust.me/dns-query | :heavy_check_mark: | 
| [Infotek](http://infotek.net.id/dns/) | https://doh.infotek.net.id:3443/dns-query | :heavy_check_mark: | Compliant with Indonesia censorship
|instadart.net|https://premiumtier-network.instadart.net/dns-query|:heavy_check_mark:|Adblocking
| [Institut national de recherche en sciences et technologies du numérique](https://www.inria.fr/fr) | https://qlf-doh.inria.fr/dns-query | :heavy_check_mark: |
| [Institute of Operating Systems and Computer Networks](https://wiki.ibr.cs.tu-bs.de/en/services) | https://doh.ibr.cs.tu-bs.de/dns-query | :heavy_check_mark: |
| [Inter-University Computation Center](https://www.iucc.ac.il/en/) | https://doh.iucc.ac.il/dns-query | :heavy_check_mark: |
| [Internet Initiative Japan](https://public.dns.iij.jp/) | https://public.dns.iij.jp/dns-query | :heavy_check_mark: | Planned to run until March 2024 
|interop.link|https://intertop.link/dns-query|:heavy_check_mark:|Adblocking
| [Invisv](https://invisv.com/articles/dns.html) | https://dns.invisv.com/dns-query | :heavy_check_mark: | Implements Oblivious DNS
| [IPv6DNS](https://www.ipv6dns.com/index) | https://dns.ipv6dns.com/dns-query | :heavy_check_mark: |
| Irre.li | https://irre.li/dns-query | :heavy_check_mark: | Adblocking
|[Iruma Technology](https://irumatech.com/)|https://dns1.irumatech.com/dns-query|:heavy_check_mark:|Adblocking
|[isteal](https://isteal.info/)|https://dns.isteal.info/dns-query|:heavy_check_mark:|Adblocking
|[IT Нинзя](https://iamninja.ru/)|https://dns.iamninja.ru/dns-query|:heavy_check_mark:|Ad & porn blocking
|[ITCOSC](https://itcosc.com/)|https://dns.itcosc.com/dns-query|:heavy_check_mark:|
|itdept.pro|https://dns.itdept.pro/dns-query|:heavy_check_mark:|Adblocking
|[ItsPig](https://pigs.eu.org/)|https://kr.pigs.eu.org/dns-query|:heavy_check_mark:|Adblocking
| **J**
| [Jabber Germany](https://jabber-germany.de/) | https://jabber-germany.de/dns-query | :heavy_check_mark: | Part of OpenNIC project
|jabber-server.de|https://jabber-server.de/dns-query|:heavy_check_mark:|Adblocking
| Jackyes.ovh | https://jackyes.ovh/dns-query | :heavy_check_mark: | Adblocking
|jamesxue.xyz|https://tj.jamesxue.xyz/dns-query|:heavy_check_mark:|
|[jammerxd](https://jammerxd.dev/)|https://xyz2.jammerxd.dev/dns-query|:heavy_check_mark:|Adblocking
| [JeroenHD](https://jeroenhd.nl/) | https://doh.jeroenhd.nl/dns-query | :heavy_check_mark: | Adblocking
| Jfchenier.ca | https://adguard.jfchenier.ca/dns-query | :heavy_check_mark: | Adblocking
|[Jimi Robaer](https://jimirobaer.be/)|https://dns.jimirobaer.be/dns-query|:heavy_check_mark:|Adblocking
|[Jiří Počta](https://jiripocta.cz/)|https://srv5.jiripocta.cz/dns-query|:heavy_check_mark:|Adblocking
|jjm.asia|https://jjm.asia/dns-query|:heavy_check_mark:|Adblocking
|jkdns|https://jkdns.me/dns-query|:heavy_check_mark:|Adblocking
|jnorton.us|https://adg.jnorton.us/dns-query|:heavy_check_mark:|Adblocking
|joaofidelix.com.br|https://dns.joaofidelix.com.br/dns-query|:heavy_check_mark:|Adblocking
| [Jonas Hahnfeld](https://www.hahnjo.de/) | https://dns.hahnjo.de/dns-query | :heavy_check_mark: |
|josephyap.me|https://adguard.josephyap.me/dns-query|:heavy_check_mark:|Adblocking
| [jp.tiar.app](https://jp.tiar.app/) | https://jp.tiar.app/dns-query <br> https://jp.tiarap.org/dns-query | :heavy_check_mark: | No Censorship, No Logging, No ECS, support DNSSEC in Japan |
|jpjb.net|https://adguard.jpjb.net/dns-query|:heavy_check_mark:|Adblocking
|jsanagustin.net|https://adguard1.jsanagustin.net/dns-query|:heavy_check_mark:|Adblocking
|[Jucker Software Engineering](https://jucker.engineering/)|https://dns.jucker.engineering/dns-query|:heavy_check_mark:|Adblocking
|jurre-home|https://jurre-home.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| **K**
| [K0RAP](https://k0rap.com/) | https://adguard.k0rap.com/dns-query | :heavy_check_mark: | Adblocking
| [Kamil Szczepański](https://kamilszczepanski.com/) | https://dns.kamilszczepanski.com/dns-query | :heavy_check_mark: | Adblocking
|kano.sh|https://jp.kano.sh/dns-query|:heavy_check_mark:|
|kapuyhome.hu|https://adguard1.kapuyhome.hu/dns-query|:heavy_check_mark:|Adblocking
|karimdns|https://karimdns.com/dns-query|:heavy_check_mark:|Adblocking
|[Karl.ONE](https://karl.one/)|https://dns.karl.one/dns-query|:heavy_check_mark:|Adblocking
| [Kawa.tf](https://servers.opennicproject.org/edit.php?srv=ns2.fr.dns.opennic.glue) | https://dns.kawa.tf/dns-query | :heavy_check_mark: | Hosted in Strasbourg, France
|keithchung|https://keithchung.hopto.org/dns-query|:heavy_check_mark:|Adblocking
|kennethhuang|https://kennethhuang.com/dns-query|:heavy_check_mark:|Adblocking
|kenzohost.de|https://adguard.kenzohost.de/dns-query|:heavy_check_mark:|Adblocking
| [Kernel-error](https://www.kernel-error.de/2022/03/18/bind-9-18-mit-doh-und-dot/) | https://dns.kernel-error.de/dns-query | :heavy_check_mark: |
|[kescher.at](https://kescher.at/)|https://kudns.kescher.at/dns-query|:heavy_check_mark:|
| [kescherDNS](https://dns.kescher.at/) | https://dns.kescher.at/dns-query | :heavy_check_mark: | Non-logging, hosted in Vienna and Düsseldorf
| Killtw.im | https://doh.killtw.im/dns-query | :heavy_check_mark: | Adblocking
|[Kishore](https://avdkishore.dev/)|https://adguard.avdkishore.dev/dns-query|:heavy_check_mark:|
|kngnet.de|https://adguard.kngnet.de/dns-query|:heavy_check_mark:|Adblocking
|korks.tk|https://adguard.korks.tk/dns-query|:heavy_check_mark:|Adblocking
|korzhov|https://korzhov.dev/dns-query|:heavy_check_mark:|Adblocking
| [Kosan](https://kosan.moe/) | https://dns.kosan.moe/dns-query | :heavy_check_mark: | Adblocking
|koshonsa.fr|https://adguard.koshonsa.fr/dns-query|:heavy_check_mark:|Adblocking
|kpsn.org|https://dart.kpsn.org/dns-query|:heavy_check_mark:|Adblocking
|kr.chavy.dev|https://dns.kr.chavy.dev/dns-query|:heavy_check_mark:|
|[KREONET](https://kreonet.net/)|https://adns.kreonet.net/dns-query|:heavy_check_mark:|Adblocking
| Krnl.eu | https://xray.krnl.eu/dns-query | :heavy_check_mark: | Adblocking
|[Kroginski Fotografie](https://magic-pics.tk/)|https://guard.magic-pics.tk/dns-query|:heavy_check_mark:|
|krtekvpn|https://krtekvpn.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| Kswro | Adblocking: https://kswro.web.id/dns-query <br> Ad & porn blocking: https://safe.kswro.web.id/dns-query | :heavy_check_mark: |
| **L**
| [La Contre-Voie](https://lacontrevoie.fr/en/services/doh/) | https://doh.lacontrevoie.fr/dns-query | :heavy_check_mark: | Supports DNSSEC and IPv6, not logging queries' content, uses [unbound](https://github.com/NLnetLabs/unbound/). Commits for net neutrality, hosted in France.
| [Lars Lehmn](https://larsl.net/services/dns/) | https://dns.lars-lehmann.net/dns-query | :heavy_check_mark: | Based in Germany, [privacy policy](https://larsl.net/privacy-policy/)
| [Lastentarvike](https://lastentarvike.fi) | https://lastentarvike.fi/dns-query | :heavy_check_mark: |
|[Lauren Laufman](https://laurenlaufman.com/)|https://adguard.laurenlaufman.com/dns-query|:heavy_check_mark:|Adblocking
| [LavaDNS](https://dns.lavate.ch/) | Finland: https://eu1.dns.lavate.ch/dns-query | :heavy_check_mark: | DoH server in Finland. No logging, no filtering, no ECS, DNSSEC support. |
|leadmon.net|https://adguard1.leadmon.net/dns-query|:heavy_check_mark:|
|leecurrylawfirm|https://leecurrylawfirm.com/dns-query|:heavy_check_mark:|Adblocking
|lege.despagne.net|https://adguard.lege.despagne.net/dns-query|:heavy_check_mark:|Adblocking
|lekdijk.online|https://externalmobiel.lekdijk.online/dns-query|:heavy_check_mark:|
| [LibreDNS](https://libredns.gr/) | Non-filtering https://doh.libredns.gr/dns-query <br> Adblocking https://doh.libredns.gr/ads  | :heavy_check_mark: <br> :heavy_check_mark: | no logging, TLS 1.3, No DNSSEC |
| Lightmaster.pw | https://dns.lightmaster.pw/dns-query | :heavy_check_mark: | Adblocking
|lightmaster.space|https://dns.lightmaster.space/dns-query|:heavy_check_mark:|Adblocking
| [Limo Telu](https://www.limotelu.org/) | https://sby-doh.limotelu.org/dns-query | :heavy_check_mark: | No logging, DNSSEC, query minimization and prefetch, based in Surabaya, Indonesia
| [Lindung](https://lindung.pp.ua/) | Adblocking: https://lindung.pp.ua/dns-query <br> Ad & porn blocking: https://lindung.pp.ua/family | :heavy_check_mark: <br> :heavy_check_mark: |
|[lingmont.net](https://lingmont.net/)|https://adgaurd.lingmont.net/dns-query|:heavy_check_mark:|Adblocking
|lrdnet.cf|https://dns.lrdnet.cf/dns-query|:heavy_check_mark:|Adblocking
|[LS COMPUTER REPAIR](https://lspcr.space/)|https://adguard.lspcr.space/dns-query|:heavy_check_mark:|Adblocking
|lujiacai.top|https://doh.lujiacai.top/dns-query|:heavy_check_mark:|Adblocking
|lululu|https://doh.lululu.eu.org/dns-query|:heavy_check_mark:|Adblocking
|lz0724.com|https://orau.lz0724.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| **M**
|maddino|https://maddino.dedyn.io/dns-query|:heavy_check_mark:|Adblocking
|mailchan.eu|https://dnsserver.mailchan.eu/dns-query|:heavy_check_mark:|Adblocking
|malwarelul.download|https://dns.malwarelul.download/dns-query|:heavy_check_mark:|Ad & porn blocking
|[maolaohei.xyz](https://maolaohei.xyz)|https://dns.maolaohei.xyz/dns-query|:heavy_check_mark:|Adblocking
|marcbond.uk|https://dns.marcbond.uk/dns-query|:heavy_check_mark:|Adblocking
| [Masters of Cloud](https://www.masters-of-cloud.de/) | https://masters-of-cloud.de/dns-query | :heavy_check_mark: | 
| [Matteus Legat](https://legat.ml/) | https://br.servers.legat.ml/dns-query | :heavy_check_mark: | Adblocking
|mcasviper.de|https://doh.mcasviper.de/dns-query|:heavy_check_mark:|Adblocking
|me7878.com|https://dns.me7878.com/dns-query|:heavy_check_mark:|Adblocking
|meddy94.de|https://adguard.meddy94.de/dns-query|:heavy_check_mark:|Adblocking
| Meeo.win | https://dns.meeo.win/dns-query | :heavy_check_mark: | Adblocking
| [MegaNerd](https://meganerd.nl/encrypted-dns-server) | https://chewbacca.meganerd.nl/dns-query | :heavy_check_mark: | No logging, no filtering, DNSSEC, based in the Netherlands
|meidouling.com|https://jp3.meidouling.com/dns-query|:heavy_check_mark:|Adblocking
| Meshkov.info | https://testaghome.meshkov.info/dns-query | :heavy_check_mark: | Adblocking
|mgiptvpro.ml|https://dns.mgiptvpro.ml/dns-query|:heavy_check_mark:|Adblocking
|mhsystems.net|https://securenet.mhsystems.net/dns-query|:heavy_check_mark:|Adblocking
|mikeliu.org|https://dns.mikeliu.org/dns-query|:heavy_check_mark:|Adblocking
| [Minh Truong](https://truong.fi/) | https://dns.truong.fi/dns-query | :heavy_check_mark: | Adblocking
|mirandil.ru|https://dns.mirandil.ru/dns-query|:heavy_check_mark:|Adblocking
|[mjanson.de](https://mjanson.de/)|https://adguard.mjanson.de/dns-query|:heavy_check_mark:|Adblocking
| [Mobik](https://www.mobik.com/) | https://dnstls.mobik.com/dns-query | :heavy_check_mark: |
|[modr.club](https://modr.club/)|https://ps1.modr.club/dns-query|:heavy_check_mark:|
|[Mokocup](https://mokocup.cf/)|https://adguard.mokocup.cf/dns-query|:heavy_check_mark:|Adblocking
| [Molinero](https://molinero.dev/) | https://dns.molinero.dev/dns-query | :heavy_check_mark: | Adblocking
| [Monzoon](https://www.monzoon.net/) | https://zrh1-ns01.monzoon.net/dns-query | :heavy_check_mark: |
|moog.sh|https://dns.moog.sh/dns-query|:heavy_check_mark:|Ad & porn blocking
|moonssif.com|https://dns.moonssif.com/dns-query|:heavy_check_mark:|Adblocking
| [Morbitzer](https://morbitzer.de/) | https://www.morbitzer.de/dns-query | :heavy_check_mark: | 
|mrcapslock|https://mrcapslock.ir/dns-query|:heavy_check_mark:|Adblocking
|msr177|https://msr177.com/dns-query|:heavy_check_mark:|Adblocking
|[msxnet.ru](https://msxnet.ru/)|https://dns.msxnet.ru/dns-query|:heavy_check_mark:|Adblocking
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | Non-blocking https://doh.mullvad.net/dns-query <br> Adblocking https://adblock.doh.mullvad.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Public DoH server in AU, US, DE, GB, SG, and SE with QNAME minimization, audited by [Assured](https://www.assured.se/wp-content/uploads/2021/03/Assured_Mullvad_DoH_server_audit_report.pdf)
|[MULTIMEDIA CONCEPT](https://multimediaconcept.fr/)|https://blockerads.multimediaconcept.fr/dns-query|:heavy_check_mark:|Adblocking
|mulu.at|https://adguard.mulu.at/dns-query<br>https://pihole.mulu.at/dns-query|:heavy_check_mark:<br>:heavy_check_mark:|Adblocking
| [murgi.de](https://www.murgi.de/) | https://dns.murgi.de/dns-query | :heavy_check_mark: | Adblocking
|muxinghe.cn|https://dns.muxinghe.cn/dns-query|:heavy_check_mark:|Adblocking
|muxyuji.ru|https://www.muxyuji.ru/dns-query|:heavy_check_mark:|Adblocking
|my.to|https://lf-ns-001.my.to/dns-query|:heavy_check_mark:|Adblocking
|[MyFRITZ](https://myfritz.net/)|https://echoe1yidzu4ioo5.myfritz.net/dns-query|:heavy_check_mark:|Adblocking
|myhottiemama|https://myhottiemama.de/dns-query|:heavy_check_mark:|Adblocking
| Myon | https://blackhole.myon.lu/dns-query | :heavy_check_mark: | Adblocking
|mytm.cc|https://vm.mytm.cc/dns-query|:heavy_check_mark:|Adblocking
|mywire.org|https://area51.mywire.org/dns-query|:heavy_check_mark:|Adblocking
|mzrme.cn|https://dns.mzrme.cn/dns-query|:heavy_check_mark:|
| **N**
|n-wan|https://n-wan.dynv6.net/dns-query|:heavy_check_mark:|Adblocking
|n23.io|https://dns.n23.io/dns-query|:heavy_check_mark:|Adblocking
|n3120.wang|https://dns1.n3120.wang/dns-query|:heavy_check_mark:|Adblocking
| [NALA ru](http://nala.ru/) | https://doh.nala.ru/dns-query | :heavy_check_mark: |
|nas-server.ru|https://dns.nas-server.ru/dns-query|:heavy_check_mark:|Adblocking
|nas1403|https://nas1403.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [ndom91](https://ndo.dev/posts/doh) | https://dns.ndo.dev/dns-query | :heavy_check_mark: | Non-logging, adblocking, ECS disabled, QNAME minimization, recursive resolver through Unbound with DNSSEC.
| [Ndr](https://ender.fr/) | https://adguard.ender.fr/dns-query | :heavy_check_mark: | Adblocking
| [Nebula.sly.io](https://nebula.sly.io) | Adblocking https://nebula.sly.io/dns-query <br> Adblocking & porn blocking https://nebula.sly.io/porn | :heavy_check_mark: <br> :heavy_check_mark: | Server in Japan
|[neocortex.dk](https://norvig.dk/)|https://dns.norvig.dk/dns-query|:heavy_check_mark:|Adblocking
|nerdpol.ovh|https://levislondon-proxy.nerdpol.ovh/dns-query|:heavy_check_mark:|Adblocking
|[Neubsi](https://dns.neubsi.at/)|https://dns.neubsi.at/dns-query|:heavy_check_mark:|
| Nexific.it | https://doh.luigi.nexific.it/dns-query | :heavy_check_mark:|
| [NextDNS](https://nextdns.io) | https://dns.nextdns.io | :heavy_check_mark: | The first cloud-based private DNS service that gives you full control over what is allowed and what is blocked on the Internet. 300,000 domain resolution per month is free with non-filtering afterward until the end of the month. Granular dashboard, Each account can create multiple configurations, which can be used for multiple devices with prefixes to track activities on the dashboard. [Create a config ID](https://my.nextdns.io/start)
|[Nguyễn Hữu Gia Ân](https://giaan.org/)|https://dns-primary.giaan.org/dns-query|:heavy_check_mark:|Adblocking
| Nhtsky | https://dns.nhtsky.com/dns-query | :heavy_check_mark: | Adblocking
| [NIC.LV](https://doh.lv/) | https://doh.lv/dns-query <br> https://doh.nic.lv/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Run by .lv TLD registry 
| [Nielsvoorn](https://nielsvoorn.nl) | https://adguard.nielsvoorn.nl/dns-query | :heavy_check_mark: | Adblocking
|ninny|https://ninny.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [NiYaWe](https://www.niyawe.de/) | https://doh.niyawe.de/dns-query | :heavy_check_mark: |
| [Njalla](https://dns.njal.la/) | https://dns.njal.la/dns-query | :heavy_check_mark: | Non logging, based in Sweden
| [No Ad DNS](https://noaddns.com/) | https://resolver.noaddns.com/dns-query | :heavy_check_mark: | Adblocking
| [Node15](https://node15.com/) | https://pi1.node15.com/dns-query | :heavy_check_mark: | Block ads and porn
|[nolo.ltd](https://nolo.ltd/)|https://sink.nolo.ltd/dns-query|:heavy_check_mark:|Adblocking
|nongdanthanky|https://nongdanthanky.com/dns-query|:heavy_check_mark:|Adblocking
|[Norgan Networks](https://norgan.net/)|https://dns.norgan.net/dns-query|:heavy_check_mark:|Adblocking
|notecore|https://notecore.me/dns-query|:heavy_check_mark:|Adblocking
|[novali.date](https://novali.date/)|https://dns.novali.date/dns-query|:heavy_check_mark:|Adblocking
| [Novg.net](https://novg.net/) | https://dns.novg.net/dns-query | :heavy_check_mark: | Adblocking
|[ns](https://n5.lsasss.com/)|https://n5.lsasss.com/dns-query|:heavy_check_mark:|Adblocking
|NS3|https://dns8.org/dns-query<br>https://n0.eu/dns-query<br>https://ns3.com/dns-query<br>https://ns3.cx/dns-query<br>https://ns3.link/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|
| Nsc.torgues.net | https://nsc.torgues.net/dns-query | :heavy_check_mark: | Adblocking
| Nullgate.net | https://dns.nullgate.net/dns-query | :heavy_check_mark: | Adblocking
|[nullrecon.com](https://nullrecon.com/)|https://dns.nullrecon.com/dns-query|:heavy_check_mark:|Adblocking
| **O**
|o1lt|https://o1.lt/dns-query|:heavy_check_mark:|Adblocking
|[ofdoom.net](https://ofdoom.net/)|https://dns.ofdoom.net/dns-query|:heavy_check_mark:|Adblocking
|[Ondřej Šrámek](https://ondrejsramek.cz/)|https://adguard.ondrejsramek.cz/dns-query|:heavy_check_mark:|Ad & porn blocking
|[OneDNS.cc](https://onedns.cc/)|https://secure.onedns.cc/dns-query|:heavy_check_mark:|Adblocking
|[OneDNS.net](https://onedns.net/)|https://doh.onedns.net/dns-query|:heavy_check_mark:|
| Ooroot | https://jp2.ooroot.com/dns-query <br> https://sg2.ooroot.com/dns-query <br> https://hk2.ooroot.com/dns-query <br> https://tw2.ooroot.com/dns-query <br> https://kr1.ooroot.com/dns-query <br> https://kr2.ooroot.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: |
| [Open BLD DNS](https://lab.sys-adm.in/) | Adapted : https://a-bld.sys-adm.in/dns-query <br> Balanced : https://bld.sys-adm.in/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Block ads and trackers
|[OpenLoop Health](https://apollohct.com/)|https://ag.apollohct.com/dns-query|:heavy_check_mark:|Adblocking
| [opennameserver.org](https://opennameserver.org/) | Baden-Baden https://ns1.opennameserver.org/dns-query <br> Frankfurt https://ns2.opennameserver.org/dns-query <br> Sandefjord https://ns4.opennameserver.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | DNSSEC, non-logging, OpenNIC 
|[opnsource.com.au](https://opnsource.com.au/)|https://dns.opnsource.com.au/dns-query|:heavy_check_mark:|Adblocking
|osefcorp|https://osefcorp.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [Ozérim](https://ozer.im/) | https://1a.ns.ozer.im/dns-query | :heavy_check_mark: | Adblocking
| **P**
| [PaesaDNS](https://milgradesec.github.io/paesadns/) | https://dns.paesa.es/dns-query | :heavy_check_mark: | Adblocking
|[PanSzelescik](https://panszelescik.pl/)|https://dns.panszelescik.pl/dns-query|:heavy_check_mark:|Adblocking
| Path of Grace | https://doh.gcp.pathofgrace.com/dns-query | :heavy_check_mark: | Adblocking
|piekacz.pl|https://adguard.piekacz.pl/dns-query|:heavy_check_mark:|
|pitnetdns|https://pitnetdns.ga/dns-query|:heavy_check_mark:|Adblocking
| [Plan9-dns](https://jlongua.github.io/plan9-dns/) | New Jersey : https://kronos.plan9-dns.com/dns-query <br> Florida : https://pluton.plan9-dns.com/dns-query <br> Mexico : https://helios.plan9-dns.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted on Vultr
|pleumkungz.com|https://thanos.pleumkungz.com/dns-query|:heavy_check_mark:|Adblocking
| Pope.cnblw.me | https://pope.cnblw.me/dns-query | :heavy_check_mark: | Adblocking
| Port53.dk | https://doh.port53.dk/dns-query | :heavy_check_mark: | Adblocking
|porteii|https://dns.porteii.com/dns-query|:heavy_check_mark:|Adblocking
|[PriviLab.net](https://privilab.net/)|https://dns.privilab.net/dns-query|:heavy_check_mark:|Adblocking
|project-evoex|https://project-evoex.de/dns-query|:heavy_check_mark:|Adblocking
|punono|https://punono.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [PureDNS](https://puredns.org/) | https://puredns.org/dns-query | :heavy_check_mark: | Hosted in Indonesia and Singapore
| Pyry.me | https://doh.pyry.me/dns-query | :heavy_check_mark: | Adblocking
| [Pzhg](https://pzhg.wordpress.com/) | https://vpsus3.pzhg.me/dns-query <br> https://at.pzhg.me/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Adblocking
| **Q**
|q3i6k7j3|https://q3i6k7j3.stackpathcdn.com/dns-query|:heavy_check_mark:|
| [Qihoo 360](https://360.cn) | https://doh.360.cn/dns-query | :heavy_check_mark: | Based in China
| [qquackDNS](https://qquack.org/nameserver) | https://ns1.qquack.org/dns-query | :heavy_check_mark: | Adblocking, non-logging
| [Quad9](https://www.quad9.net/doh-quad9-dns-servers/) | Recommended: https://dns.quad9.net/dns-query <br> Secured: https://dns9.quad9.net/dns-query <br> Unsecured: https://dns10.quad9.net/dns-query <br> Secured w/ECS Support: https://dns11.quad9.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Secured provides: Security blocklist, DNSSEC, no EDNS Client-Subnet <br> Unsecured provides: No security blocklist, no DNSSEC, no EDNS Client-Subnet <br> Recommend is currently identical to secure.
| [Quadrant](https://quadrantsec.com/blog/quadrants-public-dns-resolver-tls-https-support) | https://doh.qis.io/dns-query | :heavy_check_mark: | No filtering & logging
|[Quentin Stoeckel](https://quentin-stoeckel.fr/)|https://home.quentin-stoeckel.fr/dns-query|:heavy_check_mark:|
|[QWER DNS](https://dns.qwer.pw/)|https://ant.dns.qwer.pw/dns-query<br>https://dog.dns.qwer.pw/dns-query<br>https://lion.dns.qwer.pw/dns-query<br>https://tiger.dns.qwer.pw/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking
| **R**
| [R0cket](https://resolver.r0cket.net/) | https://resolver.r0cket.net/dns-query | :heavy_check_mark: | Adblocking, queries are logged and monitored when there's abuse
|[R1BNC](https://r1bnc.com/)|https://r1bnc.com/dns-query|:heavy_check_mark:|Ad & porn blocking
|[rabmoor.cz](https://rabmoor.cz/)|https://adguard.rabmoor.cz/dns-query|:heavy_check_mark:|Ad & porn blocking
| rafn.is | https://dns.rafn.is/dns-query | :heavy_check_mark: | Adblocking
|[Rahul](https://ssrahul96.xyz/)|https://ag.ssrahul96.xyz/dns-query|:heavy_check_mark:|Adblocking
|[randomaizer](https://randomaizer.lentel.ru/)|https://adguard.randomaizer.lentel.ru/dns-query|:heavy_check_mark:|Adblocking
| [Rayneau](https://rayneau.fr/) | https://rayneau.fr/dns-query | :heavy_check_mark: | Block porn and ads
| reckoningslug | https://dns.reckoningslug.name/dns-query | :heavy_check_mark: |
| [Restena](https://www.restena.lu/en/service/public-dns-resolver) | https://kaitain.restena.lu/dns-query | :heavy_check_mark: | Based in Luxembourg, DNSSEC, minimal logging for technical functions
| [RethinkDNS](https://www.rethinkdns.com/) | Non-filtering: https://basic.rethinkdns.com/dns-query <br> OISD: https://sky.rethinkdns.com/1:IAAgAA== | :heavy_check_mark: <br> :heavy_check_mark: | [An open-source stub resolver](https://github.com/serverless-dns/serverless-dns) running in 200+ locations world-wide on Cloudfare's network. Fast, secure, private, transparent, configurable DNS resolver. No ECS. Implements CNAME Cloaking. No-logs. [code](https://github.com/celzero/rethink-app). [Configure custom blocklists](https://rethinkdns.com/configure)
| [Rezhajul](https://doh.rezhajul.io/) | https://doh.rezhajul.io/dns-query | :heavy_check_mark: | No Logging, DNSSEC enabled, 1.7M+ hosts filtered (ads, tracker, malware, spam, coinminer and phising).
|[Richard Applegate](https://richardapplegate.io/)|https://adguard.richardapplegate.io/dns-query|:heavy_check_mark:|
| Rin.sh | https://dns.rin.sh/dns-query | :heavy_check_mark: |
|rjmva|https://rjmva.com/dns-query|:heavy_check_mark:|Adblocking
|[RodovaTech](https://rodovatech.com/)|https://dns.rodovatech.com/dns-query|:heavy_check_mark:|Adblocking
|[ronc.ru](https://ronc.ru/)|https://dns.ronc.ru/dns-query|:heavy_check_mark:|Adblocking
| [RoTunneling](https://www.rotunneling.net/rotunneling-doh-free/) | https://dns.rotunneling.net/dns-query/public | :heavy_check_mark: | Adblocking
|[RougaCh](https://rouga.ch/)|https://adguard-dns.rouga.ch/dns-query|:heavy_check_mark:|Adblocking
| Rubyfish.cn | https://dns.rubyfish.cn/dns-query | :heavy_check_mark: | East China Zone, Based on https://github.com/m13253/dns-over-https |
| Ryan Palmer | https://dns1.ryan-palmer.com/dns-query | :heavy_check_mark: | Hosted in UK, Non-logging, non-filtering, DNSSEC
|ryanleek.com|https://adguard.ryanleek.com/dns-query|:heavy_check_mark:|Adblocking
| **S**
| [Safe Surfer](https://safesurfer.io/) | https://doh.safesurfer.io/dns-query | :heavy_check_mark: | Filter porn sites, enforce safe search
|sagutxustech|https://sagutxustech.com/dns-query|:heavy_check_mark:|Adblocking
|[Saikat](https://rsaikat.com/)|https://o.rsaikat.com/dns-query|:heavy_check_mark:|Adblocking
| Salome | https://tuic.salome.my.id/dns-query | :heavy_check_mark: | Adblocking
|sbdns.co.in|https://sbdns.co.in/dns-query|:heavy_check_mark:|Adblocking
| [Sellan DNS](https://dns.sellan.fr/) | https://dns.sellan.fr/dns-query | :heavy_check_mark: | Adblocking, no logging
| [SFR](http://sfr.fr/) | https://pates.services.sfr.fr.casepp.sfr.fr | :heavy_check_mark: |
|sgpcloud|https://sgpcloud.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|shalenkov|https://shalenkov.dev/dns-query|:heavy_check_mark:|Adblocking
| [Shecan](https://shecan.ir/) | https://free.shecan.ir/dns-query <br> https://dns.shecan.ir/dns-query <br> https://pro.shecan.ir/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Based in Iran, proxies sanctioned websites
| [Shimul D](https://shimul.me) | https://do.shimul.me/dns-query | :heavy_check_mark: | Adblocking
|[Shimul D](https://shimul.me/)|https://dns.shimul.me/dns-query|:heavy_check_mark:|Adblocking
| [Shunhang](https://www.shimmerl.top/archives/dnsqx-ls-20-12-21) | https://dns.lsho.top:444/dns-query | :heavy_check_mark: | Adblocking
| Shuting | https://adguard.shuting.idv.tw/dns-query | :heavy_check_mark: | Adblocking
| Silen.org | https://dns.silen.org/dns-query | :heavy_check_mark: | Adblocking
|[Silentlybren](https://silentlybren.com/)|https://dns.silentlybren.com/dns-query|:heavy_check_mark:|Adblocking
|sillundil.ovh|https://dot.sillundil.ovh/dns-query|:heavy_check_mark:|Adblocking
|[Simulhost](https://simulhost.com/)|https://dns.simulhost.com/dns-query|:heavy_check_mark:|Adblocking
|siry.de|https://dns.siry.de/dns-query|:heavy_check_mark:|Adblocking
|sitdns|https://sitdns.com/dns-query|:heavy_check_mark:|Adblocking
|skrep.eu|https://dns.skrep.eu/dns-query|:heavy_check_mark:|Adblocking
| Slinkyman.net | https://dns.slinkyman.net/dns-query | :heavy_check_mark: | Adblocking
|[smilence](https://geili.me/)|https://adg.geili.me/dns-query|:heavy_check_mark:|Adblocking
| [Softcom](https://www.softcom.net/) | https://clientdns3.softcom.net/dns-query | :heavy_check_mark: |
| Southam.family | https://doh.southam.family/dns-query | :heavy_check_mark: | Adblocking
| [Spacedns](https://spacedns.org/) | https://spacedns.org/dns-query | :heavy_check_mark: | Hosted in Poland, adblocking, non-logging.
| [SPIL](https://www.spil.co.id/) | https://dns.spil.co.id/dns-query | :heavy_check_mark: | Adblocking
|srv-pro|https://resolv.srv-pro.de/dns-query|:heavy_check_mark:|Adblocking
| [Startup Stack](https://startupstack.tech/) | https://dns.startupstack.tech/dns-query | :heavy_check_mark: |
| [Steven Zhu](https://www.stevenz.blog/dns/) | https://dns.stevenz.net/dns-query | :heavy_check_mark: | Adblocking, based in the US
| [Studentenstadt Freimann](https://www.stusta.de/en/) | https://muli.stusta.mhn.de/dns-query <br> https://esel.stusta.mhn.de/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |
|stvsk.ml|https://dns.stvsk.ml/dns-query|:heavy_check_mark:|Adblocking
|[SunTrack](https://sntrk.ru/)|https://guard.sntrk.ru/dns-query|:heavy_check_mark:|Adblocking
| [Surfshark](Surfshark.com) | https://dns.surfshark.com/dns-query | :heavy_check_mark: |
|surt|https://surt.ml/dns-query|:heavy_check_mark:|Adblocking
| [SWITCH](https://www.switch.ch/security/info/public-dns/) | https://dns.switch.ch/dns-query | :heavy_check_mark: | DNSSEC validation protects from forged or manipulated DNS data from upstream servers, DNS Query Name Minimisation to improve privacy, [SWITCH DNS Firewall](https://www.switch.ch/dns-firewall/) blocks access to infected or malicious websites and redirects users to a landing page |
| [Syaifullah](https://blog.syaifullah.com/public-dns-services/) | https://dns.syaifullah.com/dns-query | :heavy_check_mark: | Adblocking
| [Syshero](https://syshero.org/) | https://doh.syshero.org/dns-query | :heavy_check_mark: | 
| **T**
| t53.de | https://dns.t53.de/dns-query | :heavy_check_mark: |
|[Tardiskhost](https://tardishost.ru/)|Adblocking: https://dns0.tardishost.ru/dns-query<br>Ad & porn blocking: https://dns1.tardishost.ru/dns-query|:heavy_check_mark:<br>:heavy_check_mark:|
|[TechCPU.NET](https://techcpu.net/)|https://dns.techcpu.net/dns-query|:heavy_check_mark:|Adblocking
|[TECHNOVUS](https://technovus.in/)|https://adblock.technovus.in/dns-query|:heavy_check_mark:|Adblocking
|[TEK411com](https://tek411.com/)|https://agp01.tek411.com/dns-query|:heavy_check_mark:|Adblocking
| [Telekom Deutschland](https://telekomhilft.telekom.de/t5/Offentliche-Tests-Umfragen/Telekom-hilft-Labor-Testet-mit-uns-DNS-over-HTTPS/m-p/5008054) | https://dns.telekom.de/dns-query | :heavy_check_mark: | 
|[teng.sh](https://teng.sh/)|https://vpn-tw.teng.sh/dns-query|:heavy_check_mark:|Adblocking
| [TeraDNS](https://teradns.org/dns-over-https/) | Germany : https://de.teradns.org/dns-query <br> New York : https://ny.teradns.org/dns-query <br> Texas : https://tx.teradns.org/dns-query <br> Singapore : https://sg.teradns.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark:| Adblocking, query logged for 24 hours to detect amplification attack.
| [TÉZOÏ](https://www.tezoi.com/) | https://cloud.tezoi.com/dns-query | :heavy_check_mark: | Adblocking
|thecremeens|https://thecremeens.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| Theres.one | https://dns.theres.one/dns-query | :heavy_check_mark: | Adblocking
| therifleman.name | https://dns.therifleman.name/dns-query | :heavy_check_mark: | Based in Mumbai, IP not logged, query logged for 24 hours, adblocking
| [Tiarap](https://doh.tiar.app) | https://doh.tiar.app/dns-query <br> https://doh.tiarap.org/dns-query | :heavy_check_mark: <br> :heavy_check_mark: |Based in Singapore, No logging, block Ad/Ad-tracking/Malware, No ECS, DNSSEC |
| Timmes.nl | https://timmes.nl/dns-query | :heavy_check_mark: | Adblocking
|tk31z|https://tk31z.com/dns-query|:heavy_check_mark:|Adblocking
| Tls-data.de | https://dns.tls-data.de/dns-query | :heavy_check_mark: |
|tlz.asia|https://tlz.asia/dns-query|:heavy_check_mark:|Adblocking
|tmkis-dns|https://tmkis-dns.de/dns-query|:heavy_check_mark:|Adblocking
|[toairs](https://toairs.com/)|https://d.toairs.com/dns-query|:heavy_check_mark:|Adblocking
|toaster.lol|https://toaster.lol/dns-query|:heavy_check_mark:|Adblocking
| [Totoro625](https://www.totoro.pub/adguardhome-conf) | https://doh.totoro.pub/dns-query/ | :heavy_check_mark: | Adblocking, based in Shanghai
|[TPM](https://apigw.online/)|https://dns.apigw.online/dns-query|:heavy_check_mark:|Adblocking
|tuandns|https://tuandns.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|[tuankhaiit](https://tuankhaiit.com/)|https://dns.tuankhaiit.com/dns-query|:heavy_check_mark:|Adblocking
|tungdnsne|https://tungdnsne.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| turker.info | https://adguard-dns.turker.info/dns-query | :heavy_check_mark: | Adblocking
| [TWNIC](https://www.twnic.net.tw/) | https://dns.twnic.tw/dns-query | :heavy_check_mark: | No source IP logging. Operated by [Quad101](https://101.101.101.101/index_en.html) project, according to this [announcement](https://blog.twnic.net.tw/2018/12/28/1803/) |
|[Tyler G. Wahl](https://tylerwahl.com/)|https://dns-east.tylerwahl.com/dns-query|:heavy_check_mark:|Adblocking
|[tyler@twtrs.com](https://twtrs.com/)|https://dns.twtrs.com/dns-query|:heavy_check_mark:|Adblocking
|typaza|https://typaza.com/dns-query|:heavy_check_mark:|Adblocking
| **U**
| Ueni.dyndns.org | https://ueni.dyndns.org/dns-query | :heavy_check_mark: | Adblocking
| Ultima Thule | https://adguard-ironhide.ultima-thule.ru/dns-query | :heavy_check_mark: | Adblocking
| [UncensoredDNS](https://blog.uncensoreddns.org/dns-servers/) | Anycast : https://anycast.uncensoreddns.org/dns-query <br> https://anycast.censurfridns.dk/dns-query <br> Denmark : https://unicast.uncensoreddns.org/dns-query <br> https://unicast.censurfridns.dk/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Non-logging, anycast on Denmark and US
| [Università di Padova](https://www.unipd.it/) | https://galileo.math.unipd.it/dns-query | :heavy_check_mark: | 
| [Universität Bremen](https://www.uni-bremen.de/zfn/weitere-it-dienste/domain-name-service-dns) | https://ines.zfn.uni-bremen.de/dns-query | :heavy_check_mark: | 
|unixfox|https://unixfox.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| [Unstoppable Domains](https://docs.unstoppabledomains.com/d-websites/resolving-dwebsites-in-a-browser/) | https://resolver.unstoppable.io/dns-query | :heavy_check_mark: | Also resolve `.crypto` TLD of Unstoppable Domains.
| [Usable Privacy](https://docs.usableprivacy.com/updns/) | https://adfree.usableprivacy.net/dns-query | :heavy_check_mark: | Public non-logging DNS server with advertising and tracker filtering, use AdAway and Peter Lowe's list |
| **V**
| [Vasili Sviridov](https://vasi.li/) | https://tor.vasi.li/dns-query | :heavy_check_mark: | 
| [Velyn DNS](https://dns.velyn.my.id/) | https://doh.velyn.my.id/dns-query | :heavy_check_mark: | Adblocking
|[vendor vista](https://vendorvista.xyz/)|https://securedns.vendorvista.xyz/dns-query|:heavy_check_mark:|Adblocking
| [VinnyP](https://dns.vinnyp.xyz/privacy) | https://dns.vinnyp.xyz/dns-query | :heavy_check_mark: | No logging, self recursive resolved, block ads, malware & porn.
| Vinokurov | https://dns.vinokurov.tk/dns-query | :heavy_check_mark: | Adblocking
| [vMath](https://www.vmath.my.id/) | https://dns.vmath.my.id/dns-query | :heavy_check_mark: | Adblocking
|[vpnRF](https://vpnrf.com/)|https://awsdns.vpnrf.com/dns-query|:heavy_check_mark:|Adblocking
|vpservice.cf|https://vpservice.cf/dns-query|:heavy_check_mark:|Adblocking
|[vvmm.me](https://vvmm.me/)|https://vvmm.me/dns-query|:heavy_check_mark:|Adblocking
| **W**
|[wakgood](https://wakgood.net/)|https://dns.wakgood.net/dns-query|:heavy_check_mark:|Adblocking
|wantaquddin|https://wantaquddin.com/dns-query|:heavy_check_mark:|Ad & porn blocking
| [WarpNine](https://warpnine.de/) | https://dns.warpnine.de/dns-query | :heavy_check_mark: | 
| [Wewitro](https://wewitro.de/) | https://doh.wewitro.net/dns-query | :heavy_check_mark: | Adblocking
|whax|https://whax.eu.org/dns-query|:heavy_check_mark:|Adblocking
| Wirimij.nl | https://adguard.wirimij.nl/dns-query | :heavy_check_mark: | Adblocking
|wns.watch|https://dns.wns.watch/dns-query|:heavy_check_mark:|Ad & porn blocking
| [Woozeno](https://iris.woozeno.eu/) | https://iris.woozeno.eu/dns-query | :heavy_check_mark: | 
| **X**
|x-o-x|https://x-o-x.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
|[x88](https://x88.in/)|https://ads.x88.in/dns-query|:heavy_check_mark:|Adblocking
| [xcom.pro](https://doh.xcom.pro/) | https://doh.xcom.pro/dns-query | :heavy_check_mark: | Adblocking
|xenergy.cc|https://xenergy.cc/dns-query|:heavy_check_mark:|Adblocking
|xthwo|https://xthwo.duckdns.org/dns-query|:heavy_check_mark:|Adblocking
| **Y**
| [Yarp](https://yarp.lefolgoc.net/) | https://yarp.lefolgoc.net/dns-query | :heavy_check_mark: <br> :heavy_check_mark: | Hosted in France, no logging.
|yazilimatolye.com|https://lion.yazilimatolye.com/dns-query|:heavy_check_mark:|Adblocking
|ychen.cf|https://ychen.cf/dns-query|:heavy_check_mark:|Adblocking
|ychen|https://ychen.ga/dns-query|:heavy_check_mark:|Adblocking
| [Yoooo](https://wyx.cloud/) | https://wyx.cloud/dns-query | :heavy_check_mark: | 
| Youni | https://dns.youni.win/dns-query | :heavy_check_mark: | Adblocking
| [your-dns](https://github.com/yegle/your-dns) | https://your-dns.run/dns-query | :heavy_check_mark: | Adblocking
|[YouRoute](https://youroute.ru/)|https://adguard.youroute.ru/dns-query|:heavy_check_mark:|Adblocking
|yovbak|https://yovbak.com/dns-query|:heavy_check_mark:|Adblocking
| ypbind.de | https://dns.ypbind.de/dns-query | :heavy_check_mark: | Adblocking
| **Z**
| [Zach Zheng](https://zachitect.com/) | https://adguard.zachitect.com/dns-query | :heavy_check_mark: | Adblocking
| Zfsystem | https://dns.zfsystem.tech/dns-query | :heavy_check_mark: | Adblocking
|zxcvb.pp.ua|https://zxcvb.pp.ua/dns-query|:heavy_check_mark:|Adblocking
| **0-9**
|0ooo.icu|https://dns.0ooo.icu/dns-query|:heavy_check_mark:|Adblocking
|0rz.space|https://1.0rz.space/dns-query|:heavy_check_mark:|Adblocking
|0rz.space|https://2.0rz.space/dns-query|:heavy_check_mark:|Adblocking
|11i.eu|https://1.11i.eu/dns-query<br>https://2.11i.eu/dns-query<br>https://3.11i.eu/dns-query|:heavy_check_mark:<br>:heavy_check_mark:<br>:heavy_check_mark:|Adblocking
|1899.com.mx|https://ns1.1899.com.mx/dns-query|:heavy_check_mark:|Adblocking
|1899.com.mx|https://ns2.1899.com.mx/dns-query|:heavy_check_mark:|Adblocking
|2025up.xyz|https://dhold.2025up.xyz/dns-query|:heavy_check_mark:|
|240130034.xyz|https://t2c.240130034.xyz/dns-query|:heavy_check_mark:|Adblocking
|[280blocker](https://doh003.280blocker.net/)|https://doh003.280blocker.net/dns-query|:heavy_check_mark:|Ad & porn blocking
|2poi.com|https://dns.2poi.com/dns-query|:heavy_check_mark:|Adblocking
|2t9.de|https://dns.2t9.de/dns-query|:heavy_check_mark:|Adblocking
|3363.net|https://n.3363.net/dns-query|:heavy_check_mark:|
|[4Women Clinic](https://lunet.design/)|https://dns.lunet.design/dns-query|:heavy_check_mark:|Adblocking
|52306.org|https://dns.52306.org/dns-query|:heavy_check_mark:|
| [5ososea](https://www.5ososea.com/) | Adblocking: https://dns.5ososea.com/dns-query <br> Ad & porn blocking: https://family.5ososea.com/dns-query <br> Ad & porn blocking with safe search: https://kids.5ososea.com/dns-query | :heavy_check_mark: <br> :heavy_check_mark: <br> :heavy_check_mark: | Hosted in Germany, query logged for 24 hours.
|68360612.xyz|https://jp.68360612.xyz/dns-query|:heavy_check_mark:|
| [7vpn](https://dns.7vpn.com/) | https://dns.7vpn.com/dns-query | :heavy_check_mark: | Adblocking
|886886886.xyz|https://dns.886886886.xyz/dns-query|:heavy_check_mark:|Adblocking
|996333.xyz|https://jpok.996333.xyz/dns-query|:heavy_check_mark:|Adblocking
| **Others**
| @jedisct1  | https://doh.crypto.sx/dns-query | :heavy_check_mark: |a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust.
|[@MarcRnt](https://marcrnt.de/)|https://home.marcrnt.de/dns-query|:heavy_check_mark:|Adblocking
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