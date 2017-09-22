# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

## `--json <data>`

    curl --json '{"msg": "$msg"}' http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Replaces the $msg with the environment variable called 'msg', and escapes it
  correctly according to JSON string rules

## `--json-data`

    echo '{"msg": "foo"}' | curl --json-data http://example.com

- Makes a POST
- Sets a `Content-Type: application/json` header in the request.
- Streams POST body from stdin

## JSON response

When sending a JSON POST (enabling "JSON mode"), enable JSON response parsing as well:

- Prettify JSON reponse with syntax highlightning