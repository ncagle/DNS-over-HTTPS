# DOH implementation in curl

First PR is work in progress: https://github.com/curl/curl/pull/2668

## What works so far:

- Basic DOH using POST to the given DOH URL
- A and AAAA records are retrieved
- try [simeple-doh.c](https://gist.github.com/bagder/93092c51fdd5c49a967cc1e641a9f369)
- cleans up all memory, at least when all works

## Bootstrap

The DOH server is given with a host name that itself needs to be resolved. This initial resolve needs to be done by the native resolver before DOH kicks in. Or the address is provided with `--resolve` / `CURLOPT_RESOLVE`.

## DOH resolver

When a DOH-resolve is to get done, it will need to
1. issue the DOH resolve asynchronously
2. create one or two easy handles and associated HTTP transfers (`A` + `AAAA` resolves will need one request each)
3. add the easy handles to the multi handle to make the DOH-transfers perform
4. parse the DOH responses, feed the parsed resolve data into the DNS cache.
5. close the DOH easy handles
6. return the address data to the initial transfer that needed it, and continue 

## DOH-application

Code for a libcurl-using application doing DOH resolves: https://github.com/curl/doh