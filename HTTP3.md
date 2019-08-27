HTTP/3 support (**experimental**) has landed in master. We encourage you to build and try it out. 

 - [q] = specific for the quiche backend
 - [n] = specific for the ngtcp2 backend

## Build instructions

[Instructions](https://github.com/curl/curl/blob/master/docs/HTTP3.md)

- The [n] build broke on Aug 26 2019 and has not been fixed yet

## HTTP/3 Test servers

[a list](https://bagder.github.io/HTTP3-test/)

## Still doesn't work

- multiplexing (for [q] we await [issue #112](https://github.com/cloudflare/quiche/issues/112))

If you find other things that don't work, add them here (with details) or [file them as an issue](https://github.com/curl/curl/issues)!