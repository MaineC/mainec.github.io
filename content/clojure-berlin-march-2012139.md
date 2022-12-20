---
title: "Clojure Berlin - March 2012"
date: 2012-03-07T22:37:03+01:00
tags: [clojure,Cascalog,Hadoop,Event,General,]
---

# Clojure Berlin - March 2012


In today's <a href="http://www.meetup.com/Clojure-Berlin/">Clojure meetup</a> <a 
href="http://twitter.com/#!/sthuebner">Stefan Hübner</a> gave an introduction to <a 
href="https://github.com/nathanmarz/cascalog">Cascalog</a> - a Clojure library based on <a 
href="http://www.cascading.org/">Cascading</a> for large scale data processing on Apache Hadoop without 
hassle.<br><br>After a brief overview of what he is using the tool for to do log processing at his day job for <a 
href="http://maps.nokia.com/">http://maps.nokia.com</a> Stefan went into some more detail on why he chose Cascalog over 
other project that provide abstraction layers on top of Hadoop's plain map/reduce library: Both Pig and Hive provide 
easy to learn SQL-like languages to quickly write analysis jobs. The major disadvantage however comes when in need for 
domain specific operators - in particular when these turn out to be needed just once: Developers end up switching back 
and forth between e.g. Pig Latin and Java code to accomplish their analysis need. These kinds of one-off analysis tasks 
are exactly where Cascalog shines: No need to leave the Clojure context, just program your map/reduce jobs on a very 
high level (Cascalog itself is quite similar to datalog in syntax which makes it easy to read and simple to forget 
about all the nitty-gritty details of writing map/reduce jobs).<br><br>Writing a join to compute persons' age and 
gender from a trivial data model is as simple as typing:<br><br><code><br>  ;; Persons' age and gender<br>  (?<- 
(stdout)<br>       [?person ?age ?gender]<br>       (age ?person ?age)<br>       (gender ?person 
?gender)<br></code><br><br>Multiple sorts of input generators are implemented already: Reading text files, using files 
in HDFS as input are both common use cases. Of course it is possible to provide your own implementation for that as 
well to integrate any type of data input in addition to what is available already.<br><br>In my view Cascalog combines 
the speed of development that was brought by Pig and Hive with the flexibility of being able to seemlessly switch to a 
powerful programming language for anything custom. If you yourself have been using or even contributing to either 
Cascalog or Cascading: I'd love to see your submission to <a 
href="http://berlinbuzzwords.de/content/call-submissions">Berlin Buzzwords</a> - remember, the submission deadline is 
this week on Sunday *MEZ*.
