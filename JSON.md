# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

## `--json -|<data>|@filename`

    curl --json '{"msg": "$msg"}' http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Replaces the $msg with the environment variable called 'msg', and escapes it
  correctly according to JSON string rules (but how would it know when to escape like a string and when it is other kinds of data?)

Should also support `-` to read JSON from stdin and `@filename` to read it from a given file.

## `--data={}`

If the first byte of the --data content starts with '{' or '[' use `application/json` as Content-type instead
of `application/x-www-form-urlencoded`.  If you really wanted `application/x-www-form-urlencoded` in that case
you could override it with --header.

Not completely backwards compatible.

## `--header-format=json`

    curl --dump-header header.json --header-format=json http://example.com/baz >body.json

    $ cat header.json
    {
      "http_code": 200,
      "headers": {
        "Content-Type": "application/json".
        "Last-Modified": "....",
        "ETag": "\"134a-6d5-530904afbe7c0\"",
        ...
     }
    }

A problem with "headers" is that it's not clear what to do about repeated headers.
The repeated header might also have their field name written with inconsistent
casing.  One option is to return it as an array:

    {
      "headers": [
        { "name": "Content-Type", "value": "application/json" },
        { "name": "Last-Modified", "value: "....",
        { "name": "ETag", "value": "\"134a-6d5-530904afbe7c0\"" }
      ]
    }

It's also inconvenient to not have fixed casing for the headers keys, so perhaps
keys should always be lower-cased:

    { "headers": {
        "content-type": "application/json",
        "last-modified": "....",
        "etag": "....",
    }

## `--write-out-json`

Writes all the supported --write-out variables in the form of a JSON object.  Something like:

    {
      "content_type": "text/html",
      "filename_effective": "example.html",
      "http_code": 200,
      ...
      "time_total": 453
    }

## `--accept=json|<content-type>|<majortype>/*`

Where `json` is just a shorthand for `application/json`.  This sets the "Accept:" header in the
request and checks that the Content-Type in the response is actually `application/json`. If the
response content type doesn't match it is treated as `--fail` (no output and status set to 22).

If `--accept=<content-type>` is repeated all listed types is acceptable.

## JSON response

Not needed. Pipe output to [jq](https://stedolan.github.io/jq/) or similar.

