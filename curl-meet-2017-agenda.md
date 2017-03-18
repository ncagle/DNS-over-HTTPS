## Friday/Saturday/Sunday evening

If you signed up for it, we have [joint dinners](curl-meeting-2017-dinners) all three evenings. Everyone has to pay for themselves though.

## Friday

| Time  | Activity |
|-------|----------|
| 19:30 | (optional) dinner at [Barfüßer](http://www.barfuesser-nuernberg.de)—organized, but paid for individually

## Saturday

| Time  | Activity |
|-------|----------|
| 08:30 | Setting up?
| 09:00 | Registration. Get a name tag. Say hello.
| 09:30 | Introductions
| 09:40 | Keynote: The first 20 years and the next - Daniel Stenberg
| 10:30 | Break
| 10:40 | Lightning talk
| 11:00 | curl test suite - Dan Fandrich
| 12:00 | Lunch (provided)
| 12:45 | Lightning talk — http://wttr.in: creating console oriented web sites — Igor Chubin
| 13:00 | Wrapping curl - Christian Schnitz
| 13:30 | the curl web site - Dan and Daniel
| 14:00 | How Google uses curl - Tony Aiuto
| 15:00 | Break - sign up for unconference topics
| 15:30 | Unconference
| 17:30 | Wrapup and curl quiz!
| 18:30 | (optional) dinner at [Landbierparadies](http://landbierparadies.com)—organized, but paid for individually

## Sunday

| Time | Activity |
|-------|----------|
| 09:00 | curl is the Swiss army knife - Dan Fandrich
| 09:45 | Panel discussion / Q&A with curl committers
| 10:30 | Break
| 10:45 | Lightning talks
| 11:15 | HTTP/2, where we are now and what's coming - Daniel Stenberg
| 12:00 | Lunch (provided)
| 12:45 | Lightning talks
| 13:00 |
| 14:00 |
| 15:00 | Break
| 15:00 | Breakout sessions/unconference
| 16:00 | Final wrap up talk
| 18:00 | (optional) dinner at [Hans im Glück](http://hansimglueck-burgergrill.de)—organized, but paid for individually

Care should be taken to the fact that people will start to drop off Sunday afternoon.

# Suggested talks

| Who | Topic |
|-----|-------|
| Daniel Stenberg | The first 20 years and the next (Keynote)
| Tony Aiuto | How Google uses curl. We have some unique challenges trying to support hundreds of applications on multiple platforms from a single copy of the checked in source.
| Dan Fandrich | A key to the curl project's success in keeping the quality of its releases high despite its rapid rate of new features and improvements is its regression test suite. Over 1000 tests cover a wide selection of protocols and features and help detect problems before they reach the public in a release. This talk will touch on the origins and growth of the test suite and its effectiveness, describe its architecture, features and test file format, and show how easy it is to add a new test to the corpus. It will conclude with a discussion on the main areas lacking test coverage and directions of possible future improvements.
| Daniel Stenberg/Fandrich | The curl project is run in an open manner and that extends to its official web site, https://curl.haxx.se. Learn about the technology behind the web site that serves millions of requests a year, from its hardware and HTTP stack to its unique templating system. Find out more about some of the inconspicuous features on the web site, like the latest download version tracker, the download wizard, the mirror tracker and the Metalink link generator.
| Dan Fandrich | curl is the Swiss Army knife of web tools. Its simple syntax belies its power, which comes through harnessing its literally hundreds of command-line options in a controlled sequence. Discover how to harness that power to automate scripting tasks. Learn how a simple click in a browser can turn into dozens of requests, and how to perform them using curl. Find out the kinds of techniques used in modern web sites that, deliberately or not, put road blocks in the way of a simple scripting task.
| Daniel Stenberg | HTTP/2 - what it is, how it works, how to do it with curl
| - | TLS 1.3 - status and how to use
| Daniel Stenberg | How does curl verify certificates
| Daniel Stenberg | curl security and interaction with the rest of the ecosystem 
| Christian Schmitz | Wrapping CURL. Talking about problems, wishes, pitfalls and successes when wrapping lib curl for other development tools.

# Lightning talks (supposedly slightly shorter)

| Who | Topic |
|-----|-------|
| Daniel Stenberg | "Everything curl" and how to contribute to the book
| Igor Chubin | http://wttr.in: creating console oriented web sites
| Daniel Stenberg | The state of QUIC
| Daniel Stenberg | Two features I'd like to see in the cmdline tool but probably won't implement myself
| Dagobert Michelsen | How to keep standard software up-to-date on a legacy platform
| Isaac Boukris | SPNEGO, Kerberos, GSS-API and Negotiate support and how to make them better
| Kamil Dudka | Life of a distro packager
| Kamil Dudka | Why Red Hat switched to NSS and still uses it
| Aleksandar Lazic | curl for network debugging
| Stefan Eissing | how I use curl in my mod_http2 tests (and where I do not)
| Daniel Stenberg | The URL situation
| Michael Kaufmann | WebSocket support for curl

# Discussion topics

For the panel on Sunday, or other opportunities

 1. How should we improve the experience for Windows developers
 2. Project management. How to make decisions, distribute responsibilities and make everyone feel respected and important. Continue like before, or change something?
 3. Is the time ripe to change `-X` (`CURLOPT_CUSTOMREQUEST`) to only change the initial HTTP request and not the subsequent ones when following redirects? A common source for head aches to users.
 4. People keep reacting to changes/bug fixes a long time after they've been discussed or changed. Can we do anything to make people notice or respond sooner?
 5. Can we integrate with Let's Encrypt (better) ?
 6. Should we have a curl://up in 2018 ? Where?
 7. Alternate build systems? Can we come up with something that works better for Windows?
 8. Discussions/questions. With kids not used to email anymore, should we "bless" stackoverflow for asking curl questions? Should we open a separate repo on github for "discussion" issues?
 9. Redesigning the web site. We have an offer, do people think its needed/desired?

# Presentation Template

There's a LibreOffice Impress [presentation template](curlup-presentation-template.otp)
available if you'd like to use it for your presentations. It uses the Luxi Sans
and Liberation Sans typefaces.
