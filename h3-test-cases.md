# H3 Test Cases

Thinking about adding H3 test cases to curl:

* using nghttpx (if properly built) in similar fashion for the H2 tests
* adding `http/3` as a server setup for `runtests.pl`
* having it take a certificate arg like the `https` server

Dependencies:

* adding a `nghttpx` and `nghttpx-h3` features to make such tests conditional on what is installed on the system
* adding a `--with-test-nghttpx=<path>`to `configure` so that a specific one cane be chosen