(The URL API was added to libcurl 7.62.0)

# Include

You still only include `<curl/curl.h>` in your code.

# Create, cleanup, duplicate

Create a handle that holds URL info and resources:

~~~c
  CURLU *h = curl_url();
~~~

When done with it, clean it up:

~~~c
  curl_url_cleanup(h);
~~~

When you need a copy of a handle, just duplicate it:

~~~c
  CURLU *nh = curl_url_dup(h);
~~~

# Parse a URL

~~~c
  rc = curl_url_set(h, CURLUPART_URL, "https://example.com:449/foo/bar?name=moo", 0);
~~~

(The zero in the function call is bitmask for changing specific features.)

If successful, this stores the URL in its individual parts within the handle.

# Redirect to a relative URL

When the handle already has parsed a URL, setting a relative URL will make it
"redirect" to adapt to it.

~~~c
  rc = curl_url_set(h, CURLUPART_URL, "../test?another", 0);
~~~

# Get a URL

The `CURLU` handle represents a URL and you can easily extract that:

~~~c
  char *url;
  rc = curl_url_get(h, CURLUPART_URL, &url, 0);
  curl_free(url);
~~~

(The zero in the function call is bitmask for changing specific features.)

# Get individual URL parts

When a URL has been parsed or parts have been set, you can extract those pieces from the handle at any time.

~~~c
  rc = curl_url_get(h, CURLUPART_HOST, &host, 0);
  rc = curl_url_get(h, CURLUPART_SCHEME, &scheme, 0);
  rc = curl_url_get(h, CURLUPART_USER, &user, 0);
  rc = curl_url_get(h, CURLUPART_PASSWORD, &password, 0);
  rc = curl_url_get(h, CURLUPART_PORT, &port, 0);
  rc = curl_url_get(h, CURLUPART_PATH, &path, 0);
  rc = curl_url_get(h, CURLUPART_QUERY, &query, 0);
  rc = curl_url_get(h, CURLUPART_FRAGMENT, &fragment, 0);
~~~

Extracted parts are not URL decoded unless the user asks for it with the `CURLU_URLDECODE` flag.

Remember to free the returned string with `curl_free` when you're done with it!

# Set individual URL parts

A user can opt to set individual parts, either after having parsed a full URL
or instead of parsing such. 

~~~c
  rc = curl_url_set(urlp, CURLUPART_HOST, "www.example.com", 0);
  rc = curl_url_set(urlp, CURLUPART_SCHEME, "https", 0);
  rc = curl_url_set(urlp, CURLUPART_USER, "john", 0);
  rc = curl_url_set(urlp, CURLUPART_PASSWORD, "doe", 0);
  rc = curl_url_set(urlp, CURLUPART_PORT, "443", 0);
  rc = curl_url_set(urlp, CURLUPART_PATH, "/index.html", 0);
  rc = curl_url_set(urlp, CURLUPART_QUERY, "name=john", 0);
  rc = curl_url_set(urlp, CURLUPART_FRAGMENT, "anchor", 0);
~~~

Set parts are not URL encoded unless the user asks for it with the `CURLU_URLENCODE` flag.

# Append to the query

An application can append a string to the right end of the query part with the `CURLU_APPENDQUERY` flag.

Imagine a handle that holds the URL `https://example.com/?shoes=2`. An application can then add the string `hat=1` to the query part like this:

~~~c
  rc = curl_url_set(urlp, CURLUPART_QUERY, "hat=1", CURLU_APPENDQUERY);
~~~

It will even notice the lack of an ampersand (`&`) separator so it will inject one too, and the handle's full URL would then equal `https://example.com/?shoes=2&hat=1`.

The appended string can of course also get URL encoded on add, and if asked, the encoding will skip the '=' character. For example, append `candy=M&M` to what we already have, and URL encode it to deal with the ampersand in the data:

~~~c
  rc = curl_url_set(urlp, CURLUPART_QUERY, "candy=M&M", CURLU_APPENDQUERY | CURLU_URLENCODE);
~~~

Now the URL looks like `https://example.com/?shoes=2&hat=1&candy=M%26M`.

# CURLOPT_CURLU

(not yet implemented)

It makes sense to also add an option that allows a `CURLU *` to be passed to libcurl as a URL instead of the traditional `CURLOPT_URL`.
