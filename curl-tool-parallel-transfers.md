*(this is a design idea, a wiki page for brainstorming how this could work/behave)*

    curl --parallel https://example.org/index.html -O https://example.com

This would start both transfers at the same time and transfer them in parallel. It would of course also work with uploads and would allow "any" amount of transfers at the same time.

(**--parallel** is not written in stone as name for this.)

## Challenges

How would the progress meter work?

## Things to think of

- Default needs to remain "serial transfers" for backwards compatibility
- The internals need to change to use the multi API instead of easy
- There will be users who wish to cap the number of simultaneous transfers somehow (`--parallel-max NUM`).
