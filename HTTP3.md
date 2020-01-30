HTTP/3 support (**experimental**) has landed in master. We encourage you to build and try it out. 

## Build instructions

[Instructions](https://github.com/curl/curl/blob/master/docs/HTTP3.md)

## h3-25

As of January 30, 2020 curl speaks h3-25 with either backend.

## Still doesn't work

(mostly because enough time and effort hasn't been put into it yet)

- multiplexing (for quiche, a new API has been provided to map streams to `Curl_easy *`)
- push
- trailers
- `CURLINFO_CONNECT_TIME_T` and `CURLINFO_APPCONNECT_TIME_T` don't work (at least with quiche) [#4516](https://github.com/curl/curl/issues/4516)

If you find other things that don't work, add them here (with details) or [file them as an issue](https://github.com/curl/curl/issues)!