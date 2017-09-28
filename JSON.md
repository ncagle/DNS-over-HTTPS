# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

## `--json -|<data>|@filename`

    curl --json '{"msg": "$msg"}' http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Replaces the $msg with the environment variable called 'msg', and escapes it
  correctly according to JSON string rules (but how would it know when to escape like a string and when it is other kinds of data?)

Should also support `-` to read JSON from stdin and `@filename` to read it from a given file.

## `--header-format=json`

    curl --dump-header header.json --header-format=json http://example.com/baz >body.json

    $ cat header.json
    {
      "http_code": 200,
      "headers": {
        "Content-Type": "application/json".
        "Last-Modified": "....",
        "ETag": "\"134a-6d5-530904afbe7c0|"",
        ...
     }
    }

## JSON response

Not needed. Pipe output to [jq](https://stedolan.github.io/jq/) or similar.