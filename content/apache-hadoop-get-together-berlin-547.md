---
title: "Apache Hadoop Get Together Berlin"
date: 2013-05-08T23:41:54+02:00
tags: Hadoop,
---

# Apache Hadoop Get Together Berlin


This evening I joined the group over at <a href="http://www.immobilienscout24.de/">Immobilienscout 24</a> for today's 
Hadoop Get Together. David Obermann had invited Dr. Falk-Florian Henrich from CeleraOne to talk about their real-time 
analytics on live data streams.<br><br><center><img 
src="http://isabel-drost.de/Bilder/wordpress/hgt_june_2013_2.jpg"/></center><br><br>Their system is being used by <del> 
the <a href="http://global.nytimes.com/">New York Times</a></del> Springer's Die Welt for traffic analysis. The goal is 
to identify recurring users that might be willing to pay for the content they want to read. The trade-off here is to 
keep readers interested long enough to make them pay in the end, instead of scaring them away with a restrictive pay 
wall which would immediately lead to way less ad revenues.<br> <br>Currently CeleraOne's system is based on a 
combination of MongoDB for persistent storage, ZeroMQ for communicating with the revenue engine and http/json for 
connecting to the controlling web frontend. The live traffic analysis is all done in RAM, while long term storage ends 
up in MongoDB.<br><br>The second speaker was <a href="http://mhausenblas.info/">Michael Hausenblas</a> from <a 
href="http://www.mapr.com/">MapR</a>. He spends most of his time contributing to Apache Drill - an open source 
implementation of Google's Dremel.<br><br><table><tr><td><br><img 
src="http://isabel-drost.de/Bilder/wordpress/hgt_june_2013.jpg"/><br></td><td><img 
src="http://isabel-drost.de/Bilder/wordpress/hgt_june_2013_1.JPG"/><br></td></tr></table><br><br>Being an Apache 
project Drill is developed in an open, meritocratic way - contributors come from various different backgrounds. 
Currently Drill is in its early stages of development: They have a logical plan, a reference interpreter, a basic SQL 
parser. There is a demo application. As data backends they support HBase.<br><br>For most of the implementation they 
are trying to re-use existing libraries, e.g. for the columnar storage Drill is looking into either using Twitter's 
Parquet or Hive ORC file format.<br><br>In terms of contributing to the project: There is no need to be a rockstar 
programmer to make valuable contributions to Apache Drill: Use cases, documentation, test data are all valuable and 
appreciated by the project.<br><br>For more information check out the slide deck (this is an older version - this 
nights edition most likely soon to be published):<br><br><script async class="speakerdeck-embed" 
data-id="43402fe08d640130efa412313926fc13" data-ratio="1.33333333333333" 
src="//speakerdeck.com/assets/embed.js"></script><br><br>If you missed today's event make sure to get enlisted in the 
<a href="http://www.xing.com/net/informationretrieval">Hadoop Get Together Xing Group</a> so next time you get a 
notification. <br><br>One thing to note though: When registering for the event - please make sure to free your ticket 
if you cannot make it. I had a few requests from people who would have loved to attend today who didn't get a ticket 
but would most likely have fit into the room.
