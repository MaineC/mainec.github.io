---
title: "Wonder if you should switch from your RDBMS to Apache Hadoop: Don't!"
date: 2013-08-26T17:10:58+02:00
tags: Hadoop,NOSQL,rdbms,
---

# Wonder if you should switch from your RDBMS to Apache Hadoop: Don't!


Last weekend I spend a lot of fun time at FrOSCon* in Sankt Augustin - always great to catch up with friends in the 
open source space. As always there were quite a few talks on NoSQL, Hadoop, but also really solid advise on tuning your 
system for stuff like MySQL (including a side note on PostgreSQL and Oracle) from Kristian Köhntopp. When following 
some of the discussions in the audience before and after the talk I could not help but shake my head on some of the 
advise given about HDFS and friends.<br><br>This is to give a really short rule of thumb on what project to use for 
which occasion. Maybe it helps clear some false assumptions. Note: All of the below are most likely gross 
oversimplifications. Don't use it as hard and fast advise but as a first step towards finding more information with 
your preferred search engine.<br><br><table><br><tr><th>Use Case 1 - relational 
data</th><th>Technology</th></tr><br><tr><td>I have usual relational data</td><td>Use a relational database - think 
MySQL and friends</td></tr><br><tr><td>I have relational data but my database doesn't perform.</td><td>Tune your 
system, go to step 1.</td></tr><br><tr><td>I have relational data but way more reads than one machine can 
accomodate.</td><td>Have master-slave replication turned on, configure enough slaves to accommodate your 
traffic.</td></tr><br><tr><td>I have relational data, but way too much data for a single machine.</td><td>Start 
sharding your database.</td></tr><br><tr><td>I have a lot of reads (or writes) and too much data for a single 
machine.</td><td>If the sharding+replication pain gets unbearable but you still need strong consistency guarantees 
start playing with HBase. You might loose the option of SQL but win being able to scale beyond traditional solutions. 
Hint: Unless your online product is hugely successful switching to HBase usually means you've missed some tuning 
option.</td></tr><br><tr><th>Use Case 2 - Crawling</th><th>Technology</th></tr><br><tr><td>I want to store and process 
a crawl of the internet.</td><td>Store it as flat files, if you like encode metadata together with the data in protocol 
buffers, thrift or Avro.</td></tr><br><tr><td>My internet crawl no longer fits on a single disk.</td><td>Put multiple 
disks in your machine, RAID them if you like.</td></tr><br><tr><td>Processing my crawl takes too long.</td><td>Optimise 
your pipeline. Make sure you utilise all processors in your machine.</td></tr><br><tr><td>Processing the crawl still 
takes too long.</td><td>If your data doesn't fit on a single machine, takes way too long to process but there is no 
bigger machine that you can reasonably pay for you are probably willing to take some pain. Get yourself more than one 
machine, hook them together, install Hadoop and use either plain map reduce , Pig, Hive or Cascading to process the 
data. Distribution-wise Apache, Cloudera, MapR, Hortonworks are all good choices.</td></tr><br><tr><th>Use Case 3 - 
BI</th><th>Technology</th></tr><br><tr><td>I have structured data and want my business analysts to find great new 
insights.</td><td>Use a data warehouse your analysts are most familiar with.</td></tr><br><tr><td>I want to draw 
conclusions from one year worth of traffic on a busy web site (hint: resulting log files no longer fit on the hard disk 
of my biggest machine).</td><td>Stream your logs into HDFS. From here it depends: If it's your developers that want to 
get their hands dirty, Cascading and depending packages might be a decent idea. There's plenty of UDFs in Pig that will 
help you as well. If the work is to be done by data analysts that only speak SQL use Hive.</td></tr><br><tr><td>I want 
to correlate user transactions with social media activity around my brand.</td><td>See 
above.</td></tr><br></table><br><br><b>A really short three bullet point summary</b><br><br><ul><br><li>Use HBase to 
scale the backend your end users interact with. If you want to trade strong consistency for being able to span multiple 
datacenters on multiple continents take a look at Cassandra.<br><li>Use plain HDFS with Hive/Pig/Cascading for batch 
analysis. This could be business intelligence queries against user transactions, log file analysis for statistics, data 
extraction steps for internet crawls, social media data or other sensor data.<br><li>Use Drill or Impala for low 
latency business intelligence queries.<br></ul><br><br><b>Good advise from ApacheConEU 2008/9</b><br><br>Back at one of 
the first ApacheCons I ever attended there was an Apache Hadoop BoF. One of the attendees asked for good reasons to 
switch from his current working infrastructure to Hadoop. In my opinion the advise he got from <a 
href="https://en.wikipedia.org/wiki/Christophe_Bisciglia">Christophe Bisciglia</a> is still valid today. Paraphrased 
version: <blockquote>For as long as you wonder why you should be switching to Hadoop, don't. </blockquote><br><br>A 
parting note: I've left CouchDB, MongoDB, JackRabbit and friends out of the equation. The reason for this is my own 
lack of first-hand experience with those projects. Maybe someone else can add to the list here.<br><br><small><br>* A 
note to the organisers: Thilo and myself married last year in September. So when seeing the term "Fromm" in a speaker's 
surname doesn't automatically mean that the speaker hotel room should be booked on the name "Thilo Fromm" - the speaker 
on your list could as well be called "Isabel Drost-Fromm". It was hilarious to have the speaker reimbursement package 
signed by my husband though this year around I was the one giving a talk at your conference ;)</small>
