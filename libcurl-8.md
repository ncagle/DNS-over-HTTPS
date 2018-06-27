At some point we should bump the libcurl version number to 8 and in that same move, bump the soname and clean up some of the legacy functions and garbage we've carried with us for many years. Discussion at https://github.com/curl/curl/pull/1981

# Functions to remove - and why

## curl_getenv

Not transfer related, not necessary for libcurl-using applications.

## curl_*printf family

(10 different functions!)

Not transfer related, not necessary for libcurl-using applications. Discouraged for applications since 2004.

Removing them will allow us to trim them, both in features and in performance. Reduces "attack surface" too, as we've had at least one CVE in this code (for features curl itself doesn't use).

## curl_strequal

Not transfer related, not necessary for libcurl-using applications.

## curl_strnequal

Not transfer related, not necessary for libcurl-using applications.

## curl_getdate

Not transfer related, not necessary for libcurl-using applications.

## curl_multi_socket

Replaced with curl_multi_socket_action

## curl_multi_socket_all

Replaced with curl_multi_socket_action

## curl_formadd

Replaced by the curl_mime_* family.

## curl_formfree

Replaced by the curl_mime_* family.

## curl_formget

Hardly used, not necessary for applications doing transfers with curl. Does not have a implementation in curl_mime_*.

## curl_escape

Replaced by curl_easy_escape

## curl_unescape

Replaced by curl_easy_unescape

# curl_easy_setopt options to remove - and why

## CURLOPT_DNS_USE_GLOBAL_CACHE

It uses global variables without locking. Really bad.

# Protocols to remove - and why

## TELNET

Was never a good match for curl, has always been quirky to use and has always had a very small amount of users.