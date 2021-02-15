Every transfer in libcurl can be associated with one connection (or none).

## data

the name we use internally for pointing to the main transfer object: `struct Curl_easy`

## conn

the name we use internally for connection objects: `struct connectdata`

## `data->conn`

This is the pointer in the transfer struct that pointers to the connection currently used.

## `conn->data`

**Danger!** This is the pointer in the connection struct that points to the *current owner* of the connection. This changes often and rapidly since a connection can be multiplexed by multiple and many transfers. The existence and use of this pointer is error prone and should be subject for removal over time.

## Current status

At January 8, 2021:
~~~shell
$ git grep 'conn->data'  | wc -l
939
~~~

|Date| count | comment |
|----|-------|---------|
|Jan 26 | 39 | with [f2f91ac709bcfc](https://github.com/curl/curl/commit/f2f91ac709bcfc)
|Jan 26 | 40 | with [234638ea63fac](https://github.com/curl/curl/commit/234638ea63fac)
|Jan 26 | 67 | with [1dc8aa870e879d3](https://github.com/curl/curl/commit/1dc8aa870e879d3)
|Jan 24 | 89 | with [ecb13416](https://github.com/curl/curl/commit/ecb13416)
|Jan 22 | 120 | with [14e075d1a7fd](https://github.com/curl/curl/commit/14e075d1a7fd)
|Jan 22 | 122 | with [8335c6417ea21bd](https://github.com/curl/curl/commit/8335c6417ea21bd)
|Jan 21 | 149 | with [5a19cb5a3c](https://github.com/curl/curl/commit/5a19cb5a3c)
|Jan 21 | 154 | with [c977a6d0dc2](https://github.com/curl/curl/commit/c977a6d0dc2)
|Jan 20 | 162 |  |
|Jan 19 | 172 | fixed quic backends in [2bdec0b3636e113](https://github.com/curl/curl/commit/2bdec0b3636e)
|Jan 19 | 198 | fixed ftplistparser.c
|Jan 19 | 203 | landed [#6479](https://github.com/curl/curl/pull/6479)
|Jan 18 | 367 | landed [#6425](https://github.com/curl/curl/pull/6425)
|Jan 11 | 919 | Fixed the grep, it should be for `'conn->data\W'` :grin: 


## How to do it

Removing the use in one big sweep is deemed too much work and too big a change for us to muster. However, we can move *towards* this goal by taking small steps every now and then.

In many places in the code, we can make sure to pass *both* `data` and `conn` to functions that need access to both.

For functions that are transfer-oriented, we should rather *just* pass `data` to them as the connection can be inferred from that.

Functions that *only* gets `conn` passed to them **should not** do things for the transfer, as we need to stop assuming we know the transfer based on the connection.

## counter.sh
~~~shell
#!/bin/sh
total=`git grep  'conn->data\W'  | wc -l`

git grep -c 'conn->data\W'  | sort -k2 -t: -g

echo "Total: $total"
