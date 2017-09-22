# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

## `--json <data>`

    curl --json '{"msg": "$msg"}' http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Replaces the $msg with the environment variable called 'msg', and escapes it
  correctly according to JSON string rules (but how would it know when to escape like a string and when it is other kinds of data?)

Should also support `-` to read JSON from stdin and `@filename` to read it from a given file.

## `--json-data`

    echo '{"msg": "foo"}' | curl --json-data http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Streams POST body from stdin

(this can probably be supported by `--json -` in the same style `-d` and friends already work)

## JSON response

When sending a JSON POST (enabling "JSON mode"), enable JSON response parsing as well:

- Prettify JSON reponse with syntax highlightning

(this is probably superfluous and should be replaced by piping output to [jq](https://stedolan.github.io/jq/))