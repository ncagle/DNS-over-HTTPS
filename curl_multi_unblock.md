# Unblock `curl_multi_wait()`

Both `curl_multi_wait()` and `curl_multi_poll()` can be called and can be sit "hanging" for a while, waiting for activity or a timeout.

Here's an idea for a function that can be called from another thread to instantly unblock that call and make it return back to the application.

## `curl_multi_unblock()`

`CURLMcode curl_multi_unblock(CURLM *multi);`

Can be called from the same or another thread. This "unblocks" calls to `curl_multi_wait()` or `curl_multi_poll()` that would otherwise wait for the timeout or for activity to happen on one of the sockets. Unblocking such a
call means the function will return early but with no indicating that it was triggered by this function. (To ponder: can/should we provide info that it was?)

## Implementation

This can be done by using the recently added `Curl_socketpair()` function and making sure we setup such a pipe and always wait for activty on that in addition to the other file descriptors.

## A mutex lock

We need mutex locking for the pipe in the multi handle used for this and we currently have no such thing.

libcurl itself has no way to do safe multi-threaded locking so we need to leave that to the application to do it for us, similar to how it is done for the share interface.

The mutex setup is done with these four new options to `curl_multi_setopt()`: 

1. `CURLMOPT_LOCKFUNCTION` - mutex lock the specific multi handle
2. `CURLMOPT_LOCKDATA` - custom pointer to pass to the lock callback
3. `CURLMOPT_UNLOCKFUNCTION` - mutex unlock the handle again
4. `CURLMOPT_UNLOCKDATA` - custom pointer to pass to the unlock callback
