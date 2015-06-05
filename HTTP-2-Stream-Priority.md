*"A client can assign a priority for a new stream by including prioritization information in the HEADERS frame that opens the stream. At any other time, the PRIORITY frame can be used to change the priority of a stream."* [spec](https://httpwg.github.io/specs/rfc7540.html#StreamPriority)

CURLOPT_STREAM_PRIORITY, long value

'value' should be a number between 1 - 256. Values outside of this range has undefined behavior.

-----

*"Each stream can be given an explicit dependency on another stream. Including a dependency expresses a preference to allocate resources to the identified stream rather than to the dependent stream."* [spec](https://httpwg.github.io/specs/rfc7540.html#pri-depend)

CURLOPT_STREAM_DEPENDS_ON, CURL *handle

A technicality with dependencies is that a stream can specify which other stream it depends on, but that stream is specified with a stream id over the protocol. We don't know the stream id of a stream until that stream is created.