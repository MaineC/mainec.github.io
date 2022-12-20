---
title: "GoTo Con AMS - Day 1"
date: 2011-10-22T20:44:03+02:00
tags: amsterdam,gotocon,General,
---

# GoTo Con AMS - Day 1


Last week <a href="http://gotocon.com/amsterdam-2011/">GoTo Con</a> took place in Amsterdam. Being a sister conference 
to GoTo in Aarhus the Amsterdam event focused on the broad topics of agile development, architectural challenges, 
backend and frontend development, platforms like the JVM and .NET. In addition the Amsterdam event featured a special 
Apache track tailored towards presentations focusing on the development model at Apache and the technologies developed 
at Apache.<br><br><h2>Keynote: Dart</h2><br><br>The first day started with the keynote by Kasper Lund who introduced 
Google's new language Dart. Kasper was involved with developing V8 at Google. Based on his (and other project members') 
experiences with large JavaScript projects the idea to create a new language for the browser was born. The goal was to 
build a language that had less pitfalls than JavaScript, makes it easier to provide tool support for and makes 
reasoning about code easier. <a href="http://try.dartlang.org">Dart</a> comes with class based single inheritance, 
lexical scoping, optional typing. It is by design single threaded. The concept of isolates cleanly introduces the 
concept of isolated workers that communicate through message passing only and thus can be run in parallel by the VM. 
One concept that seemed particularly interesting for an interpreted language was that of snapshots: An application can 
be serialized after it has loaded and initialized, the result can even be transferred, shortening load time 
substantially.<br><br>So far Dart is just a tech preview - on the agenda of the development team we find items such as 
better support for REST arguments, enums, reflection, pattern matching, tooling for test coverage and profiling. All <a 
href="http://dart.googlecode.com">code is freely available</a>, also the <a href="http://dartlang.org">language 
specification and tutorials</a> are open. The developers would love to get more feedback from external 
teams.<br><br><h2>Twitter JVM tuning best practices</h2><br><br>In his presentation on JVM tuning Attila Szegedi went 
into quite some detail on what kind of measures Twitter usually takes when it comes to optimizing code that run on the 
JVM and exhibits performance issues. Broadly speaking there are three dimensions along which the usual culprits for bad 
performance hide: <br><ul><br><li>Memory footprint of the applciation.<br><li>Latency of requests.<br><li>Thread 
coordination issues.<br></ul><br><br><b>Memory footprint reduction</b><br><br>A first step always should be to verify 
that memory is actually responsible for the issues seen. Running the JVM with verbosegc turned on helps identify how 
often and how effective full GC cycles happen on the machine. Next step is to take into account the simple solution: 
Evaluate whether the application can simply be given more memory. If that does not help or is impossible start thinking 
about how to shrink memory requirements: Use caching to avoid having to load all data im memory at once, trim down the 
data representation used in your implementation, when looking into what to trim know exactly what amount of memory 
various objects need and how many of these object you actually keep in memory - this analysis should also go into 
detail when using code generated from frameworks like thrift. <br><br><b>Latency fights</b><br><br>When taking a simple 
view latency optimization boils down to making a tradeoff between memory usage and time. A little less naive view is to 
understand that actually it is a set of three goals to optimize:<br><br><img 
src="http://isabel-drost.de/Bilder/wordpress/triangle_goto_11.png" width="300" style="float:left"/><br><br>Tuning an 
application means to take the product of the three, shift focus but keep the product stable. Optimization is assumed to 
increase the resulting product.<br><br>Biggest thread to latency are full gc cycles. Things to keep in mind when tuning 
and optimizing: Though the type of gc to run is configurable, this configuration does not apply to cleanup of eden 
space - Eden is always cleaned up with a stop-the-world gc. In general this is not too grave, as cleaning up objects 
that are no longer referenced is very cheap. However it can turn into a problem when there are too many surviving 
objects.<br><br>When it comes to selecting GC implementations: Optimize for throughput by delaying GC for as long as 
possible. This is especially handy for bulk jobs. When optimizing for responsiveness use low pause collectors - they 
incur a somewhat constant penalty however those avoid having single requests with extremely large response time. This 
is most handy for online jobs.<br><br>Other options to look into: Use adaptivesizepolicy and maxgcholdmillis to allow 
the jvm to size heap on its own based on your target characteristics. Use the printheapatgc option to view gc heap 
collection statistics - especially watch out for fromspace being less than 100%, use printtenuredistribution to keep an 
eye on number of ages, size distribution. In general, give an app as much memory as possible - when using concurrent 
mark and sweep implementation make sure to over-provision by about 25 to 30% to give the app a gc cushion for 
operation. If you can spare one cpu, set initiateoccupationfraction to 0 and let gc run all the time.<br><br><b>Thread 
coordination</b><br><br>The last issue in general causing delays are thread coordination issues. The facilities for 
multi-threaded programming in Java are still pretty low level - even worse, developers generally hardly know about 
synchronized - not so much about the atomic data types that are available - let alone other features of the concurrent 
package.<br><br>Make sure you check out the speaker's <a 
href="http://gotocon.com/dl/goto-amsterdam-2011/slides/AttilaSzegedi_JVMPerformanceOptimizationsAtTwittersScale.pdf">sli
des</a> they certainly contain valuable information for developers that want to scale their Java 
applications.<br><br><h2>Akka</h2><br>Another talk that was pretty interesting to me was the introduction of Akka - a 
project I had only heard about before but did not have any deep technical background knowledge on. The goals when 
building it were fault tolerance, scalability and concurrency. Basically an easy way to scale up and out. Built in 
Scala, Akka also comes with Java bindings.<br><br>Akka is built around the actor model for easier distribution. Actors 
are isolated, communicate only via messages and have no shared memory - making it easy to run them in a distributed way 
without having to worry about synchronization. Distribution across machines is currently based on protocol buffers and 
NIO. However the resulting network topology is still hard wired during development time.<br><br>The goal of new Akka 
developments is to make roll-out dynamic and adaptive. For that they came up with a zookeeper based virtual address 
resolution, configurable load balancing strategies and the option for reconfiguration during 
runtime.<br><br><h2>Concluding remarks</h2><br><br>The first day was filled with lots of technical talks - so several 
remained more on the overview/introductory level - which is a good thing to learn about new technologies. In addition 
there were a few presentations on new features of upcoming and past releases for instance for Java 7 and Sprint 3.1 - 
it's always nice to learn about the rational behind changes and improvements.<br><br>As for the agile talks - most of 
them propagated pretty innovative ideas that need a lot of courage to put into practice. However in several cases I 
could not help but get the feeling that either the processes presented were very specific to the environment they were 
established in and would not survive sudden stress - be it decline in revenue or team issues. In addition quite a few 
ideas that were introduced as novelties were already inherent in existing processes: Trust and natural communication 
really is the goal when establishing things like Scrum. In the end, the meetings are just the tool to get there. 
Clarity wrt to vision and even business value is core to prioritizing work to be done. Understanding and finding 
suitable metrics to measure and monitor business value of a product should be at the heart of any development 
project.<br><br>Overall the first day brought together a good crowd of talented people exchanging interesting ideas, 
news on current projects and technical details of battle-field-stories. Being still rather small, the Amsterdam edition 
of GoTo con certainly made it easy to get in touch with speakers as well as other attendees over a cup of coffee and 
discuss the presented issues. Huge thanks to the organizers for putting together an interesting schedule, booking a 
really tasty meal and having a friendly answer to any question from confused attendees.
