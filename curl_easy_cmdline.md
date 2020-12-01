# `CURLcode curl_easy_cmdline(CURL *easy, char **line)`

Given an easy handle with populated options, return a *curl command line* that
would perform the same transfer as a null-terminated string.

The returned string **must** be freed with `curl_free()`.

## Brainstorm

This wiki page is meant for jotting down ideas and dreams.