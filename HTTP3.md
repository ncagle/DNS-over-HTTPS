HTTP/3 support (**experimental**) has landed in master. We encourage you to build and try it out. 

## Build instructions

[Instructions](https://github.com/curl/curl/blob/master/docs/HTTP3.md)

## Still doesn't work

(mostly because enough time and effort hasn't been put into it yet)

- multiplexing (for quiche we await [issue #112](https://github.com/cloudflare/quiche/issues/112))
- push
- trailers

If you find other things that don't work, add them here (with details) or [file them as an issue](https://github.com/curl/curl/issues)!