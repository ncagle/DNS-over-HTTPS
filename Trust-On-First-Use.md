_(this is a design idea, a wiki page for brainstorming how this should work/behave)_

# curl tofu, Trust On First Use

    curl https://example.com

(this mode probably needs to be enabled, or alternatively it needs an option to disable it)

Perform as usual with the standard CA cert setup, ask for `CERTINFO` to get returned. (run A)

If run A doesn't return an error, goto Cleanup Mode (Discuss: what to do on non-CA errors)

## If run A fails with a CA-cert error

Check the file $CURLTRUST if there's an existing entry for "https://example.com"

If there's an entry with certs/pinning present and it matches the certs from run A, then continue and silently retry the transfer with those certs provided. (run B)

If there isn't a local trust entry present, prompt the user if one should be created. If confirmed, save the certs from run A to $CURLTRUST for this URL. If declined, fail. If confirmed, re-run the transfer with the custom trusts. (run B)

## If run B fails with a CA-cert error

Warn the user about this situation (**suspected Man-In-The-Middle**) and offer her to re-run to update trust. If affirmative, remove the current entry for the URL and do a run C.

## If run C fails with a CA-cert error

Alert the user that this system is impossible to trust and fail.

## Cleanup Mode

If there's an existing entry in $CURLTRUST for this URL, remove that entry now since the "proper" ca cert works for this site.

## $CURLTRUST

Could be called `$HOME/.curl-trust` by default?

# Requirements

This requires that libcurl in use was built with a TLS backend that supports
1. [CURLOPT_CERTINFO](https://curl.haxx.se/libcurl/c/CURLOPT_CERTINFO.html)
2. Custom CA cert, preferably via callback.

To ponder about is what curl should do when a libcurl is used without these super powers.