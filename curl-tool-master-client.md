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

