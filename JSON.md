# JSON awareness in the curl tool

This page is for brainstorming and gather ideas and suggestions on how to improve curl when used to send and receive JSON formatted data.

These are **ideas** and **a proposal**. We can still improve, discard, replace and add to them.

Discuss it [here](https://github.com/curl/curl/discussions/8312) also seen on [hackernews](https://news.ycombinator.com/item?id=30011382) and [reddit](https://www.reddit.com/r/programming/comments/s8puao/curl_to_add_native_json_support/)

## `--json -|<data>|@filename`

    curl --json [whatever] http://example.com

A shortcut. Equals doing `-d [whatever] -H "Content-Type: application/json"`. This also supports `-` to read JSON from stdin and `@filename` to read it from a given file. Does not check/verify that the data is actually conforming JSON.

## `--jp [part]`

('jp' as short for "JSON part")

Build a JSON request body, and use the request header `Content-Type:
application/json`.

Multiple `--jp` options can be provided on the same command line to add
multiple parts to the body.

**[part]** is an instruction how to build JSON content

The idea is to be able to create and pass on most simple JSON data bodies and
allow scripts and users to pass in parts of that data as shell variables etc
when required (== handle quoting conveniently).

(Syntax inspired by [jo](https://github.com/jpmens/jo/blob/master/jo.md))

## Idea of how it could work

Input:

    --jp a=b

Body sent:

    {
       "a": "b"
    }

Input:

    --jp a=b --jp c=d --jp e=2 --jp f=false

Body:

    {
       "a": "b",
       "c": "d",
       "e": 2,
       "f": false
    }

Input:

    --jp ":list Monday, Tuesday, Wednesday, Thursday"

Body:

    [
      "Monday",
      "Tuesday",
      "Wednesday",
      "Thursday"
    ]

Input:

    --jp map=europe --jp prime[]=13 --jp prime[]=17 --jp target[x]=-10 --jp target[y]=32

    {
      "map": "europe",
      "prime": [
        13,
        17
      ],
      "target": {
        "x": -10,
        "y": 32
      }
    }


## JSON response

Not particular handling. Pipe output to [jq](https://stedolan.github.io/jq/) or similar.

