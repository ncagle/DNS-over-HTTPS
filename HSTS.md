# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Work-In-Progress

https://github.com/curl/curl/pull/5896

## Behavior

We introduce an in-memory cache for HSTS hosts, so that subsequent HTTP-only requests to a host name present in the cache will get internally "redirected" to the HTTPS version.

## `curl_easy_setopt()` options:

 - `CURLOPT_HSTS` - enable HSTS for this easy handle
 - `CURLOPT_HSTS_PRELOAD` - provide a set of preloaded HSTS host names
 - `CURLOPT_HSTS_FILE` - specify file name where to store the HSTS cache on close (and possibly read from at startup)
 - Should we consider ability to save to something else than a file?

## curl cmdline options

 - `--hsts [filename]` - enable HSTS, use the file as HSTS cache. If filename is `""` (no length) then no file will be used, only in-memory cache.

## HSTS cache file format

For each hsts entry:

    [host name] [SUB/-] "YYYYMMDD HH:MM:SS"

`SUB` means `includeSubDomains` was used for the name.
The time stamp is when the entry expires.