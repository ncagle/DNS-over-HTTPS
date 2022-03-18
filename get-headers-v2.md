# An HTTP header access API (v2)

This was proposal v2, v1 is in [A header access API](get-headers.md).

The work on implementing takes places in [PR 8593](https://github.com/curl/curl/pull/8593). The API has already been changed a bit in that PR compared to this wiki page. This page will be removed when the PR lands, to keep the proper documentation at a single place: the libcurl man pages.

Designed for HTTP(S). Headers are available in the easy handle after and
during a transfer.

[Feedback here](https://github.com/curl/curl/discussions/8496)

Below are the man pages for the two new functions. Generated from the PR
content 2022-03-18 12:17 UTC.

----

NAME
====

curl\_easy\_header - get a HTTP header

SYNOPSIS
========

    #include <curl/curl.h>

    CURLHcode curl_easy_header(CURL *easy,
                               const char *name,
                               size_t index,
                               unsigned int origin,
                               int request,
                               struct curl_header **hout);

DESCRIPTION
===========

EXPERIMENTAL feature!

*curl\_easy\_header(3)* returns a pointer to a \"curl\_header\" struct in **hout** with data for the HTTP response header *name*. The case insensitive nul-terminated header name should be specified without colon.

*index* 0 means asking for the first instance of the header. If the returned header struct has **amount** set larger than 1, it means there are more instances of the same header name available to get. Asking for a too big index makes**CURLHE\_BADINDEX** get returned.

The *origin* argument is for specifying which headers to receive, as a single HTTP transfer might provide headers from several different places and they may then have different importance to the user and headers using the same name might be used. The *origin* is a bitmask for what header sources you want. See the descriptions below.

The *request* argument tells libcurl from which request you want headers from. A single transfer might consist of a series of HTTP requests and this argument lets you specify which particular invidual request you want the headers from. 0 being the first request and then the number increases for further redirects or when multi-state authentication is used. Passing in -1 is a shortcut to \"the last\" request in the series, independently of the actual amount of requests used.

libcurl stores and provides the actually used \"correct\" headers. If for example two headers with the same name arrive and the latter overrides the former, then only the latter will be provided. If the first header survives the second, then only the first one will be provided. An application using this API does not have to bother about multiple headers used wrongly.

The memory for the returned struct is associated with the easy handle and subsequent calls to *curl\_easy\_header(3)* will clobber the struct used in the previous calls for the same easy handle. Applications need to copy the data if it wants to keep it around. The memory used for the struct gets freed with calling *curl\_easy\_cleanup(3)* of the easy handle.

The first line in a HTTP response is called the status line. It is not considered a header by this function. Headers are the \"name: value\" lines following the status.

This function can be used before (all) headers have been received and is fine to call from within libcurl callbacks. It will always return the state of the headers at the time it is called.

The header struct
=================

    struct curl_header {
       char *name;
       char *value;
       size_t amount;
       size_t index;
       unsigned int origin;
       void *anchor;
    };

The data **name** field points to, will be the same as the requested name but it might have a different case.

The data **value** field points to, comes exactly as delivered over the network but with leading and trailing whitespace and newlines stripped off. The \`value\` data is nul-terminated.

**amount** is how many headers using this name that exist, within the origin and request scope asked for.

**index** is the zero based entry number of this particular header, which in case this header was used more than once in the requested scope can be larger than 0 but is always less than **amount**.

The **origin** field in the \"curl\_header\" struct has one of the bits set, indicating where from the header originates.

**anchor** is a private handle used by libcurl internals. Do not modify.

ORIGINS
=======

-   The header arrived as a header from the server.

-   The header arrived as a trailer. A header that arrives after the body.

-   The header arrived in a CONNECT response. A CONNECT request is being done to setup a transfer \"through\" a HTTP(S) proxy.

-   The header arrived in a HTTP 1xx response. A 1xx response is an \"intermediate\" response that might happen before the \"real\" response.

-   The header is a HTTP/2 or HTTP/3 pseudo header

EXAMPLE
=======

    struct curl_header *type;
    CURLHcode h =
      curl_easy_header(easy, "Content-Type", 0, CURLH_HEADER, &type);

AVAILABILITY
============

Added in 7.83.0

RETURN VALUE
============

This function returns a CURLHcode indiciating success or error.

-   There is no header with the requested index.

-   No such header exists.

-   No headers at all have been recorded.

-   There was no such request number.

-   Out of resources

-   One or more of the given arguments are bad.

-   HTTP or the header API has been disbled in the build.

SEE ALSO
========

**curl\_easy\_nextheader**(3), **curl\_easy\_perform**(3)

----

NAME
====

curl\_easy\_nextheader - get the next HTTP header

SYNOPSIS
========

    #include <curl/curl.h>

    struct curl_header *curl_easy_nextheader(CURL *easy,
                                             unsigned int origin,
                                             int request,
                                             struct curl_header *prev);

DESCRIPTION
===========

EXPERIMENTAL feature!

This function lets an application iterate over all previously received HTTP headers.

The *origin* argument is for specifying which headers to receive, as a single HTTP transfer might provide headers from several different places and they may then have different importance to the user and headers using the same name might be used. The *origin* is a bitmask for what header sources you want. See the *curl\_easy\_header(3)* man page for the origin descriptions.

The *request* argument tells libcurl from which request you want headers from. A single transfer might consist of a series of HTTP requests and this argument lets you specify which particular invidual request you want the headers from. 0 being the first request and then the number increases for further redirects or when multi-state authentication is used. Passing in -1 is a shortcut to \"the last\" request in the series, independently of the actual amount of requests used.

It is suggested that you pass in the same **origin** and **request** when iterating over a range of headers as changing the value mid-loop might give you unexpected results.

If *prev* is NULL, this function returns a pointer to the first header stored within the given scope (origin + request).

If *prev* is a pointer to a previously returned header struct, *curl\_easy\_nextheader(3)* returns a pointer the next header stored within the given scope. This way, an application can iterate over all availble headers.

The memory for the struct this points to, is owned and managed by libcurl and is associated with the easy handle. Applications must copy the data if they want it to survive subsequent API calls or the life-time of the easy handle.

EXAMPLE
=======

    struct curl_header *prev = NULL;
    struct curl_header *h;

    /* extract the normal headers from the first request */
    while((h = curl_easy_nextheader(easy, CURLH_HEADER, 0, prev))) {
       print "%s: %s\n", h->name, h->value);
       prev = h;
    }

    /* extract the normal headers + 1xx + trailers from the last request */
    unsigned int origin = CURLH_HEADER| CURLH_1XX | CURLH_TRAILER;
    while((h = curl_easy_nextheader(easy, origin, -1, prev))) {
       print "%s: %s\n", h->name, h->value);
       prev = h;
    }

AVAILABILITY
============

Added in 7.83.0

RETURN VALUE
============

This function returns the next header, or NULL when there are no more (matching) headers or an error occurred.

If this function returns NULL when *prev* was set to NULL, then there are no headers available within the scope to return.

SEE ALSO
========

**curl\_easy\_header**(3), **curl\_easy\_perform**(3)
