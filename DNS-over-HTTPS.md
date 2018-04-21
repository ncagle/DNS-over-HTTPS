# DOH

Do DNS resolves over HTTPS for privacy, performance and security. Also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

This is work in progress: https://tools.ietf.org/html/draft-ietf-doh-dns-over-https-05

# Servers

Google runs one. Test with `https://dns.google.com/experimental?ct&dns=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB` (DNS stamp: `sdns://AgUAAAAAAAAAACDyXGrcc5eNecJ8nomJCJ-q6eCLTEn6bHic0hWGUwYQaA5kbnMuZ29vZ2xlLmNvbQ0vZXhwZXJpbWVudGFs`)

Cloudflare runs one at `https://dns.cloudflare.com/.well-known/dns` (DNS stamp: `sdns://AgcAAAAAAAAAACDrdSX4jw2UWPgamVAZv9NMuJzNyVfnsO8xXxD4l2OBGBJkbnMuY2xvdWRmbGFyZS5jb20KL2Rucy1xdWVyeQ`) -- Supports POST only.

CleanBrowsing runs an anycast DoH server with parental control (restricts access to adult content + enforces safe search) at `https://doh.cleanbrowsing.org/doh/family-filter/?ct&dns=` (DNS stamp: `sdns://AgMAAAAAAAAAAAAVZG9oLmNsZWFuYnJvd3Npbmcub3JnEy9kb2gvZmFtaWx5LWZpbHRlci8`)

Daniel runs a "toy server" that only supports GET: `https://daniel.haxx.se/dns?dns=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB`

@chantra has another "toy server" which runs [doh-proxy](https://github.com/facebookexperimental/doh-proxy): `https://dns.dnsoverhttps.net/dns-query?ct&dns=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB`

@jedisct1 has a server which runs another project called [doh-proxy](https://github.com/jedisct1/rust-doh), written in Rust. `https://doh.crypto.sx/dns-query?ct&dns=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB`
([DNS stamp](https://github.com/jedisct1/dnscrypt-proxy/wiki/stamps): `sdns://AgcAAAAAAAAAACAd2FCKjFZZBDl8eGRR4I9XYTzzyKcj9vN5_Uw4WLbznw1kb2guY3J5cHRvLnN4Ci9kbnMtcXVlcnk`)

SecureDNS.eu runs one at `https://doh.securedns.eu/dns-query?ct&dns=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB` (DNS stamp: `sdns://AgcAAAAAAAAAAAAQZG9oLnNlY3VyZWRucy5ldQovZG5zLXF1ZXJ5`)

# DOH in curl

## Bootstrap

The DOH server is given with a host name that itself needs to be resolved. This initial resolve needs to be done by the native resolver before DOH kicks in. Or the address is provided with `--resolve` / `CURLOPT_RESOLVE`.

## DOH resolver

When a DOH-resolve is to get done, it will need to
1. issue the DOH resolve asynchronously
2. create one or two easy handles and associated HTTP transfers (`A` + `AAAA` resolves will need one request each)
3. add the easy handles to the multi handle to make the DOH-transfers perform
4. parse the DOH responses, feed the parsed resolve data into the DNS cache.
5. close the DOH easy handles
5. return the address data to the initial transfer that needed it, and continue 

## A "Custom resolver" ?

Anders Bakken works on making the DNS backend generic enough to allow applications to plug in a custom DNS resolver in [#2232](https://github.com/curl/curl/pull/2232). Will that be suitable for this DOH resolver

# DOH Tools

Facebook's [doh-proxy](https://facebookexperimental.github.io/doh-proxy/) and associated tools.

Daniel's [dns2doh](https://github.com/bagder/dns2doh) tool for generating DOH responses and questions.

Frank Denis' [doh-proxy](https://github.com/jedisct1/rust-doh) (server-side proxy) and [dnscrypt-proxy](https://github.com/jedisct1/dnscrypt-proxy) (client proxy).

Daniel Cid's [doh-php-client](https://github.com/dcid/doh-php-client) can be used to test and run DoH requests via PHP applications.

Travis Burtrum's [jDnsProxy](https://github.com/moparisthebest/jDnsProxy) DNS proxy and cache, implementing [DNS-over-TLS](https://tools.ietf.org/html/rfc7858), [DNS-over-HTTPS](https://tools.ietf.org/html/draft-hoffman-dns-over-https), and [Serve-Stale](https://tools.ietf.org/html/draft-ietf-dnsop-serve-stale)

Star Brilliant's [dns-over-https](https://github.com/m13253/dns-over-https), with server-side and client-side implementation, written in Golang.