
- CURLMOPT_PUSHFUNCTION  [callback]
- CURLMOPT_PUSHDATA      [callback pointer]

These are two new options for curl_multi_setopt()

Without the CURLMOPT_PUSHFUNCTION set, pushed streams will be refused.

~~~
   int curl_push_callback(CURL *parent,
                          CURL *easy,
                          size_t num_headers,
                          struct curl_pushheaders *headers,
                          void *userp);
~~~

This callback gets called when a new stream is being pushed by the server.

 - 'easy' is a newly created handle that represents this new transfer.

 - 'parent' is the handle of the stream on which this push arrives. The new
handle has been duphandle()d from the parent, meaning that it has gotten all
its options inherited. It is then up to the application to alter any options
if desired.

 - 'num_headers' is the number of name+value pairs that was received and can be
accessed

 - 'headers' is a handle used to access push headers using the accessor functions described below. This only accesses and provides the PUSH_PROMISE headers, the normal response headers will be provided in the header callback as usual.

 - 'userp' is the pointer set with CURLMOPT_PUSHDATA

If the callback returns CURL_PUSH_OK, the 'easy' handle will be added to the
multi handle, the callback must not do that by itself.

Header Accessors
================

Accessor functions to read PUSH_PROMISE headers from within the push callback (and *only*
within the callback):
~~~
  char *curl_pushheader_bynum(push_headers, size_t num);
~~~
Returns the header index 'num' (or NULL). The returned pointer points
to a string that will be freed when this callback returns. A header string is
both name and value, colon separated in HTTP 1.1-style. Using this function, the application code can iterate
over all headers received in the PUSH_PROMISE.
~~~
  char *curl_pushheader_byname(push_headers, const char *name);
~~~
Returns the *value* for the given header name (or NULL). This is a shortcut so that the application doesn't have to loop through all headers to find the one it is interested in.

Callback return codes
=====================

Return code|Description
--- | --- |
CURL_PUSH_OK|we have accepted the stream and it can now start receiving data, the ownership of the CURL handle has been taken over bythe application.
CURL_PUSH_DENY | the callback denies the stream and no data for this will reach the application, the easy handle will be destroyed by libcurl
* | all other return codes are reserved for future use
