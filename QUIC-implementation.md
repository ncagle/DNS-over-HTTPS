Misc notes about the coming QUIC and HTTP/3 support in curl.

# API

## `CURLOPT_HTTP_VERSION`

Leave this to work for the *primary* HTTP request, which without additional
options is never h3.

## `CURLOPT_ALTSVC <filename>` (new)

When set, makes libcurl parse received `Alt-Svc:` headers and keep a cache in
memory that maps SOURCE-(PROTOCOL + HOST + PORT) to DEST-(PROTOCOL + HOST +
PORT) for AGE seconds.

Load cache file from filename or if "", just enabled it in memory.

- This cache should get saved to disk when the handle is closed. (Like
  cookies.)

- This cache should become sharable between handles in a multi handle, and
  using the share interface. (Like cookies)

For Alt-Svc cache file format, see below.

## `CURLOPT_ALTSVC_CTRL <bitmask>` (new)

Instructs how to act on received `Alt-Svc:` headers.

- Re-issue immediately over new protocol. Makes libcurl halt the current
  transfer and instead switch over to the alternative after all headers have been received.
  By default, libcurl will use parsed headers for the *next* transfer.
- Accept protocol h1
- Accept protocol h2
- Accept protocol h3

If multiple alternatives are provided, we should also provide some ways to control how to traverse that list. Firefox for example have (experimental) racing of them *all* and sticking to the one that first connects successfully.

## direct-to-h3

To ponder about is how to ask libcurl to go straight to QUIC desthost + destport if we happen to know that exists and works and we don't want to bounce via an Alt-Svc response. Possibly by having an option allowing pre-populating the altsvc cache similar to `CURLOPT_RESOLVE` for the dns cache.

We should also offer a shortcut to have libcurl use the host + port from the URL as the quic host and port.

It might also be done differently for the command line tool.

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

# Alt-Svc cache file

Store in plain ASCII text files, one line per entry. Treat leading `#` as a comment line to skip.

|source protocol | source host name | source port number | dest protocol | dest host name | dest port number | expire time|
|--|--|--|--|--|--|--|
| h1, h2, h2c, h3 | the name used in the source URL  | the port number in the source URL | alternative protocol: h1, h2, h2c, h3 | the name to use as alternative host | the alternative port number | The expire time in YYYYMMDDHHMMSS. This is necessary to make expire times survive app/curl stops and restarts |

An example line could then look like:

    h2 example.com 443 h3 shiny.example.com 8443 20191231000000
