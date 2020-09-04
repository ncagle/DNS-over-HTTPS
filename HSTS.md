# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Work-In-Progress

https://github.com/curl/curl/pull/5896

## Behavior

We introduce an in-memory cache for HSTS hosts, so that subsequent HTTP-only requests to a host name present in the cache will get internally "redirected" to the HTTPS version.

## `curl_easy_setopt()` options:

 - `CURLOPT_HSTS_CTRL` - enable HSTS for this easy handle
 - `CURLOPT_HSTS_PRELOAD` - provide a set of preloaded HSTS host names
 - `CURLOPT_HSTS` - specify file name where to store the HSTS cache on close (and possibly read from at startup)
 - Future: consider ability to save to something else than a file

## curl cmdline options

 - `--hsts [filename]` - enable HSTS, use the file as HSTS cache. If filename is `""` (no length) then no file will be used, only in-memory cache.

## HSTS cache file format

For each hsts entry:

    [host name] "YYYYMMDD HH:MM:SS"

The `[host name]` is dot-prefixed if it is a includeSubDomain.

The time stamp is when the entry expires.

I considered using wget's file format for the HSTS cache. However, they store the time stamp as the epoch (number of seconds since 1970) and I strongly disagree with using that format. Instead I opted to use a format similar to the curl alt-svc cache file format.