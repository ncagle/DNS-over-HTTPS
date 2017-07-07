# Background

current libcurl only picks one out of the authentication methods as returned in the HTTP 401 or 407 responses. It knows how to deal with different methods and will select the one it considers "most secure" out of the one it has been configured to use.

But HTTP servers can send back several different realms using the same method, which libcurl ignores and it will only pick the first occurrence.

# Realm aware

## Before-hand

Let the application tell libcurl upfront which realm(s) that are interesting, and have libcurl automatically pick the first that matches and ignore the rest.

## On demand

Have libcurl tell the application about which realms that show up (with a callback) and have the application pick one to use right there and then.

# The API

... fill in specifics ...