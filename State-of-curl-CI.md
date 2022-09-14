The current CI setup for curl is documented in [CI.md](https://github.com/curl/curl/blob/master/tests/CI.md). This wiki page is used to document the current issues regarding random flakiness of some CI builds and serve as a discussion basis for future improvements.

Known issues affecting CI stability:

* Random unavailability of package repositories for Linux (Ubuntu APT), macOS (Homebrew) and FreeBSD
* FTP (and maybe other pingpong-protocols or those tested with sockfilt) randomly loose data on Windows CI, see [#9380](https://github.com/curl/curl/issues/9380)
* At the end (sometimes in the middle of them) of the Windows CI builds we randomly get exit code 143, see [#9469](https://github.com/curl/curl/pull/9469) and e.g. [this run](https://github.com/curl/curl/runs/8285644244)
* Some builds + test rounds take a long time and occasionally hit the maximum allowed time in some runners
* Several builds use dependencies from git and infrequently, those builds are broken or inaccessible

Already planned work related to CI:

* Migration from Zuul to other CI services
* Merging and de-duplication of all Linux workflows on GitHub Actions by @mback2k, see e.g. [#9501](https://github.com/curl/curl/pull/9501)
* Introduce new (eventually better) ways to build and test for Windows by @mback2k, e.g. using WSL for test servers on Windows or Wine for curl on Linux

Visibility issues:

* Appveyor and Zuul both appear as a single CI job on GitHub, while still having many sub-jobs. A single :x: in the list, can then mean one to 25 failures. Flaky, or not flaky.

# Proposals

## Containerised builds

Containerising builds mitigates the "random unavailability of package repositories" problem, but would introduce an "unavailability of container repository" problem instead. However, we have a lot more control over which container repository can be used, and it would also allow for developers to get started faster.

## Disabling all flaky tests to get to constantly green pipelines

@cmeister2 proposes disabling all flaky test suites so that we can be strict about "only green pipelines get merged" - this reduces the burden on both the developer and the reviewer to be able to say that a set of changes is "good" or not.

@mback2k does not think this is feasible as this would remove too many "useful" CI builds at this point. "useful" meaning here that without those we are probably not able to discover relevant issues on e.g. Windows before a release.

## Having a CI "team" that reviews CI-tagged changes

@cmeister2 proposes that there's a specific subteam for reviewing any changes that modify CI or responding to CI-tagged issues.

## Creating a GitHub Actions that splits AppVeyor CI status

@mback2k proposes to have a GitHub Actions that adds status entries to a commit for each AppVeyor job to solve the visibility issue mentioned above.