_(this is a design idea, a wiki page for brainstorming how this should work/behave)_

# curl tofu, Trust On First Use

The TOFU concept could help people avoid `--insecure` for most common cases and thus make the subsequent transfers to that site done securely. Today we tell the users "don't use -k, get the cacert, put it somewhere and then use `--cacert` in the future when you use that site". This concept could do that job for them.

## For all TLS based transfers

    curl https://example.com

This mode probably needs to be enabled, or alternatively it needs an option to disable it. It works for all transfers that use TLS (HTTPS, FTPS, POP3S, IMAPS, etc).

Idea: enabled by default for interactive user, disabled for non-interactive. "interactive" means a human is available (varies by OS, but excludes batch/cron jobs, daemon processes, etc.). Problem: how do detect "non-interactive" users?

[TL:  For Unix, "Is there a controlling TTY" - one approach is to open /dev/tty; if it fails, there's none. If it succeeds, use the fd for the prompt/response]

Perform as usual with the standard CA cert setup, ask for `CERTINFO` to get returned. (run A)

If run A returns OK, goto Cleanup Mode

If run A returns a non-CA-related error, fail normally

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

Idea: use a ca-path style directory rather than a flat file.  The file name can be something like www.example.com_443.  That way the file system handles editing (adding/deleting certs doesn't require rewriting a file, locks, etc).]

Discuss: save the URLs hashed to avoid privacy leaks if someone inspects someone else's file?

[TL: Not worth the complexity.  Plus, would prevent easy auditing to see what's in the trust store.  SSH doesn't; netrc doesn't.  But do enforce permissions on the directory/file.  Must NOT be world-writable (would allow me to add trust for an imposter site to your trust store.)  Group write is questionable.  Does need to be easy for user to determine what's locally trusted.]

[DS: I mention hashing exactly because SSH does it these days. They started out and used "plain" names for many years. The command could show the hashed names to let users know which one it works with.]

[TL: It needs to be possible for me to list the local trust store - e.g. tell me all the trust overrides in my store.  A security auditor (or conscientious user) would want to do this.  Hashing doesn't hide the sites visited, because the cert is saved, and it contains the subject.  At worst, it has a list of SANs; typically only one or two.  So you're not providing any privacy.  A hash can make access faster.  But if you use the filesystem, it will worry about that.  For privacy, you have to protect the file(s).   So I don't see the benefit of a hash.]

# Requirements

This requires that libcurl in use was built with a TLS backend that supports
1. [CURLOPT_CERTINFO](https://curl.haxx.se/libcurl/c/CURLOPT_CERTINFO.html)
2. Custom CA cert, preferably via callback.

To ponder about is what curl should do when a libcurl is used without these super powers.

[TL: Presumably an option flag on connect (or per-thread global) for "PROMPT_ON_TLS_ERROR"; backward compatibility argues for off by default - who knows what context a library is used in.]

[TL: Random thought - you may not each "run" to make a connection to the server.  It may be possible to use TLS backend hooks to modify the verification status.  I believe OpenSSL, at least, has hooks that allow you to intercept the verification status for each certificate in the chain, and modify it.]