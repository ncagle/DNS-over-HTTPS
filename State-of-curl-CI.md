The current CI setup for curl is documented in [CI.md](https://github.com/curl/curl/blob/master/tests/CI.md). This wiki page is used to document the current issues regarding random flakiness of some CI builds and serve as a discussion basis for future improvements.

Known issues affecting CI stability:

* Random unavailability of package repositories for Linux (Ubuntu APT), macOS (Homebrew) and FreeBSD
* FTP (and maybe other pingpong-protocols or those tested with sockfilt) randomly loose data on Windows CI, see [#9380](https://github.com/curl/curl/issues/9380)
* At the end (sometimes in the middle of them) of the Windows CI builds we randomly get exit code 143, see [#9469](https://github.com/curl/curl/pull/9469) and e.g. [this run](https://github.com/curl/curl/runs/8285644244)