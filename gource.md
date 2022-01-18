[gource](https://gource.io/) is a tool to generate a video from source code history.

## Create an gource video from the curl repo

In a curl git repo, run the following script. It will take a while to complete.

~~~shell
LOGO="300-pixel-logo.png"
CAPTION="caption.txt"
OUTPUT="curl.mp4"
gource -1920x1080 -s 0.05 -r 60 -o - --logo $LOGO --user-image-dir gource --caption-file $CAPTION --caption-duration 3 --caption-offset 80 --caption-size 24 | ffmpeg -y -r 60 -f image2pipe -vcodec ppm -i - -vcodec libx264 -preset ultrafast -pix_fmt yuv420p -crf 1 -threads 0 -bf 0 $OUTPUT
~~~

## Captions

Some "notable" moments in time to use as caption file for the gource. Save as `caption.txt` for the line above.

~~~
946508400|Dec 29 1999: all code imported to Sourceforge
946681200|January 1 2000: Daniel is the sole committer
948063600|January 17 2000: curl 6.4 (release 36)
949359600|February 1 2000: 18,937 lines of code
953506800|March 20 2000: OS/2 support
953593200|March 21 2000: 48 command line options
960501600|June 9 2000: website is live on curl.haxx.se
965599200|August 7 2000: the first libcurl release (7.1)
966808800|August 21 2000: 48 contributors and the 11 first man pages
966808800|August 21 2000: 31 public functions in the API
971388000|October 13 2000: the first CVE was reported on curl
975625200|December 1 2000: curl 7.5 at 24,959 lines of code
978303600|January 2001: MIT licensed
980118000|January 22 2001: IPv6
982018800|February 13 2001: 13 man pages
983401200|March 2001: passed 1,100 commits
985215600|March 22 2001: curl 7.7 added HTTP/1.1 support
990568800|May 23 2001: introduced the "new" test file format
991173600|May 30 2001: a second committer: Cris Bailiff
991260000|May 31 2001: the third committer: Sterling Hughes
991778400|June 6 2001: at 67 contributors
991864800|June 7 2001: curl 7.8 at 18 tests and 21 man pages
993938400|July 2001: 27,516 lines of code
999295200|September 2001: cookie-jar and multi-part formpost
1001368800|September 25 2001: curl 7.7.2 gets bundled in macOS 10.1
1007506800|December 5 2001: curl 7.9.2
1011740400|January 23 2002: at 79 tests
1015455600|March 7 2002: curl 7.9.5
1017612000|April 2002: 70 command line options
1022882400|June 2002: 35,000 lines of product code
1028325600|August 3 2002: at 5 committers
1030658400|August 30 2002: SOCKS5 support
1033423200|October 1 2002: curl 7.10 verifies server certificates by default
1033423200|October 1 2002: added the --limit-rate option
1038697200|December 1 2002: 42,977 lines of code
1041375600|January 2003: introducing autobuilds
1046473200|March 2003: 3250 commits
1049234400|April 2 2003: at 112 tests
1054418400|June 2003: multiple HTTP authentication schemes
1059861600|August 3 2003: CVE-2003-1605: the second reported one
1060034400|August 5 2003: first use of c-ares for name resolving
1060898400|August 15 2003: at 40 man pages
1065477600|October 7 2003: imported the c-ares source tree
1067641200|November 1 2003: curl 7.10.8
1070233200|December 2003: SSL for FTP
1074726000|January 22 2004: curl 7.11.0 (release 77)
1076367600|February 10 2004: at 10 committers
1079564400|March 18 2004: 94 command line options and 173 tests
1086040800|June 2 2004: curl 7.12.0 with IDN support
1091311200|August 2004: 96 command line options and 216 tests
1096581600|October 2004: passed 6000 commits
1099263600|November 1 2004: 54,273 lines of code
1103497200|December 20 2004: curl 7.12.3 introduces --retry
1107212400|February 1 2005: curl 7.13.0
1112306400|April 2005: GnuTLS and multi_socket support
1116194400|May 16 2005: curl 7.14.0: 437 contributors
1120168800|July 1 2005: 58,611 lines of code
1125525600|September 2005: added TFTP support
1129154400|October 13 2005: curl 7.15.0
1129154400|October 13 2005: 109 command line options
1133823600|December 6 2005: 301 tests
1136070000|January 2006: dropped GOPHER
1140476400|February 21 2006: SOCKS4 support
1143842400|April 1 2006: 63,965 lines of code
1150063200|June 12 2006: curl 7.15.4
1154901600|August 7 2006: curl 7.15.5 at 53 man pages
1154901600|August 7 2006: 54 public libcurl functions
1157061600|September 2006: bumped SONAME to 4
1162162800|October 30 2006: curl 7.16.0
1162335600|November 2006: added SCP and SFTP support
1164927600|December 2006: only two committers this month
1170025200|January 29 2007: added the --libcurl option
1170284400|February 2007: support NSS
1176242400|April 11 2007: 348 tests
1183240800|July 1 2007: 75,345 lines of code
1185919200|August 2007: LDAPS support
1189634400|September 13 2007: curl 7.17.0 (release 100)
1193612400|October 29 2007: curl 7.17.1
1196463600|December 2007: 9725 commits
1201474800|January 28 2008: 126 command line options
1201474800|January 28 2008: added the --data-urlencode option
1204326000|March 2008: passed 10,000 commits
1207000800|April 2008: support the QsoSSL library
1212530400|June 4 2008: curl 7.18.2 with 58 functions in the API
1214863200|July 2008: 6 commit authors this month
1220220000|September 1 2008: 654 contributors
1225494000|November 2008: 128 command line options
1232319600|January 19 2009: 519 tests
1238536800|April 2009: added the cmake build
1238623200|April 2 2009: 20 committers
1243807200|June 1 2009: 85,627 lines of code
1250028000|August 12 2009: 132 command line options
1257289200|November 4 2009: 57 man pages
1259622000|December 2009: added support for IMAP, POP3 and SMTP (and TLS versions)
1262300400|January 2010: added support for RTSP
1265670000|February 9 2010: curl 7.20.0: 10 reported CVEs in total
1267398000|March 2010: moved code to git and hosting to GitHub
1267570800|March 3 2010: 30 committers
1269385200|March 24 2010: removed the c-ares source tree
1272664800|May 2010: added RTMP and PolarSSL support
1276639200|June 16 2010: curl 7.21.0: 794 contributors and 575 tests
1280613600|August 1 2010: 138 command line options
1281564000|August 12 2010: GOPHER support is readded
1286402400|October 7 2010: reached 50 commmitters
1288566000|November 1 2010: 99,790 lines of code
1292367600|December 15 2010: 143 command line options
1292367600|December 15 2010: added the --resolve option
1296514800|February 2011: support for axTLS
1301608800|April 2011: added suppot for cyassl "natively"
1307829600|June 23 2011: curl 7.21.7
1311026400|July 19 2011: 100 committers
1315864800|September 13 2011: curl 7.22.0
1321311600|November 15 2011: curl 7.23.0
1326495600|January 14 2012: 149 command line options
1332370800|March 22 2012: curl 7.25.0 (release 127)
1337810400|May 24 2012: curl 7.26.0
1341093600|July 1 2012: added support for metalink, Schannel and Secure transport
1343340000|July 27 2012: curl 7.27.0
1349820000|October 10 2012: curl 7.28.0
1351724400|November 1 2012: 117,507 lines of code
1354316400|December 2012: 15679 commits
1359673200|February 2013: make everything non-blocking internally
1365717600|April 12 2013: curl 7.30.0
1370642400|June 8 2013: 200 committers
1372629600|July 2013: support the GSKit TLS library
1376172000|August 11 2013: 839 tests
1376258400|August 12 2013: curl 7.32.0
1377986400|September 2013: first takes on HTTP/2 support with nghttp2
1380578400|October 2013: removed krb4
1381960800|October 17 2013: added the first two CI jobs
1385852400|December 2013: welcome happy eyeballs
1390950000|January 29 2014: 161 command line options and 20 reported CVEs
1393628400|March 2014: first release with real HTTP/2
1399327200|May 6 2014: 250 commit authors
1400536800|May 20 2014: 59 man pages
1405461600|July 16 2014: 270 man pages
1405461600|July 16 2014: 1,155 contributors
1406844000|August 2014: libressl support
1409522400|September 1 2014: 131,774 lines of code
1410300000|September 10 2014: curl 7.38.0
1412892000|October 10 2014: dropped QsoSSL
1417215600|November 29 2014: added SMB(S) support
1420066800|January 2015: BoringSSL support
1420585200|January 7 2015: 285 man pages
1424386800|February 20 2015: 300 committers
1424818800|February 25 2015: 979 tests
1425164400|March 2015: Switched to use issues and pull-requests on GitHub
1429653600|April 22 2015: curl 7.42.0: 30 reported CVEs
1433109600|June 2015: multiplexed HTTP/2 transfers
1438380000|August 2015: HTTP/2 server push
1443650400|October 1 2015: support for mbedTLS
1446332400|November 2015: passed 20,000 commits
1448924400|December 2015: support the Public Suffix List for cookies
1449874800|December 12 2015: 342 man pages
1451602800|January 2016: curl tool defaults to HTTP/2 for HTTPS
1458687600|March 23 2016: 1,364 contributors
1463349600|May 17 2016: 185 command line options
1468447200|July 14 2016: 4 CI jobs
1469052000|July 21 2016: curl 7.50.0 (release 157)
1473199200|September 7 2016: 1,035 tests
1478041200|November 2 2016: 50 reported CVEs
1480546800|December 2016: HTTPS proxy support and first TLS 1.3
1487718000|February 22 2017: 205 command line options
1488322800|March 1 2017: 142,921 lines of code
1492552800|April 19 2017: curl 7.54.0
1498860000|July 2017: OSS-fuzz starts poking on curl
1503007200|August 18 2017: 500 commit authors
1504216800|September 2017: multi-SSL support at 211 command line options
1506808800|October 2017: SSLKEYLOGFILE support, new MIME API
1507068000|October 4 2017: 74 public functions
1509490800|November 2017: brotli compression
1511910000|November 29 2017: 1,649 contributors
1514761200|January 2018: libssh support
1516748400|January 24 2018: 74 reported CVEs
1519858800|March 2018: curl ships by default in Windows 10
1520031600|March 3 2018: 400 man pages
1520895600|March 13 2018: 19 CI jobs
1526335200|May 15 2018: 214 command line options and 1,197 tests
1526421600|May 16 2018: curl 7.60.0 (release 175)
1530396000|July 2018: bold headers in terminal output
1535752800|September 2018: support the MesaLink TLS library
1538344800|October 1 2018: DNS-over-HTTPS
1539381600|October 13 2018: curl 7.62.0
1540854000|October 30 2018: 80 public functions
1540940400|October 31 2018: 219 command options
1543618800|December 1 2018: droped axTLS support
1544569200|December 12 2018: 27 CI jobs
1546297200|January 1 2019: 156,023 lines of code
1551394800|March 2019: experimental alt-svc support and AmiSSL support
1553554800|March 26 2019: Plan 9 support
1558476000|May 22 2019: curl 7.65.0
1563314400|July 17 2019: 43 CI jobs
1564610400|August 2019: first HTTP/3 code
1567288800|September 2019: parallel downloads with the curl tool
1568152800|September 11 2019: curl 7.66.0 (release 186)
1572562800|November 1 2019: added supprt for BearSSL
1576796400|December 20 2019: 750 commit authors
1578438000|January 8 2020: added the etag options
1579129200|January 16 2020: dropped PolarSSL support
1583017200|March 2020: added wolfSSH support
1583276400|March 4 2020: 72 CI jobs
1585692000|April 2020: experimental MQTT
1588111200|April 29 2020: 1,352 tests
1588111200|April 29 2020: curl 7.70.0 (release 191)
1592863200|June 23 2020: 232 command line options
1596232800|August 2020: hello zstd compression
1602626400|October 14 2020: curl 7.73.0 added --output-dir
1602626400|October 14 2020: 85 public functions and 89 CI jobs
1604185200|November 2020: moved over to curl.se
1607468400|December 9 2020: 2,287 contributors
1607468400|December 9 2020: 454 man pages
1607986800|December 15 2020: GOPHERS support
1612306800|February 3 2021: the hyper HTTP backend and rustls support
1613602800|February 18 2021: helped land Ingenuity on Mars
1616713200|March 26 2021: curl 7.77.0 (release 200)
1617228000|April 1 2021: 172,623 lines of code
1621980000|May 26 2021: 1,427 tests and 99 CI jobs
1626818400|July 21 2021: 242 command line options
1631656800|September 15 2021: 111 reported CVEs
1636498800|November 10 2021: curl 7.80.0 with 86 public functions
1638313200|December 2021: passed 28,000 commits
1641337200|January 5 2022: curl 7.81.0 (release 205)
1641337200|January 5 2022: 472 man pages and 100 CI jobs
1641769200|January 10 2022: dropped MesaLink support
~~~