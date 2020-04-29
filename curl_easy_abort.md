# Abortable `curl_easy_perform()`

1. Introduce new option to `curl_share_setopt()`: `CURL_LOCK_ABORT`
2. Participating transfers must then use a shared object with that bit set
3. Such share objects *should* have the mutex callback set.

## `curl_easy_abort()`

`CURLcode curl_easy_abort(CURL *easy);`

Can be called from the same or another thread. This aborts the specific
transfer *iff* that transfer was setup to allow being externally aborted like
described above. A transfer that is aborted is terminated, not simply paused.

Trying to abort a non-participating transfer will only result in a
`CURLE_ABORT_DENIED` (new) return code.

A transfer that is successfully stopped by this function will return the
`CURLE_ABORTED` (new) return code.

Users of this function must take precautions to make sure that the handle
itself is still valid when used in this function.
