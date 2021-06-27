An attempt to assess and document the expected string encoding for libcurl APIs where strings are used as inputs or return values.

Notes:
- Encodings describe how the string _should_ work, based on content and how/where it is being used. This may differ from reality depending on build configuration.
- Please feel free to add any missing API to the list.
- Entries marked with `?` are yet to be finalized.
- An interesting category is for example the referrer string which is normally a URL, where UTF-8 support is expect, but the value is effectively a raw, zero-terminate string.

String types:
- **binary** = raw bytes with an explicit length
- **ASCII**  = zero terminated, 7-bit ASCII string<br>usually strings internal to libcurl. Internally, these behave the same as **raw**, but documented/accepted/valid/typical values are 7-bit ASCII.
- **UTF-8**  = zero terminated, UTF-8 encoded string<br>URLs, filenames, human-readable text, etc.
- **raw**    = zero terminated, 8-bit string<br>none of the above, codepage to be determined by context on either the local or remote side

APIs:

verified | encoding | API
:---- | :------- | :---------------------------------
✓ | binary | `CURLFORM_COPYCONTENTS` (ptr + length)
✓ | binary | `CURLFORM_COPYNAME` (ptr + length)
? | UTF-8  | `CURLFORM_FILE`
? |        | `CURLFORM_FILECONTENT`
? | ASCII  | `CURLINFO_CONTENT_TYPE`
✓ | ASCII  | `CURLINFO_EFFECTIVE_METHOD`
✓ | UTF-8  | `CURLINFO_EFFECTIVE_URL` (URL)
? | UTF-8  | `CURLINFO_FTP_ENTRY_PATH`
✓ | ASCII  | `CURLINFO_LOCAL_IP`
✓ | ASCII  | `CURLINFO_PRIMARY_IP`
✓ | UTF-8  | `CURLINFO_REDIRECT_URL` (URL)
? | UTF-8  | `CURLINFO_REFERER`
✓ | raw    | `CURLINFO_RTSP_SESSION_ID`
✓ | ASCII  | `CURLINFO_SCHEME`
✓ | UTF-8  | `CURLOPT_ABSTRACT_UNIX_SOCKET` (local filename)
✓ | ASCII  | `CURLOPT_ACCEPT_ENCODING` / `CURLOPT_ENCODING` (sent to remote, normally ASCII)
✓ | UTF-8  | `CURLOPT_ALTSVC` (local filename)
✓ | ASCII  | `CURLOPT_AWS_SIGV4` (sent to remote, normally ASCII)
✓ | UTF-8  | `CURLOPT_CAINFO` (local filename)
✓ | binary | `CURLOPT_CAINFO_BLOB` (ptr + length)
✓ | UTF-8  | `CURLOPT_CAPATH` (local directory)
✓ | raw    | `CURLOPT_COOKIE` (cookie string sent to remote)
✓ | UTF-8  | `CURLOPT_COOKIEFILE` (local filename)
✓ | UTF-8  | `CURLOPT_COOKIEJAR` (local filename)
✓ | raw    | `CURLOPT_COOKIELIST` (ASCII internal string `ALL/SESS/FLUSH/RELOAD` or raw string sent to remote)
✓ | binary | `CURLOPT_COPYPOSTFIELDS` (ptr + length)
✓ | UTF-8  | `CURLOPT_CRLFILE` (local filename)
✓ | ASCII  | `CURLOPT_CUSTOMREQUEST` (sent to remote, normally ASCII)
✓ | ASCII  | `CURLOPT_DEFAULT_PROTOCOL` (normally ASCII)
✓ | UTF-8  | `CURLOPT_DNS_SERVERS` (URL host:port)
✓ | ASCII  | `CURLOPT_DNS_INTERFACE` (local ASCII)
✓ | UTF-8  | `CURLOPT_DNS_LOCAL_IPV4` (local ASCII)
✓ | UTF-8  | `CURLOPT_DNS_LOCAL_IPV6` (local ASCII)
✓ | UTF-8  | `CURLOPT_DOH_URL` (URL)
✓ | UTF-8  | `CURLOPT_EGDSOCKET` (local filename)
✓ | ASCII  | `CURLOPT_FTPPORT` (URL IP:port)
✓ | raw    | `CURLOPT_FTP_ACCOUNT` (remote credentials)
✓ | raw    | `CURLOPT_FTP_ALTERNATIVE_TO_USER` (remote credentials)
✓ | UTF-8  | `CURLOPT_HSTS` (local filename)
✓ | UTF-8  | `CURLOPT_INTERFACE` (URL address or host)
✓ | UTF-8  | `CURLOPT_ISSUERCERT` (local filename)
✓ | binary | `CURLOPT_ISSUERCERT_BLOB` (ptr + length)
✓ | raw    | `CURLOPT_KEYPASSWD` (local credentials)
✓ | ASCII  | `CURLOPT_KRBLEVEL` / `CURLOPT_KRB4LEVEL` (ASCII)
✓ | raw    | `CURLOPT_LOGIN_OPTIONS` (sent to remote)
✓ | raw    | `CURLOPT_MAIL_AUTH` (sent to remote)
✓ | raw    | `CURLOPT_MAIL_FROM` (sent to remote)
✓ | UTF-8  | `CURLOPT_NETRC_FILE` (local filename)
✓ | UTF-8  | `CURLOPT_NOPROXY` (URL domain/IP list)
✓ | raw    | `CURLOPT_PASSWORD` (remote credentials)
✓ | UTF-8  | `CURLOPT_PINNEDPUBLICKEY` (local filename)
✓ | binary | `CURLOPT_POSTFIELDS` (ptr + length)
✓ | UTF-8  | `CURLOPT_PRE_PROXY` (URL server:port)
✓ | UTF-8  | `CURLOPT_PROXY` (URL server:port)
✓ | raw    | `CURLOPT_PROXYPASSWORD` (remote credentials)
✓ | raw    | `CURLOPT_PROXYUSERNAME` (remote credentials)
✓ | raw    | `CURLOPT_PROXYUSERPWD` (remote credentials)
✓ | UTF-8  | `CURLOPT_PROXY_CAINFO` (local filename)
✓ | binary | `CURLOPT_PROXY_CAINFO_BLOB` (ptr + length)
✓ | UTF-8  | `CURLOPT_PROXY_CAPATH` (local directory)
✓ | UTF-8  | `CURLOPT_PROXY_CRLFILE` (local filename)
✓ | UTF-8  | `CURLOPT_PROXY_ISSUERCERT` (local filename)
✓ | binary | `CURLOPT_PROXY_ISSUERCERT_BLOB` (ptr + length)
✓ | raw    | `CURLOPT_PROXY_KEYPASSWD` (local credentials)
✓ | UTF-8  | `CURLOPT_PROXY_PINNEDPUBLICKEY` (local filename)
✓ | ASCII  | `CURLOPT_PROXY_SERVICE_NAME` (normally ASCII)
✓ | UTF-8  | `CURLOPT_PROXY_SSLCERT` (local filename)
✓ | ASCII  | `CURLOPT_PROXY_SSLCERTTYPE` (local ASCII)
✓ | binary | `CURLOPT_PROXY_SSLCERT_BLOB` (ptr + length)
✓ | UTF-8  | `CURLOPT_PROXY_SSLKEY` (local filename)
✓ | ASCII  | `CURLOPT_PROXY_SSLKEYTYPE` (local ASCII)
✓ | binary | `CURLOPT_PROXY_SSLKEY_BLOB` (ptr + length)
✓ | ASCII  | `CURLOPT_PROXY_SSL_CIPHER_LIST`
✓ | ASCII  | `CURLOPT_PROXY_TLS13_CIPHERS`
✓ | raw    | `CURLOPT_PROXY_TLSAUTH_PASSWORD` (remote credentials)
✓ | ASCII  | `CURLOPT_PROXY_TLSAUTH_TYPE` (internal ASCII)
✓ | raw    | `CURLOPT_PROXY_TLSAUTH_USERNAME` (remote credentials)
✓ | UTF-8  | `CURLOPT_RANDOM_FILE` (local filename)
✓ | ASCII  | `CURLOPT_RANGE` (ASCII, sent to remote)
? | raw    | `CURLOPT_REFERER` (URL or any string)
? | UTF-8  | `CURLOPT_REQUEST_TARGET` (URL)
✓ | raw    | `CURLOPT_RTSP_SESSION_ID` (sent to remote)
✓ | UTF-8  | `CURLOPT_RTSP_STREAM_URI` (URL)
✓ | ASCII  | `CURLOPT_RTSP_TRANSPORT` (sent to remote, normally ASCII)
✓ | raw    | `CURLOPT_SASL_AUTHZID` (remote credentials)
✓ | ASCII  | `CURLOPT_SERVICE_NAME` (normally ASCII)
✓ | ASCII  | `CURLOPT_SOCKS5_GSSAPI_SERVICE` (normally ASCII)
✓ | ASCII  | `CURLOPT_SSH_HOST_PUBLIC_KEY_MD5` (local ASCII)
✓ | UTF-8  | `CURLOPT_SSH_KNOWNHOSTS` (local filename)
✓ | UTF-8  | `CURLOPT_SSH_PRIVATE_KEYFILE` (local filename)
✓ | UTF-8  | `CURLOPT_SSH_PUBLIC_KEYFILE` (local filename)
✓ | UTF-8  | `CURLOPT_SSLCERT` (local filename)
✓ | ASCII  | `CURLOPT_SSLCERTTYPE` (local ASCII)
✓ | binary | `CURLOPT_SSLCERT_BLOB` (ptr + length)
✓ | ASCII  | `CURLOPT_SSLENGINE` (internal)
✓ | UTF-8  | `CURLOPT_SSLKEY` (local filename)
✓ | ASCII  | `CURLOPT_SSLKEYTYPE` (local ASCII)
✓ | binary | `CURLOPT_SSLKEY_BLOB` (ptr + length)
✓ | ASCII  | `CURLOPT_SSL_CIPHER_LIST`
✓ | ASCII  | `CURLOPT_SSL_EC_CURVES` (local ASCII)
✓ | ASCII  | `CURLOPT_TLS13_CIPHERS`
✓ | raw    | `CURLOPT_TLSAUTH_PASSWORD` (remote credentials)
✓ | ASCII  | `CURLOPT_TLSAUTH_TYPE` (internal ASCII)
✓ | raw    | `CURLOPT_TLSAUTH_USERNAME` (remote credentials)
✓ | UTF-8  | `CURLOPT_UNIX_SOCKET_PATH` (local filename)
✓ | UTF-8  | `CURLOPT_URL` (URL)
✓ | raw    | `CURLOPT_USERAGENT` (sent to remote)
✓ | raw    | `CURLOPT_USERNAME` (remote credentials)
✓ | raw    | `CURLOPT_USERPWD` (remote credentials)
✓ | raw    | `CURLOPT_XOAUTH2_BEARER` (sent to remote)
✓ | binary | `curl_mime_data()` (ptr + length)
✓ | ASCII  | `curl_mime_encoder()` (internal ASCII)
✓ | raw    | `curl_mime_filedata()` (sent to remote)
✓ | raw    | `curl_mime_filename()` (sent to remote)
✓ | ASCII  | `curl_mime_name()` (sent to remote, normally ASCII)
✓ | ASCII  | `curl_mime_type()` (sent to remote, normally ASCII)
