### Motivation and Scope

With more parallel usage of curl and libcurl, it can become difficult to reproduce reported issues, just
because the exact order in which things happen and seem to run into trouble is not clear. Neither to
the reporter nor to the curl team.

The level of output, available via the `CURLOPT_DEBUGFUNCTION` to the application, is designed to be
informative to the user. But it does not have the detail level that might be necessary to analyze a problem. These details are available in a `debug` build of libcurl, as we develop the features and need those. But a debug build is not intended for production use.

It would therefore be helpful to have a logging facility with some flexibility added to libcurl that is also available in non-debug builds. How to do that and what features to offer?

### Features

The set of features for a logging facility:

* easy way for an app to produce a file
* easy way for an app to add curls log stream to its own
* globally adjustable, once, setting of log "levels" and "topics"
* "topics" are functional parts of libcurl that are of particular interest for analysis. Examples would be "ssl", "http", "resolve", "connection-cache", etc.
* "levels", a predefined set of verbosity. "ERROR", "INFO", "DEBUG" and "TRACE" are a good set. "WARNING" has not really shown to be productive in other systems. INFO implies ERROR, DEBUG implies INFO and ERROR.

Levels can be set for all topics or a specific one. E.g. the general log level is set to INFO, but "http" is on "TRACE".

### Implementation

The implementation needs to be lightweight when logging is not enabled. One key is that logging should only be configured right after `curl_global_init`. This avoids any synchronization issues and the logging state for a topic can be checked on the same memory location very cheaply.

The current implementation of the `LOG_CF` macro shows how to avoid most of the costs:

```
#define LOG_CF(data, cf, ...) \
  do { if(Curl_log_cf_is_debug(cf)) \
         Curl_log_cf_debug(data, cf, __VA_ARGS__); } while(0)
```

which means no calls or parameter evaluations are done unless the logging is active. It requires variable args support in macros, though. Connection filter logging can be enabled for individual filter types. Similar to the "topics" discussed above.


### API

Since logging is global, no easy handle is involved. But maybe we want to follow the same patterns, like in:

```
curl_log_setopt(CURLLOG_OPT_LEVEL, "info http:debug ssl:trace");

/* one of these */
curl_log_setopt(CURLLOG_OPT_FILE, "libcurl.log");
curl_log_setopt(CURLLOG_OPT_FD, fd);
curl_log_setopt(CURLLOG_OPT_WRITE, app_callback);

```

The `app_callback` function would get passed the `level`, `topic`, the log message, an optional `CURL *` and `CURLM *`.

### Security

In a non-debug builds, there should be no default logging anywhere unless the application configures it. The log messages my contain sensitive information. No environment variable should therefore control its behaviour. It is up to the application on how to handle it.

`curl` itself might want to add either new options to its command line or tie the logging into its `-v` and `--trace` implementation.

### Debug Builds

In debug builds, we should defined environment variables to easily change log levels when needed.







