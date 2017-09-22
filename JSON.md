# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

## `--json <data>`

    curl --json '{"msg": "$msg"}' http://example.com

- Sets the Content-Type: header in the request.

- Replaces the $msg with the environment variable called 'msg', and escapes it
  correctly according to JSON string rules

