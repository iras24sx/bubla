# bubla
Randomized stress generator docker image - based on linux stress and iperf.

It buble and randomly generate activity, what can be used for demos or testing. No root account is used for runnig, so it is compatible with the OpenShift.

Runnig without any parameter it will start with the defaults:

- max stress time is 5 seconds
- max sleeping (no stress) is 1200 seconds
- max CPU 3
- max IO 128
- max VM (mem) 128

Switches:

-l X set max time of load/stress to X seconds 
-s X set max time of sleep/no stress to X seconds 

-c X set max CPU to X
-i X set max IO to X 
-m X set max VM(mem) to X 

-h X set hostname of iperf server to X 
-p X set port of iperf server to X 

For exact behavior please check the shell script source and mainly documentation of https://people.seas.harvard.edu/~apw/stress/ and https://iperf.fr/.
