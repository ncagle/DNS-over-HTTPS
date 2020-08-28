# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Behavior

We introduce an in-memory cache for HSTS hosts, so that subsequent HTTP-only requests to a host name present in the cache will get internally "redirected" to the HTTPS version.

This will be done unconditionally if the host is present in the cache. If someone insists, we could introduce an option to explicitly opt out.

## On-disk cache

We can consider that once the in-memory handling works to achieve more persistent HSTS behavior for clients.