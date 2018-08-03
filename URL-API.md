Every once in a while the suggestion comes up that libcurl should provide an API for URL parsing and creating. In every annual user survey a two-digit percentage of users say they would use one if it existed.

Here's a brain-storming page laying out how such an API could be made to work.

# Create, cleanup, duplicate

~~~c
/* the error codes for the URL API */
typedef enum {
  CURLURLE_OK,
  CURLURLE_MALFORMED_INPUT,
  CURLURLE_BAD_PORT_NUMBER,
  CURLURLE_UNSUPPORTED_SCHEME,
  CURLURLE_URLDECODE,
  CURLURLE_RELATIVE,
  CURLURLE_NO_SCHEME,
  CURLURLE_NO_USERPWD,
  CURLURLE_NO_HOST,
  CURLURLE_NO_PORT_NUMBER,
  CURLURLE_NO_QUERY,
  CURLURLE_NO_FRAGMENT,
  CURLURLE_OUT_OF_MEMORY,
} CURLUCode;

#define CURLURL_DEFAULT_PORT (1<<0)       /* return default port numnber */
#define CURLURL_DEFAULT_SCHEME (1<<1)     /* return default scheme if
                                             missing */
#define CURLURL_NON_SUPPORT_SCHEME (1<<2) /* allow non-supported schemes */
#define CURLURL_VERIFY_ONLY (1<<3)        /* binary check of URL validity */
#define CURLURL_CONVERT_SPACES (1<<4)     /* convert ASCII spaces (0x20) to
                                             %20 */
#define CURLURL_CONVERT_8BIT   (1<<5)     /* convert >127 byte values to
                                             converted to %XX output */
#define CURLURL_CONVERT_SLASHES (1<<6)    /* also allow one or three slashes
                                             scheme separation */
#define CURLURL_URLDECODE (1<<7)          /* URL *decode* on read when getting
                                             a part (not full URL) */

/*
 * curl_url() sets the URL (or NULL) to parse. Returns error code.  If
 * successful, stores a CURLURL handle pointer in the 'urlhandle' argument.
 * NULL is an acceptable input to let users add parts individually.
 *
 * The given input URL will be parsed and split up into its components and if
 * any syntax error is found, this function returns the applicable error code.
 * This will never trigger any network use. A URL deemed to be valid by this
 * function will be considered valid by other libcurl operations as well.
 *
 * Flags
 *
 * - CURLURL_NON_SUPPORT_SCHEME allows schemes this libcurl does not
 *   support. If not set, this function returns CURLURLE_UNSUPPORTED_SCHEME
 *   for those.
 * - CURLURL_VERIFY_ONLY makes this function *not* create an output handle but
 *   will still return OK/error regarding the URL syntax.
 * - CURLURL_CONVERT_SPACES tells the function to not consider ascii space to
 *   be an error and instead convert them to %20.
 * - CURLURL_CONVERT_8BIT tells this function to convert 8 bit (>127) byte
 *   values to %xx. URLs are typically 7 bit only so such input is nornally a
 *   mistake.
 * - CURLURL_CONVERT_SLASHES makes the parser allow scheme:/host and
 *   scheme:///host as if they were correct.
 */
CURLUCode curl_url(char *URL, CURLURL **urlhandle, unsigned int flags);

/*
 * curl_url_cleanup() frees the CURLURL handle and related resources used for
 * the URL parsing. It will not free strings previously returned with the URL
 * API.
 */
void curl_url_cleanup(CURLURL *handle);

/*
 * curl_url_dup() duplicates a CURLURL handle and returns a new copy. The new
 * handle must be freed with curl_url_cleanup() when the application is done
 * with it.
 */
CURLURL *newhandle curl_url_dup(CURLURL *inhandle);

~~~

# Extract or set individual parts

~~~c

 typedef enum {
   CURLUPART_URL,    /* used to extract the full URL or set a
                        new URL, that might be relative to the
                        formerly set one */

   CURLUPART_SCHEME,
   CURLUPART_USER,
   CURLUPART_PASSWORD,
   CURLUPART_HOST,
   CURLUPART_PORT,
   CURLUPART_PATH,
   CURLUPART_QUERY,
   CURLUPART_FRAGMENT
 } CURLUPart;

/*
 * curl_url_get() extracts a specific part of the URL from a CURLURL
 * handle. Returns error code. The returned pointer MUST be freed with
 * curl_free() afterwards.
 *
 * Flags: the CURLURL_* bitmask defines described above.
 *
 * for all
 *
 * - CURLURL_URLDECODE returns the string URL decoded. If there's a %00
 *   in there then, curl_url_get() returns CURLURLE_URLDECODE.
 *
 * for URL
 *
 * - CURLURL_DEFAULT_SCHEME makes this function use "https" for scheme
 *   instead of failure if no scheme was set.
 * - CURLURL_DEFAULT_PORT makes this function insert the port number in the
 *   URL even if it matches the default for the used scheme.
 *
 * for SCHEME
 *
 * - CURLURL_DEFAULT_SCHEME makes this function return "https" instead of
 *   failure if no scheme was set.
 * - CURLURL_NON_SUPPORT_SCHEME allows this function to return a scheme name
 *   that is not supported by this libcurl.
 *
 * for PORT
 *
 * Note that the port, while being a number, will be returned as a string just
 * like all other URL parts.
 *
 * - CURLURL_DEFAULT_PORT makes this function return the default port number
 *   for the used scheme even if no explicit port number was used in the URL.
 *
 * for PATH
 *
 * Even if the URL was given without a slash after the host name, this will
 * return a slash as path.
 *
 */
CURLUcode curl_url_get(CURLURL *handle, CURLUPart what,
                       char **part, unsigned int flags);

/*
 * curl_url_set() sets a specific part of the URL in a CURLURL handle. Returns
 * error code. The passed in string will be copied. Passing a NULL instead of
 * a part string, clears that part.
 *
 * Flags: the CURLURL_* bitmask defines described above.
 *
 * for URL
 *
 * If a relative URL is set and there was a previous URL set, this will create
 * the new final URL. If there's not enough to "follow" or create a URL when
 * a relative URL is passed in, CURLURLE_RELATIVE is returned.
 *
 * for SCHEME
 *
 * - CURLURL_NON_SUPPORT_SCHEME allows this function to accept scheme names
 *   that are not supported by this libcurl.
 *
 *
 */
CURLUCode curl_url_set(CURLURL *handle, CURLUPart what,
                       char *part, unsigned int flags);


/* example */
CURLURL *urlp;
rc = curl_url("https://user:password@example.com:1234/path/html?query=name",
              &urlp, CURLURL_DEFAULT_SCHEME);

if(!rc) {
  char *host;
  char *scheme;
  char *user;
  char *password;
  char *path;
  char *query;
  char *fragment;
  char *url;
  char *port;
  CURLUCode rc;

  rc = curl_url_get(urlp, CURLUPART_URL, &url, 0);
  rc = curl_url_get(urlp, CURLUPART_HOST, &host, 0);
  rc = curl_url_get(urlp, CURLUPART_SCHEME, &scheme, 0);
  rc = curl_url_get(urlp, CURLUPART_USER, &user, 0);
  rc = curl_url_get(urlp, CURLUPART_PASSWORD, &password, 0);
  rc = curl_url_get(urlp, CURLUPART_PORT, &port, CURLURL_DEFAULT_PORT);
  rc = curl_url_get(urlp, CURLUPART_PATH, &path, 0);
  rc = curl_url_get(urlp, CURLUPART_QUERY, &query, 0);
  rc = curl_url_get(urlp, CURLUPART_FRAGMENT, &fragment, 0);

  rc = curl_url_set(urlp, CURLUPART_HOST, "www.example.com", 0);
  rc = curl_url_set(urlp, CURLUPART_SCHEME, "https", CURLURL_NON_SUPPORT_SCHEME);
  rc = curl_url_set(urlp, CURLUPART_USER, "john", 0);
  rc = curl_url_set(urlp, CURLUPART_PASSWORD, "doe", 0);
  rc = curl_url_set(urlp, CURLUPART_PORT, "443", 0);
  rc = curl_url_set(urlp, CURLUPART_PATH, "/index.html", 0);
  rc = curl_url_set(urlp, CURLUPART_QUERY, "name=john", 0);
  rc = curl_url_set(urlp, CURLUPART_FRAGMENT, "anchor", 0);

  /* set a new URL (possibly relative to the first one) */
  rc = curl_url_set(urlp, CURLUPART_URL, "../image.png", 0);

  curl_url_cleanup(urlp);
}

~~~
# CURLOPT_CURLURL

It makes sense to also add an option that allows a `CURLURL *` to be passed to libcurl as a URL instead of the traditional `CURLOPT_URL`.
