    curl --parallel https://example.org/index.html -O https://example.com

This would start both transfers at the same time and transfer them in parallel. It would of course also work with uploads and would allow "any" amount of transfers at the same time.

## Command line option

**--parallel** is not written in stone as name for this.

**-Z** might be used as a short option.

## Challenges

How would the progress meter work?

## Things to think of

- Default needs to remain "serial" for backwards compatibility
- Cap the number of simultaneous transfers somehow (`--parallel-max NUM`)
- How much parallelism should we allow by default?

## Development branch

[bagder/parallel-transfers](https://github.com/curl/curl/tree/bagder/parallel-transfers)

## Mailing list post

[Describing the goal and initial work](https://curl.haxx.se/mail/archive-2019-04/0007.html).
