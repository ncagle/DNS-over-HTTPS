# A header access API?

Replaced by [proposal v2](https://github.com/curl/curl/wiki/get-headers-v2)

Question: should this be for HTTP only?

Question: should this require being enabled in the request or should it always
do it?

## Get a specific header

    char *curl_easy_header(CURL *easy, const char *name);

Returns a pointer to the value for the header `name` (name specified *without*
colon and needs to be nul-terminated).

The contents of the returned value is exactly as delivered over the network
but without the trailing newline or CRLF pair. The data is nul-terminated.

Example:

    char *type = curl_easy_header(easy, "Content-Type");

Question: how about repsonses with multiple headers using the same name ? Bad
ones like Content-Length or accepted ones like cookies.

Question: should we differ between "there was no header using this name in the
response" and "there was no response at all so no headers were returned" in
the return? Or how about "there were *two* headers using this name in the
response".

Question: leading and trailing whitespace trim? I think leave in as delivered.

## List all headers

    struct curl_slist *curl_easy_getheaders(CURL *easy);

Returns a pointer to a linked list with header names, in the order of their
appearances in the response using the original casing (for HTTP/1, as for
later HTTP versions they are always lowercase). The list only contains the
header names, not the values that can be extracted with `curl_easy_header()`.

Question: what if the response contains two headers of the same name, how
should the application get the *second* value?
