# DOH

Do DNS resolves over HTTPS for privacy, performance and security. Also makes it easier to use a name server of your choice instead of the one configured for your system.

# Spec

This is work in progress: https://tools.ietf.org/html/draft-ietf-doh-dns-over-https-02

# Servers

Google runs one. Test with `https://dns.google.com/experimental?ct&body=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB`

Daniel runs a "toy server" that only supports GET: `https:/daniel.haxx.se/dns?body=q80BAAABAAAAAAAAA3d3dwdleGFtcGxlA2NvbQAAAQAB`

# DOH in curl

## Bootstrap

The DOH server is given with a host name that itself needs to be resolved. This initial resolve needs to be done by the native resolver before DOH kicks in.

## DOH resolver

When a DOH-resolve is to get done, it will need to
1. issue the DOH resolve asynchronously
2. create one or two easy handles and associated HTTP transfers (A + AAAA resolves will need one request each)
3. add the easy handles to the multi handle to make the DOH-transfers perform
4. parse the DOH responses, feed the parsed resolve data into the DNS cache.
5. close the DOH easy handles
5. return the address data to the initial transfer that needed it, and continue 

## A "Custom resolver" ?

Anders Bakken works on making the DNS backend generic enough to allow applications to plug in a custom DNS resolver in [#2232](https://github.com/curl/curl/pull/2232). Will that be suitable for this DOH resolver