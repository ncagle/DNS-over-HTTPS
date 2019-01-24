Misc notes about the coming [QUIC](QUIC) and HTTP/3 support in curl.

# API

## `CURLOPT_HTTP_VERSION`

Leave this to work for the *primary* HTTP request, which without additional
options is never h3.

## `CURLOPT_ALTSVC <filename>` (new)

When set, makes libcurl parse received `Alt-Svc:` headers and keep a cache in
memory that maps SOURCE-(PROTOCOL + HOST + PORT) to DEST-(PROTOCOL + HOST +
PORT) for AGE seconds.

Load cache file from filename or if "", just enable in memory.

For altsvc cache file format, see below.

## `CURLOPT_ALTSVC_CTRL <bitmask>` (new)

Instructs how to act on received `Alt-Svc:` headers.

- Re-issue immediately over new protocol. Makes libcurl halt the current
  transfer and instead switch over to the alternative after all headers have been received.
  By default, libcurl will use parsed headers for the *next* transfer.
- Accept protocol h1
- Accept protocol h2
- Accept protocol h3

If multiple alternatives are provided, we should also provide some ways to control how to traverse that list. Firefox for example have (experimental) racing of them *all* and sticking to the one that first connects successfully.

## `CURLOPT_H3 <bitmask>` (new)

Set HTTP/3 specific behavior flags.

`CURLH3_DIRECT` - When set, go straight to QUIC desthost + destport if we happen to know that exists and works and we don't want to bounce via an Alt-Svc response. Shortcuts (avoids) the altsvc cache.

# Command line options

## `--altsvc`

Enables the Alt-Svc parser in libcurl, in memory, and automatically supports all supported protocols in it. h1, h2, h3 according to what exists at build-time.

## `--altsvc-ctrl <command>`

If we think we need to provide this power to the user. I'm not sure so this should wait a little. Optionally, we can create a command line flag only for the "Re-issue immediately" option.

## `--http3-direct`

When used, this tells curl that the given URL is a host name + port that use QUIC directly. No alt-svc bouncing required.

# Implementation notes

## actions

### connect

Needs to do a QUIC connect instead of a TCP. And properly keep getting invoked until it has connected or failed.

### connected

When the QUIC connection is fine we need to find out and move on the state machine

### Send a HTTP/3 request

Should be similar logic to HTTP/2. We probably do the same from-HTTP/1-style conversion to HTTP/3 headers.

### disconnect

Disconnecting QUIC

# Alt-Svc cache

The cache is meant to keep associations that map SOURCE-(PROTOCOL + HOST + PORT) to DEST-(PROTOCOL + HOST +
PORT) for AGE seconds.

A map can be done in several stepe (the logic needs to also avoid loops).

The cache gets saved to disk when the handle is closed (if there is a file name). If is sharable between handles in a multi handle, and using the share interface. (Much like cookies)

The cache is transparently handled by libcurl and isn't really exposed to the user in other ways than it controls to what host it eventually connects.

If libcurl fails to connect to a host that it got by the altsvc cache, that cache entry should be flagged and not used anymore until it times out (it should possibly set its own negative-timeout expiry time?) and it should instead connect to another altsvc entry or the original host. 

A server's Alt-Svc response can also explicitly **clear** all the mapping for the current origin.

## File format

Store in plain ASCII text files, one line per entry, space-separated fields. Treat leading `#` as a comment line to skip.

`<source protocol> <source host name> <source port number> <dest protocol> <dest host name> <dest port number> <expire time> <Prio>`

 - source protocol = h1, h2, h2c, h3
 - source host name = the name used in the source URL
 - source port number = the port number in the source URL
 - dest protocol = alternative protocol: h1, h2, h2c, h3
 - dest host name = the name to use as alternative host
 - dest port number = the alternative port number
 - expiry time = The expire time as `YYYYMMDD HH:MM:SS` within quotes. Used to make expire times survive app/curl stops and restarts
 - persist - a `1` if the alternative was set with `persist = 1` in the header, otherwise `0`
 - prio = A signed int. The higher the more important (used if there are more than one entry for the same source). 0 means flagged for **not use**

An example line could then look like:

    h2 example.com 443 h3 shiny.example.com 8443 "20191231 00:00:00" 0 1
