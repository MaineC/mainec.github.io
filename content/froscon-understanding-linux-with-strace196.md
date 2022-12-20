---
title: "FrOSCon - understanding Linux with strace"
date: 2012-09-06T20:29:10+02:00
tags: [Event,General,]
---

# FrOSCon - understanding Linux with strace


Being a Java child I had only dealt with strace once before: Trying to figure out whether any part of the Mahout tests 
happens to use /dev/random for initialisation in a late night debugging session with my favourite embedded Linux 
developer. Strace itself is a great tool to actually see what your program is doing in terms of system calls, giving 
you the option to follow on a very detailed level what is going on.<br><br>In his talk Harald König gave a very easy to 
follow over view on <a href="http://programm.froscon.de/2012/events/924.html">how to understand Linux with strace</a>. 
Starting with the basic use cases (trace file access, program calls, replay data, analyse time stamps, do some 
statistics) the quickly moved on to showing some more advanced tricks you can do with the little tool: Finding 
sys-calls that take surprisingly long vs. times when user code is doing long-running computations. Capturing and 
replaying e.g. networking related calls to simulate problems that the application runs into. Figuring out bottlenecks 
(or just plain weird stuff) in the application by figuring out the most frequent syscall. Figuring out which 
configuration files an application really touches - sorting them by last modified date with a bit of shell magic might 
give an answer to the common question of whether the last update or the last time the user tinkered with the 
configuration turned his favourite editor to appear green instead of white. On the other hand it can also reveal when 
configurations have been deleted (in the presentation he moved away the user-emacs configuration. As a result emacs 
tried >30 times to find it for various configuration options during startup: Is it there? No. ... Is it now there? No. 
... Maybe now? Nope. ... ;) ).<br><br>When looking at strace, you might also want to take a look at ltrace that traces 
library calls - the output there might be a bit more readable in that it's not just system calls but also library 
calls. Remember though that tracing everything can not only make your app pretty slow but also quickly generates 
several gigabytes of information.
