# Project Hyper-as-a-HTTP-backend-in-curl

Also known as curl+hyper. Or CH.

Pull-requests: [curl](https://github.com/curl/curl/pull/6110) and [Hyper](https://github.com/hyperium/hyper/pull/2278)

Explanatory blog post: [rust in curl with hyper](https://daniel.haxx.se/blog/2020/10/09/rust-in-curl-with-hyper/)

Persons involved: Daniel Stenberg (on curl) and Sean McArthur (on Hyper)

# Daniel's Work Log

## November 30, 2020

While work is progressing, there are numerous little things that are different between CH and "native". A list of the ones I'm currently dealing with:

1. removed leading space in header value (test 31)
2. multiple leading spaces in header value (test 31)
3. removes trailing space in header value (test 31)
4. bad chunk in chunked encoded body not reported as error (test 36)
5. Hyper can't return `CURLE_GOT_NOTHING` (test 30)
6. Hyper can't issue HTTP/1.0 requests (test 47)
7. Won't allow an all-caps `SET-COOKIE:` header unmodified? (test 61)

## November 27, 2020

- Test 30 is again complicated. It returns 52 (`CURLE_GOT_NOTHING`) for native curl but 56 (`CURLE_RECV_ERROR`) for CH. Because Hyper doesn't give us a detailed enough error code to figure this out...
- Test 1 - 29 OK.
- Test 28 has and tests an extra leading space in the content of a HTTP header, which in the Hyper case is stripped out before delivered to curl while it isn't in "native" curl, making the end saved result different and thus the test case currently fails. I "fixed" this by introducing a new "conditional" mode for test files that allows a test case to evaluate slightly differently depending on specific curl features.
- Fixed proxy auth
- Made curl -f work
- Fixed the receive byte countere

## November 26, 2020

- Test 1-15 run OK.

## November 25, 2020

- Test 11 works too now. Just needed to make sure curl ignores the body of the first request when it knows it will follow a redirect to another.
- I pulled down Sean's updates to the hyper-capi branch he did ten hours ago and **kaboom** now test 1 - 10 are all OK! I'll get to work on the test 11 failure.

## November 24, 2020

| Test | Status |
|------|--------|
| 1 - 3|  OK |
| 4    | Trailing space after header with no content (API flaw) |
| 5 - 7| OK |
| 8    | The HTTP/1 status line "reason" is missing (API flaw) |
| 9    | multipart formposting is only partially supported |
| 10   | PUT upload is only partially supported |




## November 23, 2020

- 10 of the first 20 tests run OK.
- Test 8 fails now because curl can't extract the "reason" from the status
  line (the first) in the HTTP responses, because Hyper has no API that
  provides it.
- Turns out I hadn't fixed cookies. Did now. Test 6 and 7: OK
- Fixed `Proxy-Connection: Keep-Alive` for proxies. Test 5: OK.
- Found out that [Hyper always adds a space after the
  colon](https://github.com/hyperium/hyper/pull/2278#pullrequestreview-536261198)
  in outgoing HTTP request headers even if there's no value set in
  them. libcurl does not do that, so now test 4 fails because CH has a space
  too much in the requests! :-/
- Made POSTs with CURLOPT_POSTFIELDS work. Test 1 - 3 work now!

## November 20, 2020

- Laid ground-work for request bodies with POST/PUT.
- Fixed `Authorization:` for the simple Basic case and now test 2 works!
- The test suite now detects if curl was built to use Hyper and if so, it will
  automatically force headers in HTTP tests to use CRLF newlines. The reason
  for this is that Hyper delivers headers to curl as name/value pairs, while
  the native HTTP engine provides the headers as-is. This means that a
  non-hyper curl will save headers with the delivered newline while a Hyper
  build always will save them with CRLF. By having the test code convert the
  test cases on the fly, no test cases need to be adapted and I deem this to
  be the change with the least friction that will now allow us to run the
  "real" test suite with unmodified tests with CH.

## November 18, 2020

- Cookies work.

## November 16, 2020

- Made sure curl now says "HTTP2 enabled" even when built without nghttp2. configure shouldn't allow both Hyper and nghttp2 to co-exist in the same build (as they're mutually exclusive) but I'm leaving that detail for later.
- Fixed the "request target" in HTTP requests so that they work with HTTP proxy. `curl -x localhost:80 http://curl.se` works fine now and so does doing `CONNECT` like with `curl -x localhost:80 https://curl.se`.
- Made the query part of the URL get passed on in the request correctly
- Setting referer with `-e` works as well

## November 13, 2020

- `curl -vIL https://curl.haxx.se` works fine and redirects to `https://curl.se` correctly
- Cleaned up the commit series

## November 12, 2020

- The `HEAD` issue was fixed when upgrading an underlying Rust component. (Pointed out to me by Sean.)
- Worked on splitting out response header parsing and status line functions today to re-use them from CH. I believe I will soon have to consider landing at least parts of the patch series to reduce merge conflict risks going forward.

## November 10, 2020

- Added calls to `hyper_error_print()` for error cases
- I got an issue with `HEAD` over HTTPS + h2 (probably a dupe of [hyper#2279](https://github.com/hyperium/hyper/issues/2279))

## November 6, 2020

- in sync with the hyper-capi branch of November 4
- fixed the torture test mistakes by making sure I use the API correctly
- rebased the work on top of the HSTS stuff that landed the other day, although HSTS is not even close to working with Hyper builds yet


## November 3, 2020

- "torture tests" on test case 1 brought up an interesting API issue (which turned out to be me not understanding it)
- Use the new API to enable H2 and now `curl https://curl.se` works as expected
- The travis CI job for CH ran green!

## November 2, 2020

- I'm adding a CI job to travis to build with Hyper and run test case 1 (with valgrind)
- The debug callback is now called with all the outgoing request headers, matching default libcurl behavior
- Custom provided headers are supported in the request 
- CH works fine to fetch `https://curl.se/` too, as long as I force it to speak HTTP/1.1 only - curl will default to HTTP/2 but so far I can't tell Hyper that...

## October 30, 2020

- I can run curl's test case 1 with CH! I only modified it slightly to use CRLF newlines for the response headers.
- With Sean's new updates and a cleanup of my code, I got rid of the memory leaks when I run my test command line with CH against my local Apache. Success!
- I made use of the new API to extract the HTTP version from the response. Used to create the status-line to send in the first header callback

Sean works on a new API for me:
 1. an API to extract the "status message", the text that is last on the first line of a HTTP/1.x response

Outstanding issues to ponder about:

### Case of incoming headers

~~Hyper lowercases them. libcurl passed them on as-is.~~ This is fixed!

### CRLF headers

curl deals with incoming HTTP responses headers using either LF or CRLF (or mixed) just fine and we have many test cases like that and with the right option curl will pass on the response as-is to the application. With Hyper I can only extract the headers without having a clue about the used newline so right now I "invent" CRLF separations when passing on the data to the application. It thus makes the content different and of different sizes for server responses using LF-only...

The solution is to a "hyper mode" for the test suite. It detects when CH runs and makes sure to always deliver HTTP headers with CRLF.

## October 21, 2020

I could issue a HTTP request to my local HTTP server using CH and get the response back correctly. Using the same HTTP 
