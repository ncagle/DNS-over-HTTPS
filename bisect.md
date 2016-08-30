If something is broken in curl but was working in an older version you can use a technique called bisecting to identify what changes caused the problem.

The first step is to clone the curl repository, https://github.com/curl/curl.git . In the repo the curl releases use tag names in the format `curl-X_XX_X`, eg 7.44.0 is curl-7_44_0. Each time you build source from the repository using a different commit you should run buildconf first (./buildconf && ./configure <opts> && make).

These next two steps are not strictly required but if you're not entirely sure what you're doing you should do them to keep your sanity:
Checkout from the repo a version you know is good, build it and confirm it's good.
Checkout from the repo a version you know is bad, build it and confirm it's bad.

Now use `git bisect` commands to do the bisect. For example, if curl 7.49.1 has some issue that 7.44 does not have:

~~~
git bisect start
git bisect bad curl-7_49_1
git bisect good curl-7_44_0
~~~

Commits are checked out automatically when you bisect. Build but no install (./buildconf && ./configure <opts> && make). Confirm libcurl and curl versions match (src/curl -V and compare curl and libcurl versions). Attempt to reproduce problem using src/curl. (If problem is not 100% reproducible run multiple times to get an accurate result.) Mark each commit good (no problem), bad (problem) or skip (failed to build) using the respective commands shown below:

~~~
git bisect good
git bisect bad
git bisect skip
~~~

After you mark a commit another commit will be checked out, and repeat the above step. Assume each step about 1-2min a build, plus however long it takes you to reproduce your issue. When done to cleanup and reset to the commit before bisecting do `git bisect reset`