# Shared connection cache multi-threaded problems

(this wiki page is meant as a brain storming page and documentation area for work on and related to this specific issue and will probably be removed again subsequently once we have this nailed.)

Issue: https://github.com/curl/curl/issues/4915

We don't properly protect data from being acceessed from multiple threads when
the connection cache is shared in a multi-threaded application doing transfers
in more than one thread.

## Connection caching

When libcurl creates a new connection for use in an upcoming transfer, it will
add that to the connection cache. Used connections are present in the cache to
allow for subsequent transfers to be able to find them and potentially
multiplex on the same connection (when using HTTP/2 or HTTP/3).

When checking the cache for an available connection at the start of a new
transfer, the cache will be locked with a mutex so that the cache accesses are
thread-safe. But since the cache also holds and points to *active*
connections, traversing the cache will make it access struct data of
connections that are currently in use in another thread! (and vice versa, a
thread that updates a field in the connectdata struct might change a struct
field that a separate thread could check when looking for one in the cache).

Some of these problems are visualized excellently by the recipe provided in
issue #4915 with a thread sanitizer (tsan) build.

## Solution?

When accessing data that is potentially used by more than one thread we need
to mutex-lock.

What data? We should move all potentially-accessed-concurrently struct fields
into a separate sub-struct that makes it more obvious in the code when a lock
is necessary.

These are the ones access from within ConnectionExists():

    ->abstract_unix_socket
    ->bits
    ->connection_id
    ->conn_to_host
    ->conn_to_port
    ->data
    ->handler
    ->host
    ->http_ntlm_state
    ->http_proxy
    ->ip_addr_str
    ->localdev
    ->localport
    ->localportrange
    ->passwd
    ->proto
    ->proxy_ntlm_state
    ->proxy_ssl
    ->proxy_ssl_config
    ->remote_port
    ->sock
    ->socks_proxy
    ->ssl
    ->ssl_config
    ->tls_upgraded
    ->unix_domain_socket
    ->user
