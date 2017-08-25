_(this is a design idea, a wiki page for brainstorming how this should work/behave)_

# curl tofu, Trust On First Use

    curl https://example.com

(this mode probably needs to be enabled, or alternatively it needs an option to disable it)

[TL: Suggest enabled by default for interactive user, disabled for non-interactive.  This is the sort of thing one wants in a .ini file, not on every command.  "interactive" means a human is available (varies by OS, but excludes batch/cron jobs, daemon processes, etc.)]

Perform as usual with the standard CA cert setup, ask for `CERTINFO` to get returned. (run A)

If run A doesn't return an error, goto Cleanup Mode (Discuss: what to do on non-CA errors)

[TL: You mean expired, revoked, etc?  Default: If locally trusted, prompt w/reason.  Otherwise fail.  I'd like to redefine --insecure to mean prompt in this case - but that would break compatibility.  So I guess a new option, e.g. --trust-override to prompt for adding to local trust store]

## If run A fails with a CA-cert error

Check the file $CURLTRUST if there's an existing entry for "https://example.com"

[TL: Note this applies to all TLS protocols - e.g. curl has ftp-ssl ...]

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

[TL: Suggest you use a ca-path style directory rather than a flat file.  The file name can be something like www.example.com_443.  That way the file system handles editing (adding/deleting certs doesn't require rewriting a file, locks, etc).]

Discuss: save the URLs hashed to avoid privacy leaks if someone inspects someone else's file?

[TL: Not worth the complexity.  Plus, would prevent easy auditing to see what's in the trust store.  SSH doesn't; netrc doesn't.  But do enforce permissions on the directory/file.  Must NOT be world-writable (would allow me to add trust for an imposter site to your trust store.)  Group write is questionable.  Does need to be easy for user to determine what's locally trusted.]

# Requirements

This requires that libcurl in use was built with a TLS backend that supports
1. [CURLOPT_CERTINFO](https://curl.haxx.se/libcurl/c/CURLOPT_CERTINFO.html)
2. Custom CA cert, preferably via callback.

To ponder about is what curl should do when a libcurl is used without these super powers.

[TL: Presumably an option flag on connect (or per-thread global) for "PROMPT_ON_TLS_ERROR"; backward compatibility argues for off by default - who knows what context a library is used in.]
