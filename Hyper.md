# Project Hyper-as-a-HTTP-backend-in-curl

Also known as curl+hyper. Or CH.

Initial work is merged into master in both curl and Hyper.

Explanatory blog post: [rust in curl with hyper](https://daniel.haxx.se/blog/2020/10/09/rust-in-curl-with-hyper/)

Persons involved: Daniel Stenberg (on curl) and Sean McArthur (on Hyper)

# Outstanding work

The first phase is to (slowly) go through all tests and make sure they run as
fine with Hyper as with the native backend.

Some of the funtionality still not "there" yet include:

- multiplexed HTTP/2
- h2 Upgrade:
- pausing transfers
- receiving HTTP/1 trailers
- sending HTTP/1 trailers
- HTTP/0.9 (I've been informed Hyper supports this now but lacks C API access)

# Daniel's Work Log

## November 19, 2021

- Fixed the HA proxy protocol support, enabled two more tests.

At **32** disabled tests.

## October 27, 2021

- I verified that DoH works with hyper builds
- I verified that both QUIC/h3 backends work fine in combination with hyper
- Unified handling of "too low" HTTP response codes and now test 1430 works

At **34** disabled tests.

## October 26, 2021

- Disabled test 1294 since native libcurl supports "crazier" HTTP request
  headers than hyper does. Hyper is strict, libcurl is liberal.
- Made `CURLOPT_SUPPRESS_CONNECT_HEADERS` work with hyper
- test 1266/1267: disabled on hyper: no HTTP/0.9 support
- test 1287 need a massage to work

At **42** disabled tests.

## October 25, 2021

- Found a few more disabled tests that actually work now since a recent fix
- Adjusted a few HTTP/0.9 tests not just not run with Hyper since it doesn't support
- Adjusted some more tests to not run with hyper due to lack of support

At **47** disabled tests.

## October 22, 2021

- I'm back. Iterating over the disabled tests one by one. Some tests need a
  little editing, some have been disabled because hyper doesn't support
  everything. Some needed bug-fixes.

At **57** disabled tests.

## September 6, 2021

- David Cook spotted how [hyper doesn't provide enough API
  powers](https://github.com/curl/curl/issues/7679) to issue correct h2 psuedo
  headers which in turn makes curl fail when talking h2 to for example
  `google.com`...

## September 1, 2021

- Fixed an output issue with TFTP that made the test suite wrongly apply
  "hyper mode" which made some TFTP tests fail with curl+hyper. Fixed now.

At **64** disabled tests.

## August 31, 2021

- The Transfer-Encoding issue turned out to be a curl problem, not a hyper
  one. With the landing of [#7649](https://github.com/curl/curl/pull/7649) the
  treatment has been unified and now even more tests are enabled in hyper
  builds.

At **67** disabled tests.

## August 26, 2021

- Made the built-in HTTP code similar to hyper and reject >3 digit response
  codes and enabled test 1432 for hyper too.
- Tweaked two more tests to work with hyper
- Started [transfer-encoding discussion](https://github.com/hyperium/hyper/discussions/2633) in hyper

At **73** disabled tests.

## August 23, 2021

- Went through more tests that could be enabled now with the 1xx support.
- Fixed a few smaller issues
- Fixed HTTP/1.1 => HTTP/1.0 downgrades
- Fixed Expect: 100-continue with `CURLOPT_POSTFIELDS`
- Made `CURLOPT_IGNORE_CONTENT_LENGTH` work in hyper builds again (for FTP)

At **76** disabled tests.

## August 20, 2021

Sean fixed hyper 1xx responses in hyper, and with
[#7597](https://github.com/curl/curl/pull/7597) landed it seems to work more
in curl with tests 155 and 158 enabled. At **93** disabled tests.

## August 14, 2021

Landed initial support for 100-continue. Made test 154 run in hyper CI builds.
**97** tests remain disabled for hyper.

## July 2021

Worked on fixing more details in the hyper build to work like built-in HTTP.

## June 8, 2021

Tests that fail when built with hyper are now disabled by default in hyper
builds, which allows us to run "all tests" in CI jobs. There are **106**
tests disabled, many of them are using `Expect: 100-continue`.

## January 12, 2021

- `190 tests out of 198 reported OK: 95%` (Tests 1 to 199)

| Test | Area                                                |
|------|-----------------------------------------------------|
| 90   | NTLM via --anyauth                                  |
| 94   | auth over CONNECT                                   |
| 154  | PUT with --anyauth authorization (picking Digest)   |
| 155  | PUT with --anyauth authorization (picking NTLM)     |
| 158  | multipart formpost with only a 100 reply            |
| 159  | NTLM authorization when talking HTTP/1.0            |
| 176  | POST --ntlm to server not requiring any auth at all |
| 178  | response with negative Content-Length               |

## January 8, 2021

- To make test 178 work, we would benefit from more details from Hyper. Discussing with Sean.
- Fixed test 179

- `185 tests out of 198 reported OK: 93%` (Tests 1 to 199)

| Test | Area                                                  |
|------|-------------------------------------------------------|
| 88   | PUT with Digest authorization                         |
| 90   | NTLM via --anyauth                                    |
| 94   | auth over CONNECT                                     |
| 154  | PUT with --anyauth authorization (picking Digest)     |
| 155  | PUT with --anyauth authorization (picking NTLM)       |
| 158  | multipart formpost with only a 100 reply              |
| 159  | NTLM authorization when talking HTTP/1.0              |
| 170  | POST with --proxy-ntlm and no SSL with no response    |
| 175  | POST --digest to server not requiring any auth at all |
| 176  | POST --ntlm to server not requiring any auth at all   |
| 177  | POST --digest to server doing a 302-location          |
| 178  | response with negative Content-Length                 |
| 179  | using proxy and cookies with path checks              |

## January 5, 2021

- **96/99 tests pass**
- made CONNECT work
- fixed a bad use of the Hyper API that made test 36 fail
- made libcurl do `CURLE_GOT_NOTHING` correctly with Hyper (test 30)
- skip HTTP/0.9 since Hyper doesn't support it
- The outstanding test failures among the first 99 are:

| Test  | Area                   |
|-------|------------------------|
| 88 90 | Auth related           |
| 94    | HTTP auth over CONNECT |

## December 30, 2020

- **86/99 tests work**
- Fixed HTTP auth with Digest and NTLM. Test 64, 65, 67, 68, 69, 70, 72: OK ([#6390](https://github.com/curl/curl/pull/6390))
- time conditions (test 77-78) are OK! [#6391](https://github.com/curl/curl/pull/6391)

## December 18, 2020

- Merged the first 10 commits into master and closed
  [#6110](https://github.com/curl/curl/pull/6110). As this is a pretty big
  changed of the `http.c` file I wanted this merged to reduce the risk for
  futher merge conflicts. This merge should not affect the default curl build
  at all, but will enable curious parties to build curl with Hyper using the
  plain master branch of curl. You still need the `hyper-capi` branch of
  Hyper to build the necessary C API.

## December 16, 2020

- Continuing from yesterday. I need to fix
  [#6328](https://github.com/curl/curl/pull/6328) first (which I discovered
  while investiging a failure in the Hyper branch for a non-Hyper build using
  wolfSSL for TLS), while I've been working on this the Github actions CI
  started to fail, so I had to first fix
  [#6332](https://github.com/curl/curl/pull/6332) and then come back to make
  sure 6228 builds fine...

## December 15, 2020

- Fixing test failures with and without Hyper enabled

## December 14, 2020

Cleanining up the branch and the commits in preparation for an initial merge.

## December 11, 2020

Status: 77 of the first 99 tests run OK

- I merged all the changes to `runtests.pl` I had done in this branch.
  Primarily for the new conditional stuff but I let the "hyper mode" go with
  it to not complicate matters.
- Sean updated `hyper-capi` to help me better return the error back from the
  body write callback.
- Test 38 OK!
- Test 43 OK!
- Test 56 OK!
- Test 60 OK!

## December 10, 2020

- `28 files changed, 2973 insertions(+), 1317 deletions(-)`
- we run 29 tests in the CI now
- preparing for initial merge of patch set into curl master post the curl 7.74.0 release
- changed the configure output for Hyper detection

Out of the first 99 HTTP tests, these are the **26** tests that still fail.
Some seem to be due to lack of Hyper (API) support but most of them are just
integration related.

| Test   | Status |
|--------|--------|
| 30     | Hyper doesn't detect "no data" like native |
| 36     | Hyper doesn't detect bad chunked Transfer-Encoding like native |
| 37     | Hyper doesn't detect "no data" like native |
| 38     | refused resume, needs work |
| 43     | redirects over HTTP proxy |
| 56     | HUGE chunked transfer-encoded POST |
| 60     | PUT from stdin with wrong content-length |
| 64,65  | Digest auth |
| 66     | HTTP/0.9 response |
| 67-70  | NTLM auth |
| 72     | auth |
| 77-78  | `-z` |
| 80     | CONNECT and auth |
| 81     | proxy and NTLM auth |
| 83     | proxy-tunnel server auth |
| 88     | PUT with Digest auth |
| 89-91  | NTLM |
| 94     | CONNECT and failed proxy auth |
| 95     | proxytunnel using POST |
| 99     | refused resume |

## December 2, 2020

- fighting with test 38 - asking for a Range but getting a full response
- made test 33 work
- made test 31 work by doing conditional headers in the test
- made HTTP 1.0 requests work (with the new Hyper API for it)

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
