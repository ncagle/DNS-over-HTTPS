# Project Hyper-as-a-HTTP-backend-in-curl

Also known as curl+hyper. Or CH.

Pull-requests: [curl](https://github.com/curl/curl/pull/6110) and [Hyper](https://github.com/hyperium/hyper/pull/2278)

Explanatory blog post: [rust in curl with hyper](https://daniel.haxx.se/blog/2020/10/09/rust-in-curl-with-hyper/)

Persons involved: Daniel Stenberg (on curl) and Sean McArthur (on Hyper)

# Daniel's Work Log

## November 3, 2020

- "torture tests" on test case 1 brought up an interesting API issue
- Use the new API to enable H2 and now `curl https://curl.haxx.se` works as expected
- The travis CI job for CH ran green!

## November 2, 2020

- I'm adding a CI job to travis to build with Hyper and run test case 1 (with valgrind)
- The debug callback is now called with all the outgoing request headers, matching default libcurl behavior
- Custom provided headers are supported in the request 
- CH works fine to fetch `https://curl.haxx.se/` too, as long as I force it to speak HTTP/1.1 only - curl will default to HTTP/2 but so far I can't tell Hyper that...

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

Possible solution is to have a "hyper mode" for the HTTP test server and always deliver HTTP headers with CRLF then.

## October 21, 2020

I could issue a HTTP request to my local HTTP server using CH and get the response back correctly. Using the same HTTP 