# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Behavior

We introduce an in-memory cache for HSTS hosts, so that subsequent HTTP-only requests to a host name present in the cache will get internally "redirected" to the HTTPS version.

There needs to be an option to opt out when working with wrongly configured systems. Or possibly an opt in to remain true to the spirit of curl only doing the basics until told otherwise.

## On-disk cache

We can consider that once the in-memory handling works to achieve more persistent HSTS behavior for clients.