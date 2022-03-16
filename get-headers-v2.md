# An HTTP header access API (v2)

This was proposal v2, v1 is in [A header access API](get-headers.md).

The work on implementing takes places in [PR 8593](https://github.com/curl/curl/pull/8593). The API has already been changed a bit in that PR compared to this wiki page. This page will be removed when the PR lands, to keep the proper documentation at a single place: the libcurl man pages.

Designed for HTTP(S). Headers are available in the easy handle after and
during a transfer.

[Feedback here](https://github.com/curl/curl/discussions/8496)

## Header struct

~~~c
struct curl_header {
  char *name;    /* this might not use the same case */
  char *value;
  size_t amount; /* number of headers using this name  */
  size_t index;  /* ... of this instance, 0 or higher */
  unsigned int origin; /* from where */
  void *anchor; /* handle privately used by libcurl */
};

/* 'origin' bits */
#define CURLH_HEADER    (1<<0) /* plain server header */
#define CURLH_TRAILER   (1<<1) /* trailers */
#define CURLH_CONNECT   (1<<2) /* CONNECT headers */
#define CURLH_1XX       (1<<3) /* 1xx headers */
#define CURLH_PSEUDO    (1<<4) /* psuedo headers */

typedef enum {
  CURLHE_OK,
  CURLHE_BADINDEX,      /* header exists but not with this index */
  CURLHE_MISSING,       /* no such header exists */
  CURLHE_NOHEADERS,     /* no headers at all exist (yet) */
  CURLHE_OUT_OF_MEMORY, /* out of memory while processing */
  CURLHE_BAD_ARGUMENT,
} CURLHcode;
~~~
## Get a single header

~~~c
CURLHcode curl_easy_header(CURL *easy,
                           const char *name,
                           size_t index,
                           unsigned int origin,
                           int request,
                           struct curl_header **hout);

~~~

Returns a pointer to a `curl_header` struct in `hout` with data for the header
`name`. The case insensitive nul-terminated header name should be specified
without colon.

`index` 0 means asking for the first instance of the header. If the returned
header struct has `->amount` set larger than 1, that means there are more
instances of the same header name to get. Asking for a too big index makes
`CURLH_BADINDEX` get returned.

`origin` is a bitmask for specifying which headers to look among. See bits above.

`request` is the 0-index request number. There are multiple request done when redirects
 or multi-pass authentication is used. `-1` means the "last one" currently stored.

The contents of the returned `value` comes as delivered over the network but
with leading and trailing whitespace and newlines stripped off. The `value`
data is nul-terminated.

The `->flags` field in the `curl_header` struct has the `CURLHEADER_TRAILER`
bit if the header arrived as a trailer.

libcurl stores and provides the actually used "correct" headers. If for
example two headers with the same name arrive and the latter overrides the
former, then only the latter will be provided. If the first header survives
the second, then only the first one will be provided. An application using
this API does not have to bother about multiple headers used *wrongly*.

The memory for the returned struct is associated with the `easy` handle and
subsequent calls to `curl_easy_header()` will clobber the struct. Applications
need to copy the data if it wants to keep it around. The memory used for the
struct gets freed with calling `curl_easy_cleanup()` of the easy handle.

For *redirects*, this function returns headers from the most recent response only.

### Examples

Get the Content-Type header

    struct curl_header *type;
    CURLHcode h = curl_easy_header(easy, "Content-Type", 0, CURLH_HEADER, -1, &type);

Get all Set-Cookie: headers

    struct curl_header *cookie;
    CURLHcode h = curl_easy_header(easy, "Set-Cookie", 0, CURLH_HEADER, -1, &cookie);
    
    if(h == CURLHE_OK) {
       size_t num = cookie->amount,
       unsigned int i = 0;
       do {
          print "Cookie %u: %s\n", i, cookie->value);
          if(++i > num)
            break;
          h = curl_easy_header(easy, "Content-Type", &cookie, i);
       } while(h == CURLH_OK);
    }

## Get all headers

~~~c
struct curl_header *curl_easy_nextheader(CURL *easy,
                                         unsigned int origin,
                                         int request,
                                         struct curl_header *prev);
~~~

If `prev` is NULL, it returns the first header stored.

If `prev` is a pointer to a previously returned header struct, this function
returns the next header stored. This way, an application can iterate over all
headers.

`origin` is a bitmask for specifying when headers to look among. See bits above.

`request` is the 0-index request number. There are multiple request done when redirects
 or multi-pass authentication is used. `-1` means the "last one" currently stored.

This function returns NULL if there is no more headers to return. If this
function returns NULL when `prev` was set to NULL, then there are no headers
available to return.

The memory for the struct this points to, is owned and managed by libcurl and
is associated with the easy handle. Applications must copy the data if they
want it to survive subsequent API calls or the life-time of the easy handle.

### Example

List all response headers (including trailers):

    struct curl_header *prev = NULL;
    struct curl_header *h;

    while((h = curl_easy_nextheader(easy, CURLH_HEADER|CURLH_TRAILER, -1, prev))) {
       print "%s: %s\n", h->name, h->value);
       prev = h;
    }
