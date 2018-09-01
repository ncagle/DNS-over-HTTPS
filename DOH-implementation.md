# DoH implementation in curl

First PR is work in progress: https://github.com/curl/curl/pull/2668

## What works so far:

- works with both easy and multi interfaces
- uses POST by default to the given DoH URL
- support for optional GET (which then appends `?dns=[packet]` to the URL)
- A and AAAA records are retrieved
- try [simple-doh.c](https://gist.github.com/bagder/93092c51fdd5c49a967cc1e641a9f369)
- cleans up all memory, at least when all works
- requires a HTTPS URL
- Sets time-out for the DoH requests (based on the main transfer timeouts)
- supports IPv4-only and IPv6-only requests (based on main transfer options)
- curl's `--doh-url` option sets the DoH server with the command line tool
- unit tests for encoding/decoding and error checks in test 1650
- basic DoH test with curl in test 2100

## TODO

- Offer GET support via CURLOPT_*
- Consider how to "inherit" proxy setting
- inherit CA cert options from main transfer
- verify the response `Content-Type` before using it
- parse the URL as a "URI Template" as the spec dictates

## Questions

- user-agent?
- HTTP auth support?
- how to set VERBOSE for the DOH requests

## Bootstrap

The DoH server is given with a host name that itself needs to be resolved. This initial resolve needs to be done by the native resolver before DoH kicks in. Or the address is provided with `--resolve` / `CURLOPT_RESOLVE`.

## DoH resolver

When a DoH resolve is to get done, it will need to
1. issue the DoH resolve asynchronously
2. create one or two easy handles and associated HTTP transfers (`A` + `AAAA` resolves will need one request each)
3. add the easy handles to the multi handle to make the DoH transfers perform
4. parse the DoH responses, feed the parsed resolve data into the DNS cache.
5. close the DoH easy handles
6. return the address data to the initial transfer that needed it, and continue 

The DoH requests are done by two easy handles being added to the multi handle, and when those transfers are complete, they are removed and cleaned up transparently without that being notable for applications. **Note:** The number of `running_handles` returned from for example `curl_multi_perform` will include these two extra transfers and this is observable by applications.

## DoH application

Code for a libcurl-using application doing DoH resolves: https://github.com/curl/doh