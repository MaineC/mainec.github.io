---
title: "GoTo Con AMS - Day 2"
date: 2011-10-23T10:47:14+02:00
tags: amsterdam,gotocon,General,
---

# GoTo Con AMS - Day 2


Day two of GoTo Con Amsterdam started with a keynote by former Squeak developer Dan Ingalls. He introduced the Lively 
kernel - a component architecture for HTML5 that runs in any browser and allows easy composition, sharing and 
programming of items. Having seen Squeak years ago and being thrilled by its concepts even back then it was amazing to 
see what you can do with Lively kernel in a browser. If you are a designer and have some spare minutes to spend, 
consider taking a closer look at this project and dedicating some of your time to help them get better graphics and 
shapes for their system.<br><br>After the keynote I had a hard time deciding on whether to watch Ross Gardler's 
introduction to the Apache way or Friso van Vollenhoven's talk on building three Hadoop clusters in a year - too many 
interesting stuff in parallel that day. In the end I went for the Hadoop talk - listening to presentations on what 
Hadoop is actually being used for is always interesting - especially if it involves institutions like RIPE who have the 
data to analyze the internet downtime in Egypt.<br><br>Frise gave a great overview of Hadoop and how you can even use 
it for personal purposes: Apache Whirr makes it easy to use Hadoop in the cloud by enabling simple EC2 deployment, the 
Twitter API is a never ending source for more data to analyze (if you don't have any yourself).<br><br>After Jim 
Webber's presentation on the graph database neo4j I joined the talk on HBase use cases by Michael Stack. He introduced 
a set of HBase usages, problems people ran into and lessons learned. HBase in itself is built on top of HDFS - and as 
such inherits its advantages, strengths and some of its weaknesses.<br><br>It is great for handling 100s of GB up to PB 
of data in an online, random access but strong consistency kind of model. It provides a ruby based shell, comes with a 
java api, map reduce connectivity, pig, hive and cascading integration, provides metrics through the hadoop metrics 
subsystem that are exposed via JMX and through Ganglia, provides server side filters and co-processors, hadoop 
security, versioning, replication and more.<br><br><i>Stumbleupon</i><br><br><a 
href="http://www.stumbleupon.com/">Stumbleupon</a> deals with 1B stumbles a month, has 20M users (growing), users spend 
approx 7h a month stumbling. For them HBase is the de-factor storage engine. It's now 2.5years in production and 
enabled a "throw nothing away" culture, streamlined development. Analysis is done on a separate HBase cluster from the 
online version. Their lessons learnt: Educate engineering on how it works, study production numbers (small changes can 
make a for big payoff), over provisioning makes your life easier and gets your weekends 
back.<br><br><i>OpenTSDB</i><br><br>... is a distributed, scalable time series database that collects, stores and 
serves metrics on the fly. For stumbleupon it is their ears and eyes into the system that quickly replaced the usual 
mix of ganglia, munin and cacti.<br><br><i>Facebook</i><br><br>As announced earlier this year, Facebook's messaging 
system is based on HBase. Also facebook metrics and analytics are stored in HBase. The full story is available <a 
href="http://borthakur.com/ftp/RealtimeHadoopSigmod2011.pdf">in a SIGMOD paper by Facebook</a>. <br><br>In short - for 
Facebook Messaging HBase has to deal with 500M users, millions of messages and billions of instant messages per day. 
Most interesting piece of the system here was their migration path that by running both systems in parallel made 
switching over really smooth albeit still technologically challenging.<br><br>Their lessons learnt include the need to 
study production and adjust accordingly, to iterate on the schema to get it right. They also made the experience that 
there were still some pretty gnarly bugs - however with the help of the HBase community those could be sorted out bit 
by bit. They also concentrated on building a system that allows for locality - inter rack communication can kill 
you.<br><br><i>Yahoo</i><br><br>They keep their version of the bing webcrawl in HBase. They have high data ingest 
volumns (up to multiple TB/hour) from multiple streams. Atop their application also has a wide spectrum of access 
patterns (from scans down to single cell access). Yahoo right now runs the single larges known HBase cluster on top of 
980 2.4 GHz nodes with 16 cores and 24GB Ram each in addition to 6x2TB of disk. Their biggest table has 50B documents, 
most of the data is loaded in bulk though.<br><br><i>YFrog</i><br><br>... uses HBase as backend for their image hosting 
service. In contrast to the above HBase users they don't have a dedicated dev team but are highly motivated and skilled 
ops. Being cost senstive and with a little bit of bad luck with them really everything went bad that could go bad - 
from crashing JVMs, bad RAM crashes, bad glibc with a race condition, etc. Their lessons learnt include that it's 
better to run more smaller nodes than less big nodes. In addition lots of RAM is always great to avoid 
swapping.<br><br>The final talk I attended that day was on tackling the folklore around high performance computing. The 
speakers re-visited common wisdom that is generally known in the Java Community and re-evaluated it's applicability to 
recent hardware architectures. Make sure to check out their <a 
href="http://gotocon.com/dl/goto-amsterdam-2011/slides/DaveFarley_and_MartinThompson_TacklingTheFolkloreSurroundingHighP
erformanceComputing.pdf">slides</a> for details on common mis-conceptions when it comes to optimization patterns. Basic 
take away from this talk is to know not only your programming language and framework but also the VM you are 
implementing your code for, the system your application will run on and the hardware your stuff will be deployed to: 
Hardware vendors have gone to great length optimizing their systems, but software developers have been amazing at 
cancelling out those optimizations quicker then they were put in.<br><br>All in all a great conference with lots of 
inspiring input. Thanks to the organizers for their hard work. Looking forward to seeing some of you over in Vancouver 
for Apache Con NA 2011.
