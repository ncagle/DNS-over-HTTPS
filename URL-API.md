Every once in a while the suggestion comes up that libcurl should provide an API for URL parsing and creating. In every annual user survey a two-digit percentage of users say they would use one if it existed.

Here's a brain-storming page laying out how such an API could be made to work. Two alternatives are shown.

# URL API alternative A

~~~c
typedef enum {
  CURLURLE_OK,
  CURLURLE_MALFORMED_INPUT,
  CURLURLE_BAD_PORT_NUMBER,
  CURLURLE_UNSUPPORTED_SCHEME,
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
 * NULL is an acceptable input to let users add pieces individually.
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
CURLUCode curl_url(char *URL, CURLURL *urlhandle, unsigned int flags);

/*
 * curl_url_get() extracts a full URL from a CURLURL handle. Returns error
 * code. The returned pointer MUST be freed with curl_free() afterwards.
 *
 * The output URL might be "normalized" and might therefore not be identical
 * to the input URL even when that was deemed syntactically correct.
 *
 * This function will return error if not enough URL parts have been
 * specified.
 *
 * Flags
 *
 * - CURLURL_DEFAULT_SCHEME makes this function return "https" instead of
 *   failure if no scheme was set.
 * - CURLURL_DEFAULT_PORT makes this function insert the port number in the
 *   URL even if it matches the default for the used scheme.
 */
CURLUCode curl_url_get(CURLURL *handle, char **url, unsigned int flags);

/*
 * curl_url_host() extracts the host name part from a URL preciously set in
 * the CURLURL handle. Returns error code. The returned pointer MUST be freed
 * with curl_free() afterwards.
 *
 * The host name can also be a numerical IP address, like 192.168.0.1 or
 * [2001:1890:1112:1::20].
 *
 * To decide and document proper: encoding, IDNA.
 */
CURLUCode curl_url_host(CURLURL *handle, char **host);

/*
 * curl_url_scheme() extracts the scheme name part from a URL preciously set
 * in the CURLURL handle. Returns error code. The returned pointer MUST be
 * freed with curl_free() afterwards.
 *
 * If no scheme has been set for the URL, this function returns
 * CURLURLE_NO_SCHEME
 *
 * Flags
 *
 * - CURLURL_DEFAULT_SCHEME makes this function return "https" instead of
 *   failure if no scheme was set.
 * - CURLURL_NON_SUPPORT_SCHEME allows this function to return a scheme name
 *   that is not supported by this libcurl.
 */
CURLUCode curl_url_scheme(CURLURL *handle, char **scheme,
                            unsigned int flags);

/*
 * curl_url_userpwd() extracts the user and password parts from a URL
 * preciously set in the CURLURL handle. Returns error code. The returned
 * pointers MUST be freed with curl_free() afterwards.
 *
 * If just one of the user or password fields were set, this function will
 * return a NULL pointer for the unused field. If none of the fields were used,
 * this returns CURLURLE_NO_USERPWD.
 */
CURLUCode curl_url_userpwd(CURLURL *handle, char **user, char **password);

/*
 * curl_url_port() extracts the port number from a URL preciously set in the
 * CURLURL handle. Returns error code.
 *
 * If no port number was given in the URL, this function will return
 * CURLURLE_NO_PORT_NUMBER.
 *
 * Flags
 *
 * - CURLURL_DEFAULT_PORT makes this function return the default port number
 *   for the used scheme if no explicit port number was used in the URL.
 */
CURLUCode curl_url_port(CURLURL *handle, int *port, unsigned int flags);

/*
 * curl_url_path() extracts the path part from a URL preciously set in the
 * CURLURL handle. Returns error code. The returned pointer MUST be freed with
 * curl_free() afterwards.
 *
 * Even if the URL was given without a slash after the host name, this will
 * return a slash as path.
 */
CURLUCode curl_url_path(CURLURL *handle, char **path);

/*
 * curl_url_query() extracts the query part from a URL preciously set in the
 * CURLURL handle. Returns error code. The returned pointer MUST be freed with
 * curl_free() afterwards.
 */
CURLUCode curl_url_query(CURLURL *handle, char **query);

/* curl_url_fragment() extracts the fragment part from a URL preciously set in
 * the CURLURL handle. Returns error code. The returned pointer MUST be freed
 * with curl_free() afterwards.
 */
CURLUCode curl_url_fragment(CURLURL *handle, char **fragment);

/*
 * curl_url_cleanup() frees the CURLURL handle and related resources used for
 * the URL parsing. It will not free strings previously returned with the URL
 * API.
 */
void curl_url_cleanup(CURLURL *handle);

/*
 * curl_url_set_host() sets the host name part of a URL held by a CURLURL
 * handle. The given host argument must point to a zero terminated string
 * using an URL encoded host name.
 *
 * To decide proper: what about IDNA?
 */
CURLUCode curl_url_set_host(CURLURL *handle, const char *host);

/*
 * curl_url_set_scheme() sets the scheme part of a URL held by a CURLURL
 * handle. The given scheme argument must point to a zero terminated string
 * using an URL encoded scheme name.
 *
 * Flags
 *
 * - CURLURL_NON_SUPPORT_SCHEME allows this function to accept scheme names
 *   that are not supported by this libcurl.
 */
CURLUCode curl_url_set_scheme(CURLURL *handle, const char *scheme,
                                unsigned int flags);

/*
 * curl_url_set_userpwd() sets the user and password parts of a URL held by a
 * CURLURL handle. The given user and password arguments must point to zero
 * terminated strings using URL encoded strings.
 *
 * It is fine set one or both of the pointers to NULL to effectively not set
 * those fields.
 */
CURLUCode curl_url_set_userpwd(CURLURL *handle, const char *user,
                                 const char *password);

/*
 * curl_url_set_port() sets the port number of a URL held by a CURLURL
 * handle. The given port number must be a valid port number (1 - 65535) or
 * CURLURLE_BAD_PORT_NUMBER will be returned.
 *
 */
CURLUCode curl_url_set_port(CURLURL *handle, unsigned int port);

/*
 * curl_url_set_path() sets the path part of a URL held by a CURLURL
 * handle. The given path argument must point to a zero terminated string
 * using an URL encoded scheme name.
 *
 */
CURLUCode curl_url_set_path(CURLURL *handle, const char *path);

/*
 * curl_url_set_query() sets the query part of a URL held by a CURLURL
 * handle. The given query argument must point to a zero terminated string
 * using an URL encoded scheme name.
 *
 */
CURLUCode curl_url_set_query(CURLURL *handle, const char *query);

/*
 * curl_url_set_fragment() sets the fragment part of a URL held by a CURLURL
 * handle. The given fragment argument must point to a zero terminated string
 * using an URL encoded scheme name.
 *
 */
CURLUCode curl_url_set_fragment(CURLURL *handle, const char *fragment);

/* example code using the API */

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
  char *fullurl;
  unsigned int port;
  CURLUCode rc;

  rc = curl_url_host(urlp, &host);
  rc = curl_url_scheme(urlp, &scheme, CURLURL_DEFAULT_SCHEME);
  rc = curl_url_userpwd(urlp, &user, &password);
  rc = curl_url_port(urlp, &port, FALSE, CURLURL_DEFAULT_PORT);
  rc = curl_url_path(urlp, &path);
  rc = curl_url_query(urlp, &query);
  rc = curl_url_fragment_(urlp, &fragment);

  rc = curl_url_set_host(urlp, "www.example.com");
  rc = curl_url_set_scheme(urlp, "https", CURLURL_NON_SUPPORT_SCHEME);
  rc = curl_url_set_userpwd(urlp, "john", "doe");
  rc = curl_url_set_port(urlp, 443);
  rc = curl_url_set_path(urlp, "/index.html");
  rc = curl_url_set_query(urlp, "name=john");
  rc = curl_url_set_fragment(urlp, "achor");

  rc = curl_url_get(urlp, &fullurl, 0);

  curl_url_cleanup(urlp);
}
~~~

# URL API alternative B

~~~c

 typedef enum {
   CURLUPART_FULLURL,
   CURLUPART_SCHEME,
   CURLUPART_USER,
   CURLUPART_PASSWORD,
   CURLUPART_HOST,
   CURLUPART_PORT,
   CURLUPART_PATH,
   CURLUPART_QUERY,
   CURLUPART_FRAGMENT
 } CURLUPart;

/* curl_url() and curl_url_cleanup() work like above */
CURLUCode curl_url(char *URL, CURLURL *urlhandle, unsigned int flags);
void curl_url_cleanup(CURLURL *handle);

/*
 * curl_url_get() extracts a specific part of the URL from a CURLURL
 * handle. Returns error code. The returned pointer MUST be freed with
 * curl_free() afterwards.
 *
 * Flags: the CURLURL_* bitmask defines described above.
 *
 */
CURLUcode curl_url_get(CURLURL *handle, CURLUPart what,
                       char **part, unsigned int flags);

/*
 * curl_url_set() sets a specific part of the URL in a CURLURL handle. Returns
 * error code. The passed in string will be copied.
 *
 * Flags: the CURLURL_* bitmask defines described above.
 *
 */
CURLUCode curl_url_set(CURLURL *handle, CURLPIECE what,
                       char *part, unsigned int flags);
