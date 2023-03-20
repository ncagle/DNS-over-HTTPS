In PR #10780 we have support for HTTP/2 proxy tunneling, e.g. sending the `CONNECT` over a H2 connection.
What we do **not** have is sharing of such a connection for several transfers.

## why not?

Several reasons:

* In curl's connection reuse, one part is to check hostname/port pairs. What the transfer wants and what an existing connection offers. For non-tunnel proxies, different origin hostnames are fine. For tunnel proxied connection, they are not. Logic would need to change here. Which is possible.
* The TLS context for a transfer, the client-to-origin encryption, sits in a SSL connection filter. And, as the name says, that is part of the connection. For a 2nd transfer through the h2 tunnel, there would need to be a 2nd TLS context and that cannot also be part of the connection filters. This is complicated.

```
url1 --> TLS1 --> 
                 ⚡️--> h2 proxy --> TCP...
url2 --> TLS2 --> 
```

Connection filters only point "downwards", so the filters for TLS1 and TLS2 could point to the same tunnel filter. But what is the endpoint the transfers then write to?

One way to address that is to have some filters be part of the easy handle and always read/write through that for a particular handle. But that would not allow reuse of TLS1 for other things. Not good.

Another approach would be to allow connections to be stacked onto other, more general connections. So, when establishing a new connection, it would look for existing ones that it could use. Find the tunnel one and go through that. Needs then some ref counting, so connection are not closed while still in use by other connections.

