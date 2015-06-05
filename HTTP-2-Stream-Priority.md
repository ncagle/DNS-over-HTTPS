*"A client can assign a priority for a new stream by including prioritization information in the HEADERS frame that opens the stream. At any other time, the PRIORITY frame can be used to change the priority of a stream."* [spec](https://httpwg.github.io/specs/rfc7540.html#StreamPriority)

curl_easy_setopt(handle, CURLOPT_STREAM_PRIORITY, long value);

'value' should be a number between 1 - 256. Passing a value outside of this range has undefined behavior.

-----

*"Each stream can be given an explicit dependency on another stream. Including a dependency expresses a preference to allocate resources to the identified stream rather than to the dependent stream."* [spec](https://httpwg.github.io/specs/rfc7540.html#pri-depend)

curl_easy_setopt(handle, CURLOPT_STREAM_DEPENDS_ON, CURL *handle);

A technicality with dependencies is that a stream can specify which other stream it depends on, but that stream is specified with a stream id over the protocol. We don't know the stream id of a stream until that stream is created.

Run-time and pre-transfer
-------------------------

Both stream priorities and stream dependencies are allowed to be changed at any time during a transfer (strictly speaking there exist some protocol restrains on exactly when such http2 packets can be sent but we can ignore that in higher levels).

To accommodate for this, we need to make sure that these options work for both use-cases - and we need to explicitly document that they can be used while the transfers are in progress since most curl_easy_setopt() options are documented to only have an effect when set before or between transfers.