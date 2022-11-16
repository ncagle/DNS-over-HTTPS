# ssl_config handling

There is `struct ssl_primary_config` that holds the configuration *input* parameters for setting up a connection. Since curl manages SSL for direct and proxy use, a `Curl_easy *data` handle holds two instances: `ssl.primary` and `proxy_ssl.primary` (the `ssl` and `proxy_ssl` members are type `struct ssl_config_data` and also keep other stuff like callbacks, verification status, etc).

## Current Status

When creating a new connection `struct connectdata *conn`, `ssl.primary` and `proxy_ssl.primary` are cloned into `conn->ssl_config` and `conn->proxy_ssl_config`. Then the new `conn` is checking the connection cache, if an existing connection with the same properties can be found. If so, `conn` is freed and the existing connection is used.

`SSL` connection filters look into `conn->ssl_config` or `conn->proxy_ssl_config`, depending on their type, to set everything up and do the handshake. Curiously, the vtls backends differ in use of these. Some use `data->ssl.primary` and `data->proxy_ssl.primary` for config data that has been cloned into the connection (**bagder**: a leftover of earlier times?).

Connections with SSL need these cloned config settings, because when reusing connection, the original `data` handle might no longer exist. For reuse, the connection needs to be "standalone".

Some properties seem to be in the wrong place right now, mainly `certverifyresult` that is living in `data` and being set by `conn`. This means this property is not kept at the connection and retrieval of this will not work when reusing a connection for a new `data` instance (it seems from my read of the code).

## Alternate Approach

Curl could move `conn->ssl_config` or `conn->proxy_ssl_config` into the SSL filter instances. It would work like this:

1. adding an SSL filter is given `data`. The filter makes a clone of the used `ssl_primary_config` when it starts connecting, preserving the effective values.
1. the SSL filters frees it on its destruction
1. when looking into the connection cache, `(data, new_conn)` is used for matching an `existing` connection. New functions to query SSL data present at a connection are added to match `data`'s ssl configuration:
  - `Curl_ssl_cf_get_config(data, conn, sockindex) -> *ssl_primary_config or NULL`
  - `Curl_ssl_cf_get_proxy_config(data, conn, sockindex) -> *ssl_primary_config or NULL`

The advantage of this is that these records are only cloned when needed. The cost of matching is a tiny bit higher since existing filters need to be inspected. The SSL config data can be kept more "local" to the filters.

## Open Issues / Observations

* I believe `certverifyresult` should become part of the connection, not `data`.
* vtls backends should no longer use `data->ssl.primary` during handshake, the copies should be there.
* `setopt.c` sets some parameters on the `conn` copy (if present in `data->conn`). I am not sure this has any effect, unless the underlying connection is closed.

# Daniel's feedback on the three issues

## certverifyresult

This is only accessible via the `curl_easy_getinfo()` API with a `CURL *`
handle as argument, that is `data` internally. The values must thus be stored
associated with the handle. Also because the connection may have been closed
and gone by the time `curl_easy_getinfo()` is called.

If you want to remove them from the struct where they are now, as they are
rather different in nature, perhaps a more suitable home for them would be
`struct PureInfo` where other values is stored for the purpose of being
available for `curl_easy_getinfo()` calls.

## not use `data->ssl.primary` during handshake

Seems fair, the copies are made for the connection to have its own set.

## setopt.c setting variables in 'conn'

Looking at that code now, it seems like we shouldn't have to set the variables
in existing connections as they are already created and the values should not
be considered anymore.

But this said, the commit that brought this code (5505df7d24) was a reaction
to issue #1941 which was fixed by this so there is/was a use case. I believe
the user is then setting this value in a callback for the currently live
connection.
