---
title: "JAX: Java HPC by Norman Maurer"
date: 2013-05-19T20:31:16+02:00
tags: [performance,Event,JAX,netty,]
---

# JAX: Java HPC by Norman Maurer


For slides see also: <a 
href="https://speakerdeck.com/normanmaurer/high-performance-networking-on-the-jvm-less<br>ons-learned">Speakerdeck: 
High performance networking on the JVM</a><br><br><P><br>Norman started his talk clarifying what he means by high 
scale: Anything above<br>1000 concurrent connections in his talk are considered high scale, anything<br>below 100 
concurrent connections is fine to be handled with threads and blocking<br>IO. Before tuning anything, make sure to 
measure if you have any problem at<br>all: Readability should always go before optimisation.<br><br><P><br>He gave a 
few pointers as to where to look for optimisations: Get started by<br>studying the socket options - TCP-NO-DELAY as 
well as the send and receive<br>buffer sizes are most interesting. When under GC pressure (check the GC locks<br>to 
figure out if you are) make sure to minimise allocation and deallocation of<br>objects. In order to do that consider 
making objects static and final where<br>possible. Make sure to use CMS or G1 for garbage collection in order 
to<br>maximise throughput. Size areas in the JVM heap according to your access<br>patterns. The goal should always be 
to minimise the chance of running into a<br>stop the world garbage collection.<br><br><P><br>When it comes to using 
buffers you have the choice of using direct or heap<br>buffers. While the former are expensive to create, the latter 
come with the<br>cost of being zero'ed out. Often people start buffer pooling, potentially<br>initialising the pool in 
a lazy manner. In order to avoid memory fragmentation<br>in the Java heap, it can be a good idea to create the buffer 
at startup time<br>and re-use it later on.<br><br><P><br>In particular when parsing structured messages like they are 
common in<br>protocols it usually makes sense to use gathering writes and scattering reads<br>to minimise the number of 
system calls for reading and writing. Also try to<br>buffer more if you want to minimise system calls. Use slice and 
duplicate to<br>create views on your buffers to avoid mem copies. Use a file channel when<br>copying files without 
modifications.<br><br><P><br>Make sure you do not block - think of DNS servers being unavailable or slow as<br>an 
example.<br><br><P><br>As a parting note,  make sure to define and document your threading model. It<br>may ease 
development to know that some objects will always only be used in a<br>single threaded context. It usually helps to 
reduce context switches as well as<br>may ease development to know that some objects will always only be used in 
a<br>single threaded context. It usually helps to reduce context switches as well as<br>keeping data in the same thread 
to avoid having to use synchronisation and the<br>use of volatile.<br><br><P><br>Also make a conscious decision about 
which protocol you would like to use for<br>transport - in addition to tcp there's  also udp, udt, sctp. Use pipelining 
in<br>order to parallelise.<br><br><P><br>
