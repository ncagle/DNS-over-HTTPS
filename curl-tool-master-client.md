*(this is a design idea, a wiki page for brainstorming how this could work/behave)*

## Use case

This style of script exists everywhere:

~~~shell
    #!/bin/sh
    for i in 1 .. 100000; do
      curl https://example.com/yadayada;
    done
~~~

It opens a connection, performs a transfer, then closes the connection again. Very many times. One way to offer an improvement for this would be to have a master/client concept. The client then uses the master to perform the transfers, and as the master process stays alive in the background, the connection cache is properly reused and these 100000 transfers are all done over the same persistent connection:

~~~shell
    #!/bin/sh
    curl --master-start
    for i in 1 .. 100000; do
      curl https://example.com/yadayada;
    done
~~~

## Challenges

Cookies - make sure they're "scoped" and shared identically when using the master as they would normally be.

## Controls

Master should have an inactivity timeout?

    curl --master-min 7                # start if needed, 7 min timeout
    curl --master-min 10 <transfer>    # start if needed, 10 min timeout
    curl --master-sec 300 <transfer>   # like above, better for testing!      

Explicit stop command?

    curl --master-stop             # stops a running master
    curl --master-stop <transfer>  # stops master after transfer completes

Can master be made to stop when the shell that launched it exits?

## Discovery

How does a client discover that there's a master present to be used? The presence of a named pipe? And environment variable? An explicit command line option?

curlrc can be used to transparently cause the master to be used.

## Prerequisites

This feature will be better if the master process can handle [parallel transfers](curl-tool-parallel-transfers) so that there can be more than one client process simultaneously using a single master process.