# Introduction

The curl project received the suggestion to package the official curl binary we produce for Windows in a signed installer. In the long term this package could be used by Microsoft to ship our official curl binary instead of a custom build which lacks features and stays behind in terms of changes and fixes.

The use of MSXI as packaging/installer format was suggested, because this can be considered the future of Windows application packaging due to the possibility of distribution via the Microsoft Store and installation by normal users without administrative privileges.

## Requirements

* Code Signing certificate from a trusted public CA
* CI environment to sign libcurl.dll, curl.exe and the installer/package
* Windows CI environment to package the signed binaries in an MSIX installer
  (MSIX SDK seems not to be cross-platform / not available as binary on Linux)

## Potential next steps

1. Figure out how the MSIX package should look like in terms of metadata and content
2. Create a CI pipeline using GitHub Actions (or some other Windows CI environment) to build an MSIX package
3. Trigger the CI pipeline from the existing curl-for-win repository or the curl website once a new release is published
4. Once everything is working, get a trusted code signing certificate (testing can be done with a self-signed one)
5. _Optional:_ talk to Microsoft about shipping via the Microsoft Store (and superseeding their curl installation)

## Refs

https://github.com/curl/curl/issues/5424