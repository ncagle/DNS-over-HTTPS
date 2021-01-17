Every transfer in libcurl can be associated with one connection (or none).

## data

the name we use internally for pointing to the main transfer object

## conn

the name we use internally for connection objects

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
