HTTP/3 support (**experimental**) has landed in master. We encourage you to build and try it out. 

## Build instructions

[Instructions](https://github.com/curl/curl/blob/master/docs/HTTP3.md)

## h3-27

As of March, 2020 curl speaks h3-27 with either backend.

## Still doesn't work

(mostly because enough time and effort hasn't been put into it yet)

- certificates (we need to make sure the checks work and can be disabled like before, that we can provide custom certs like for other connections and we need to show cert info in the verbose output like "normally") [#5038](https://github.com/curl/curl/issues/5038)

- multiplexing (for quiche, a new API has been provided to map streams to `Curl_easy *`)
- push
- trailers
- `CURLINFO_CONNECT_TIME_T` and `CURLINFO_APPCONNECT_TIME_T` don't work (at least with quiche) [#4516](https://github.com/curl/curl/issues/4516)

If you find other things that don't work, add them here (with details) or [file them as an issue](https://github.com/curl/curl/issues)!

## HTTP/3 tests

We don't have any HTTP/3 testing at all in the test suite. One approach to get it going, is probably to use a h3<=>h1 proxy so that we can keep using `sws` for the backend HTTP contents etc. We have this setup working for h2.

## qlog

qlog is a common QUIC logging format and it would be helpful if curl could be told to output qlogs for easier QUIC level debugging.