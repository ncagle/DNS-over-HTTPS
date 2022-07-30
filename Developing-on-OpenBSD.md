### Introduction

Because *curl* is an **autotools project**, which itself is deeply integrated into the *GNU operating system*, using it may not be that obvious on a different Unix-like system.
This page aims to collect notes and hints to keep in mind, when using OpenBSD as a development platform for curl.

It is primarily the work of [Emil Engler](https://github.com/emilengler), who is, according to himself, a very stubborn person in the usage of his tools, although edits are much appreciated as this is an editable wiki :-)

### Installing autotools

Before you can develop curl, you'll have to install the tools required for autotools.
```sh
pkg_add autotools # Pick 2.69
pkg_add automake # Pick 1.16
pkg_add libtool
```

After this, you need to set a few environment variables specifying versions.
Append these lines to your `~/.profile` file.
```sh
export AUTOCONF_VERSION=2.69
export AUTOMAKE_VERSION=1.16
```

### Building curl with `--enable-debug`

When building curl with `--enable-debug`, be sure to use the **OpenBSD version of libtool** (found at `/usr/bin/libtool`) instead of the GNU version, which you must install from ports for whatever reason, as it is **broken**.
```
autoreconf -fi
./configure --enable-debug
make LIBTOOL=/usr/bin/libtool -j4
```