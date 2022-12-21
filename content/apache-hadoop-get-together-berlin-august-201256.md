---
title: "Apache Hadoop Get Together Berlin - August 2012"
date: 2012-08-15T23:30:29+02:00
tags: [GetTogether,Cascalog,hcatalog,Hadoop,hive,Pig,Berlin,Get Together,]
---

# Apache Hadoop Get Together Berlin - August 2012


Despite beautiful summer weather roughly 50 people gathered at <a 
href="http://www.immobilienscout24.de">ImmobilienScout24</a> for the August 2012 edition of the <a 
href="http://www.xing.com/net/informationretrieval">Apache Hadoop Get Together</a> (Thanks again for hosting the event 
and sponsoring drinks and pizza to ImmoScout as well as to <a 
href="http://www.linkedin.com/profile/view?id=9861942">David Obermann</a> for organising the 
meetup.<br><br><center><img src="/hgt_2012.jpg"/></center><br><br>Today there 
were three talks: In the first presentation <a href="http://www.linkedin.com/in/draganmilosevic">Dragan Milosevic</a> 
(also known from his <a href="http://vimeo.com/10201534">talk at the Hadoop GetTogether</a> and his <a 
href="http://vimeo.com/43808511">presentation at Berlin Buzzwords</a>) provided more insight as to how Zanox is 
managing their internal RPC protocols in particular when it comes to versioning and upgrading protocol versions. Though 
in principle very simple to do this sort of problem still is very common when starting to roll out distributed systems 
and scaling them over time. The concepts he described were not unlike what is available today in projects like <a 
href="http://avro.apache.org">Avro</a>, <a href="http://thrift.apache.org/">Thrift</a> or <a 
href="http://code.google.com/p/protobuf/">protocol buffers</a>. However by the time they needed versioning support for 
their client server applications neither of these projects was a really good fit. This also highlights one important 
constraint: With communication being a very central component in distributed systems, changing libraries after an 
implementation went to production can be too painful to be followed through.<br><br>In the second presentation Stefanie 
Huber, Manuel Messner and Stephan Friese showed how Gameduell is using Hadoop to provide better data analytics for 
marketing, BI, developers, product managers et.al. Founded in 2003 they have a accumulated quite a bit of data 
consisting of micro transactions (related to payment operations), user activities, gaming results that need to be used 
for balancing games. Their team turned a hairy, complex system into a pretty clean, Hadoop based solution: By now all 
actions end up in a Hadoop cluster (with an option to subscribe to a feed for realtime events). Typically from there 
people would start analysis jobs either in plain map reduce or in pig and export the data to external databases for 
further analysis by BI people who preferred Hive as a query language as it is much closer to SQL than any of the 
alternatives. As of late they introduced <a href="http://incubator.apache.org/hcatalog">HCatalog</a> to support 
providing a common view on data for all three analysis options - in addition to allowing for a more abstract view of 
the data available that does not require knowing the exact filesystem structure to access the data.<br><br>After a 
short break in the last talk of the evening <a href="https://github.com/sthuebner">Stefan Hübner</a> introduced <a 
href="https://github.com/nathanmarz/cascalog/">Cascalog</a> to the otherwise pretty Java-savvy crowd. Being based on 
Cascading Cascalog provides for a concise way of formulating queries to a Hadoop cluster (compared to plain map 
reduce). Also when contrasted with Pig or Hive what stands out is the option to easily and seemlessly integrate 
additional functions (both map- and reduce-side) into Cascalog scripts without switching languages or abstractions. 
Note: When testing Cascalog scripts, one project to look at is <a 
href="https://github.com/sritchie/midje-cascalog">Midje</a>. <br><br>Overall a really interesting evening with lots of 
new input, interesting discussions and new input. Always amazing to see what other big data applications people in 
Berlin are developing. It's awesome to see so many development teams adopt seemingly new technologies (some even still 
in the <a href="http://incubator.apache.org">Apache Incubator</a>) for production systems. Looking forward to the next 
edition - as well as to the slides and videos of today's edition.
