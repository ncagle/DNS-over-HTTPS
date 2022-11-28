# Using HTTPS records

Draft: [Service binding and parameter specification via the DNS (DNS SVCB and
HTTPS
RRs)](https://www.ietf.org/archive/id/draft-ietf-dnsop-svcb-https-11.html)

## Description

`HTTPS` is the name of a new DNS record that provides application protocol
information to a client early. Using the data returned in this record, the
client can connect directly to the appropriate host and use the most suitable
application protocol version.

Using this record lets a client use HTTP/3 directly instead of having to
"bounce" over an initial HTTP/1 or HTTP/2 request using the `Alt-Svc:`
response header.

## Hints

An example HTTPS record could look like this:

~~~
example.com 300 IN HTTPS  1 cdn.example.net
                            alpn="h3,h2,http/1.1"
                            ipv4hint=192.1.2.3,192.3.4.5
                            ipv6hint=2001:db8::1000:fe90,2001:db8::2000:85e5
~~~

| data            | meaning                 |
|-----------------|-------------------------|
| example.com     | domain name             |
| 300             | TTL                     |
| IN              | class                   |
| HTTPS           | record type             |
| 1               | priority                |
| cdn.example.net | target (host)           |
| alpn            | ALPN list to use        |
| ipv4hint        | possible IPv4 addresses |
| ipv6hint        | possible IPv6 addresses |

## Getting this record

Unfortunately there is no universally available function call that will return
the contents of this DNS record.

When curl resolves host names it typically uses `getaddrinfo` (by default) or
it was optionally built to use c-ares instead and its
[cares_getaddrinfo](https://c-ares.org/ares_getaddrinfo.html). None of those
will return HTTPS record details.

There simply is no easy existing way to get this DNS record using the normal
POSIX function calls.

## Using c-ares for HTTPS

One way to proceed is to build curl with c-ares and use c-ares for getting the
HTTPS record for the host name used in the URL.

The c-ares function call for the HTTPS records needs to be done *in addition*
to the regular name resolve call(s) and therefor the HTTPS record response
risks coming back after the name resolve is complete (or even not at all).

If a successful HTTPS response comes first, curl could potentially start with
the information in that record (if there are ipv*hints given) and kick off a
new name resolve for the new target host name in the mean time (if it indeed
is a new target host name provided).

If the name is resolved before the HTTPS response comes back, curl should
probably wait for a short time extra just in case, and otherwise continue as
if there is no HTTPS record for the domain.

## New use of c-ares

The extra c-ares lookup for HTTPS then needs to be done even if `getaddrinfo`
is otherwise used for the name resolve. For this case, an added complication
is that up until now building with c-ares means that curl will also use c-ares
for name resolving while I now suggest that there is going to be another
"mode" where c-ares is used, but only *in addition* to the normal stock name
resolver.

If c-ares is used also for the name resolve, adding just another lookup on the
same channel should be less complicated.

## Caching

The existing DNS cache could be extended to also hold this HTTPS data per entry so that
repeated lookups of the same host name within a short period of time are done faster.