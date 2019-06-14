# bubla
Randomized stress generator docker image - based on linux stress and iperf.

It buble and randomly generate activity, what can be used for demos or testing. No root account is used for runnig, so it is compatible with the OpenShift.

# Runnig without any parameter it will start with the defaults:

- max stress time is 5 seconds
- max sleeping (no stress) is 1200 seconds
- max CPU 3
- max IO 128
- max VM (mem) 128

Second step of the cycle runs iperf for same time, as was for stress and tries to tranfer something at max spped of 10 Mbit.

This is repeating ad infinitum.

# Configuration can be done by

## Environment variables with self-describing names:
- BUBLA_MAXCPU 
- BUBLA_MAXIO
- BUBLA_MAXMEM
- BUBLA_MAXSTRESSTIME
- BUBLA_MAXSLEEPTIME
- BUBLA_IPERFSERVERHOST
- BUBLA_IPERFSERVERPORT


## Or commandline switches:
```
-l X set max time of load/stress to X seconds 
-s X set max time of sleep/no stress to X seconds 

-c X set max CPU to X
-i X set max IO to X 
-m X set max VM(mem) to X 

-h X set hostname of iperf server to X 
-p X set port of iperf server to X 
```
For exact behavior please check the shell script source and mainly documentation of https://people.seas.harvard.edu/~apw/stress/ and https://iperf.fr/.
