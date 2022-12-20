---
title: "JAX: Pigs, snakes and deaths by 1k cuts"
date: 2013-05-20T20:32:16+02:00
tags: [performance,Java,Event,JAX,]
---

# JAX: Pigs, snakes and deaths by 1k cuts


In his talk on performance problems Rainer Schuppe gave a great introduction to<br>which kinds of performance problems 
can be observed in production and how to<br>best root-cause them.<br><br><P><br>Simply put performance issues usually 
arise due to a difference in either data<br>volumn, concurrency levels or resource usage between the dev, qa and 
production<br>environments. The tooling to uncover and explain them is pretty well known:<br>Staring with looking at 
logfiles, ARM tools, using aspects, bytecode<br>instrumentalisation, sampling, watching JMX statistics, and PMI 
tools.<br><br><P><br>All of theses tools have their own unique advantages and disadvantages. With<br>logs you get the 
most freedom, however you have to know what to log at<br>development time. In addition logging is i/o heavy, so doing 
too much can slow<br>the application down itself. In a common distributed system logs need to be<br>aggregated somehow. 
As a simple example of what can go wrong are cascading<br>exceptions spilled to disk that cause machines to run out of 
disk space one<br>after the other. When relying on logging make sure to keep transaction<br>contexts, in particular 
transaction ids across machines and services to<br>correlate outages. In terms of tool support, look at scribe, splunk 
and flume.<br><br><P><br>A tool often used for tracking down performance issues in development is the<br>well known 
profiler. Usually it creates lots of very detailed data. However it<br>is most valuable in development - in production 
profiling a complete server<br>stack produces way too much load and data to be feasable. In addition there's<br>usually 
no transaction context available for correlation again.<br><br><P><br>A third way of watching applications do their 
work is to watch via JMX. This<br>capability is built in for any Java application, in particular for 
servlet<br>containers. Again there is not transaction context. Unless you take care of it<br>there won't be any 
historic data.<br><br><P><br>When it comes to diagnosing problems, you are essentially left with fixing<br>either the 
"it does not work" case or the "it is slow case".<br><br><P><br>For the "it is slow case" there are a few 
incarnations:<br><br><UL><br><LI>It was always slow, we got used to it.<br></LI><br><LI>It gets slow over 
time.<br></LI><br><LI>It gets slower exponentially.<br></LI><br><LI>It suddenly gets slow.<br></LI><br><LI>There is a 
spontanous crash.<br></LI><br></UL><br><br><P><br>In the case of "it does not work" you are left with the following 
observations:<br><br><UL><br><LI>Sudden outages.<br></LI><br><LI>Always flaky.<br></LI><br><LI>Sporadic error 
messages.<br></LI><br><LI>Silent death.<br></LI><br><LI>Increasing error rates.<br></LI><br><LI>Misleading error 
messages.<br></LI><br></UL><br><br><P><br>In the end you will always be spinning in a Look at symptoms, 
Elimnate<br>non-causes, Identifiy suspects, Confirm and Eliminate comparing to normal. If<br>not done with that, 
leather, rinse, repeat. When it comes to causes for errors<br>and slowness you will usually will run into one of the 
following causes: In<br>many cases bad coding practices are a problem, too much load, missing backends,<br>resource 
conflicts, memory and resource leakage as well as hardware/networking<br>issues are causes.<br><br><P><br>Some symptoms 
you may observe include foreseeable lock ups (it's always slow<br>after four hours, so we just reboot automatically 
before that), consistent<br>slowness, sporadic errors (it always happens after a certain request came in),<br>getting 
slow and slower (most likely leaking resources), sudden chaos (e.g.<br>someone pulling the plug or someone removing a 
hard disk), and high utilisation<br>of resources.<br><br><h2>Linear memory leak</h2><br><br>In case of a linear memory 
leak, the application usually runs into an OOM<br>eventually, getting ever slower before that due to GC pressure. 
Reasons could<br>be linear structures being filled but never emptied. What you observe are<br>growing heap utilisation 
and growing GC times. In order to find such leakage<br>make sure to turn on verbose GC logging, do heapdumps to find 
leaks. One<br>challenge though: It may be hard to find the leakage if the problem is not one<br>large object, but many, 
many small ones that lead to a death by 1000 cuts<br>bleeding the application to death.<br><br><P><br>In development 
and testing you will do heap comparisons. Keep in mind that<br>taking a heap dump causes the JVM to stop. You can use 
common profilers to look<br>at the heap dump. There are variants that help with automatic leak 
detection.<br><br><P><br>A variant is the pig in a python issue where sudden unusually large objects<br>cause the 
application to be overloaded.<br><br><H2><A NAME="SECTION00332000000000000000"><br>Resource leaks and 
conflicts</A><br></H2><br>Another common problem is leaking resources other than memory - not closing<br>file handles 
can be one incarnation. Those problems cause a slowness over time,<br>they may lead to having the heap grow over time - 
usually that is not the most<br>visible problem though. If instance tracking does not help here, your last<br>resort 
should be doing code audits.<br><br><P><br>In case of conflicting resource usage you usually face code that was 
developed<br>with overly cautious locking and data integrity constraints. The way to go are<br>threaddumps to uncover 
threads in block and wait states.<br><br><H2><A NAME="SECTION00333000000000000000"><br>Bad coding 
practices</A><br></H2><br>When it comes to bad coding practices what is usually seen is code in endless<br>loops (easy 
to see in thread dumps), cpu bound computations where no result<br>caching is done. Also layeritis with too much 
(de-)serialisation can be a<br>problem. In addition there is a general "the ORM will save us all" problem that<br>may 
lead to massive SQL statements, or to using the wrong data fetch strategy.<br>When it comes to caching - if caches are 
too large, access times of course grow<br>as well. There could be never ending retry loops, ever blocking 
networking<br>calls. Also people tend to catch exceptions but not do anything about them<br>other than adding a little 
#fixme annotation to the code.<br><br><P><br>When it comes to locking you might run into dead-/live-lock problems. 
There<br>could be chokepoints (resources that all threads need for each processing<br>chain). In a thread dump you will 
typically see lots of wait instead of block<br>time.<br><br><P><br>In addition there could be internal and external 
bottlenecks. In particular<br>keep those in mind when dealing with databases.<br><br><P><br>The goal should be to find 
an optimum for your application between too many too<br>small requests that waste resources getting dispatched, and one 
huge request<br>that everyone else is waiting for.<br><br>
