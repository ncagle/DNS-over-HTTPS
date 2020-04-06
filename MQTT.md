The code is being worked on in PR [#5173](https://github.com/curl/curl/pull/5173)

## Issues to figure out

### 1. How to deliver the responses


 Right now, the response to a subscribe can be one or many publishes, each of each will send the following data to the write callback/output:

    [2 byte topic size][topic][payload]

The response is entirely binary.

### 2. The command line tool's handling of responses

The above described binary method is probably less convenient for shell scripts and other users of the command line tool.