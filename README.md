# Process Pairs - Watchdog

You have already dealt with an unreliable program in task "ROC", where the faults occur deterministically. You already know how to analyze and to harden your environment. But those are not the only reasons for that an application might crash. One further reason could be a library that your application depends on crashes non-deterministically. This crashes your application, too.It is unacceptable for an long running service to be restarted by a system administrator by hand after each crash. Instead the service implementation has to cope with this.

You shall implement the "process pair" approach to harden our watch dog service.

## Process Pair approach

The approach is to have a pair of processes: a worker and a watch dog. The worker is your regular service. The watch dog process waits for the worker to crash. It spawns an new worker process immediately after the original has worker crashed.

## Your Task

We provide you with a web server watch dog implementation. You have to add the process pair approach to make it more reliable.
