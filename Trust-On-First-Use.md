_(this is a design idea, a wiki page for brainstorming how this should work/behave)_

# curl tofu, Trust On First Use

The TOFU concept could help people avoid `--insecure` for most common cases and thus make the subsequent transfers to that site done securely. Today we tell the users "don't use -k, get the cacert, put it somewhere and then use `--cacert` in the future when you use that site". This concept could do that job for them.

## For all TLS based transfers

    curl https://example.com

This mode probably needs to be enabled, or alternatively it needs an option to disable it. It works for all transfers that use TLS (HTTPS, FTPS, POP3S, IMAPS, etc).

Idea: enabled by default for interactive user, disabled for non-interactive. "interactive" means a human is available (varies by OS, but excludes batch/cron jobs, daemon processes, etc.). Problem: how do detect "non-interactive" users? For Unix, "Is there a controlling TTY" - one approach is to open /dev/tty; if it fails, there's none. If it succeeds, use the fd for the prompt/response.

Perform as usual with the standard CA cert setup, ask for `CERTINFO` to get returned. (run A)

If run A returns OK, goto Cleanup Mode

If run A returns a non-CA-related error, fail normally

## If run A fails with a CA-cert error

Check the file $CURLTRUST if there's an existing entry for "https://example.com"

If there's an entry with certs/pinning present and it matches the certs from run A, then continue and silently retry the transfer with those certs provided. (run B)

If there isn't a local trust entry present, prompt the user if one should be created. If confirmed, save the public key from run A to $CURLTRUST for this URL. If declined, fail. If confirmed, re-run the transfer with the custom trusts. (run B)

## If run B fails with a CA-cert error

Warn the user about this situation (**suspected Man-In-The-Middle**) and offer her to re-run to update trust. If affirmative, remove the current entry for the URL and do a run C.

## If run C fails with a CA-cert error

Alert the user that this system is impossible to trust and fail.

## Cleanup Mode

If there's an existing entry in $CURLTRUST for this URL, remove that entry now since the "proper" ca cert works for this site.

## $CURLTRUST

Could be called `$HOME/.curl-trust` by default?

Idea: use a ca-path style directory rather than a flat file.  The file name can be something like www.example.com_443.  That way the file system handles editing (adding/deleting certs doesn't require rewriting a file, locks, etc).]

Discuss: save the URLs hashed to avoid privacy leaks if someone inspects someone else's file? With keypinning, there's no host name store or derived anywhere.

# What to store for a site

Storing the certificate for tofu is not very useful. For example, when one has 1-month validity cert which is renewed each month but the same private key is kept. 

The way to PIN such certificates is either by storing the public key of the certificate, or a hash of the public key (just like HPKP does).

# Requirements

This requires that libcurl in use was built with a TLS backend that supports
1. [CURLOPT_CERTINFO](https://curl.haxx.se/libcurl/c/CURLOPT_CERTINFO.html)
2. key pinning support

To ponder about is what curl should do when a libcurl is used without these super powers.

[TL: Presumably an option flag on connect (or per-thread global) for "PROMPT_ON_TLS_ERROR"; backward compatibility argues for off by default - who knows what context a library is used in.]

# Other notes

The discussion around this idea is kept in [Issue1822](https://github.com/curl/curl/issues/1822)