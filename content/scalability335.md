---
title: "Scalability"
date: 2010-06-23T11:17:53+02:00
tags: [CouchDB,Free Software,scalability,]
---

# Scalability


For Berlin Buzzwords we concentrated pretty heavily on scalable systems and architectures: We had talks on Hadoop for 
scaling data analysis; HBase, Cassandra and Hypertable for scaling data storage; Lucene and Solr for scaling 
search.<br><br>A recurring pattern was people telling success stories involving project that either involve large 
amounts of data or growing user numbers. Of course the whole topic of scalability is <a 
href="http://teddziuba.com/2008/04/im-going-to-scale-my-foot-up-y.html">extremely interesting</a> for ambitious 
developers: Who would not be happy to solve internet-scale problems, have petabytes of data at his fingertips or tell 
others that their "other computer is a data center".<br><br>There are however two aspects of scalability that people 
tend to forget pretty easily: First of, if you are designing a new system from scratch that implements a so far unknown 
business case - your problem most likely is not scalability. It's way more likely that you have to solve marketing 
tasks, just getting people to use your cool new application. Only after observing what users actually do and use you 
have the slightest chance of spotting the real bottlenecks and optimising with clear goals in mind (e.g. reduce 
database load for user interaction x by 40%).<br><br>The second issue people tend to forget about scalability is that 
the term is about scaling systems - some developers easily mix that up with high performance. The goal is not to be 
able to deal with high work load, but to build a system that can deal with increasing (or decreasing) work load. 
Ultimately this means that not only your technology must be scalable: Any architecture can only scale to a certain 
load. The organisation building the system must be willing to continuously monitor the application they built - and be 
willing to <a href="http://videolectures.net/wsdm09_dean_cblirs/">re-visit architectural decisions</a> if the 
environment changes. <br><br>Jan Lehnardt had a very interesting point in his talk on CouchDB: When talking about 
scalability, people usually look into the upper right corner of the application benchmark. However to be truely 
scalable one should also look into the lower left corner: Being scalable should not only mean to be able to scale 
systems up - but also to be able to scale them down. In the case of CouchDB this means that not only large 
installations at BBC are possible - but running the application on mobile devices should be possible without problems 
as well. It's an interesting point in the current "high scalability" hype.
