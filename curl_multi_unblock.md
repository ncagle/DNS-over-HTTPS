# Unblock `curl_multi_wait()`

Both `curl_multi_wait()` and `curl_multi_poll()` can be called and can be sit "hanging" for a while, waiting for activity or a timeout.

Here's an idea for a function that can be called from another thread to instantly unblock that call and make it return back to the application.

## `curl_multi_unblock()`

`CURLMcode curl_multi_unblock(CURLM *multi);`

Can be called from the same or another thread. This "unblocks" calls to `curl_multi_wait()` or `curl_multi_poll()` that would otherwise wait for the timeout or for activity to happen on one of the sockets. Unblocking such a
call means the function will return early but with no indicating that it was triggered by this function. (To ponder: can/should we provide info that it was?)

## Implementation

This can be done by using the recently added `Curl_socketpair()` function and making sure we setup such a pipe and always wait for activty on that in addition to the other file descriptors.
