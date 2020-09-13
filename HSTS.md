# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Work-In-Progress

https://github.com/curl/curl/pull/5896

## Behavior

We introduce an in-memory cache for HSTS hosts, so that subsequent HTTP-only requests to a host name present in the cache will get internally "redirected" to the HTTPS version.

## `curl_easy_setopt()` options:

 - `CURLOPT_HSTS_CTRL` - enable HSTS for this easy handle
 - `CURLOPT_HSTS` - specify file name where to store the HSTS cache on close (and possibly read from at startup)

## curl cmdline options

 - `--hsts [filename]` - enable HSTS, use the file as HSTS cache. If filename is `""` (no length) then no file will be used, only in-memory cache.

## HSTS cache file format

Lines starting with `#` are ignored.

For each hsts entry:

    [host name] "YYYYMMDD HH:MM:SS"

The `[host name]` is dot-prefixed if it is a includeSubDomain.

The time stamp is when the entry expires.

I considered using wget's file format for the HSTS cache. However, they store the time stamp as the epoch (number of seconds since 1970) and I strongly disagree with using that format. Instead I opted to use a format similar to the curl alt-svc cache file format.

# Possible future

 - provide a set of preloaded HSTS host names
 - ability to save to something else than a file

~~~c
struct curl_hstsentry
{
   char *name;
   size_t namelen;
   bool includeSubDomain;
   char expire[18]; /* YYYYMMDD HH:MM:SS [null-terminated] */
};

/*
 * CURLOPT_HSTSREADFUNCTION
 * gets called repeatedly by libcurl to populate the in-memory HSTS cache.
 *
 * Copy the host name to 'name' (no longer than namelen bytes).
 * Set 'namelen' to the actual length of the stored name
 * Set 'includeSubDomain' to TRUE or FALSE.
 * Set 'expire' to a date stamp or a zero length string for *forever*
 * (wrong date stamp format might cause the name to not get accepted)
 *
 * Return codes:
 * CURLSTS_AGAIN - call the function again
 * CURLSTS_DONE - this was the last entry
 * CURLSTS_FAIL - major problem, abort the transfer now
 */
CURLSTScode hstsread(CURL *easy, struct curl_hstsentry *sts, void *userp);

/*
 * CURLOPT_HSTSWRITEFUNCTION
 * gets called repeatedly by libcurl to save the HSTS cache on closure.
 *
 * Copy the host name from 'name' (namelen bytes).
 * Clone the 'includeSubDomain' status
 * Copy or parse the 'expire' timestamp (which might be a zero string if
 * previously set to *forever*)
 *
 * if 'flags & CURLSTS_FLAG_LASTONE` equals true, this is the last callback
 * in this save "round".
 *
 * Return codes:
 * CURLSTS_AGAIN - call the function again (if there are more entries)
 * CURLSTS_DONE - don't call the callback again
 * CURLSTS_FAIL - major problem, no more HSTS entries will be saved
 */
CURLSTScode hstswrite(CURL *easy, struct curl_hstsentry *sts,
                      unsigned int flags, void *userp);