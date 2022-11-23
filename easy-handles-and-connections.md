# Easy Handles and Connections

Lifetime and ownership handling are hard. There is an issue in regard to modelling for `Curl_easy *data` and `struct connectdata *conn` right now.

## Situation

From the API user point of view, everything happens via a `data` and that is where their callbacks are registered and need to be invoked. Breaking that would mean breaking the API.

Otoh, a `conn` instance can have zero, one or more `data` tied to it. The `zero` case happens when `conn` is held by a connection cache. And the cache belongs to a `struct Curl_multi *multi`.

A `multi` is either created by an API user, or comes implicitly into existence during handling of a stand-alone `data`. Many `data` can share a users `multi`, but a `data` can also hold its own `multi` for a while (the difference seems to be remembered in assigning either `data->multi` or `data->multi_easy`).

This makes lifetimes and ownership a bit tricky.

### Connection Filters

Since `conn` can live without a `data`, so do its connection filters (`cf`). Ownership and lifetime of a `cf` is simple. It belongs to one `conn` only, never leaving it. And all `cf` for a `conn` are destroyed when the `conn` is freed.

This allows a `cf->conn` to keep a reference to its connection, assigned when adding it. That should never change. A `cf` should never move to another connection.

### `data` and `cf`

The connection filters have no member `cf->data`, since there can be many `data` during a `cf` lifetime (same for `conn`). But `data` is still in most `cf` function parameters, because API and callbacks.

### `data` and vtls filters

The `vtls` connection filter now stumbles upon the problem that it registers callbacks at the `SSL*` instances with its `cf` as userdata. When the callback is invoked by the `SSL*`, the `data` instance that was causing all this, is unavailable.

The current workaround in PR #9962 is to save the `data` in a special place before invoking `SSL` operations, so that callbacks may find it there. This is brittle in that missed assignments may result NULL or wrong `data` instances to be used. The `data` saved may already have been deleted. Yikes!


