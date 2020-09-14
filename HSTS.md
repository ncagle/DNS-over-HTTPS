# Plans for HSTS support in curl

Spec: [HTTP Strict Transport Security](https://tools.ietf.org/html/rfc6797)

## Work-In-Progress

https://github.com/curl/curl/pull/5896

(What is described in this wiki page is supposedly matching the code and docs in the PR. It means that we will eventually remove this
wiki page and instead refer to code and docs in the source tree.)

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

# Read/write callbacks

~~~c
struct curl_hstsentry
{
  char *name;
  size_t namelen;
  int includeSubDomains:1;
  char expire[18]; /* YYYYMMDD HH:MM:SS [null-terminated] */
};

struct curl_index
{
  size_t index; /* the provided entry's "index" or count */
  size_t total; /* total number of entries to save */
};

typedef enum {
  CURLSTS_AGAIN,
  CURLSTS_DONE,
  CURLSTS_FAIL
} CURLSTScode;

/*
 * CURLOPT_HSTSREADFUNCTION
 * gets called repeatedly by libcurl to populate the in-memory HSTS cache.
 *
 * Copy the host name to 'name' (no longer than 'namelen' bytes). Make it
 * null-terminated.
 * Set 'includeSubDomain' to TRUE or FALSE.
 * Set 'expire' to a date stamp or a zero length string for *forever*
 * (wrong date stamp format might cause the name to not get accepted)
 *
 * Return codes:
 * CURLSTS_AGAIN - call the function again
 * CURLSTS_DONE - this was the last entry
 * CURLSTS_FAIL - major problem, abort the transfer now
 * [others] - all other return codes are reserved for future use
 */
CURLSTScode hstsread(CURL *easy, struct curl_hstsentry *sts, void *userp);

/*
 * CURLOPT_HSTSWRITEFUNCTION
 * gets called repeatedly by libcurl to save the HSTS cache on closure.
 *
 * Copy the host name from 'name' (null-terminated).
 * Clone the 'includeSubDomain' status
 * Copy or parse the 'expire' timestamp (which might be a zero string if
 * previously set to *forever*)
 *
 * 'index' points to a struct with information about each entry and the
 * expected total amount to get save using this callback.
 *
 * Return codes:
 * CURLSTS_AGAIN - call the function again (if there are more entries)
 * CURLSTS_DONE - don't call the callback again
 * CURLSTS_FAIL - major problem, no more HSTS entries will be saved
 * [others] - all other return codes are reserved for future use
 */
CURLSTScode hstswrite(CURL *easy, struct curl_hstsentry *sts,
                      struct curl_index *index, void *userp);
