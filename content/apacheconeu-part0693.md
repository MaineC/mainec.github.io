---
title: "ApacheConEU - part 06"
date: 2012-11-15T20:48:35+01:00
tags: ApacheCon,Apache Con,tomcat,apacheconeu,
---

# ApacheConEU - part 06


For the next session I joined the Tomcat crowd in Marc Thomas' to learn more on Tomcat reverse proxy configurations. 
One rather common setup is to have Tomcat connected to an httpd instance. One common issue encountered with this setup 
in particular when running httpd with the event mpm is the problem of thread exhaustion on tomcat's side. Fixes include 
always having more active tomcat threads than there can be httpd threads at any one time and to disable persistent 
connections. Keep in mind that tomcat performance does not degrade gracefully here - in case of thread exhaustion it 
just goes downhill very quickly. One famous example here was an issue with the ASF jira: After weeks of debugging bad 
performance, after blaming the hardware, the os, the JVM, the java implementation in generally finally the number of 
threads was increased resulting in a smoothly running system...<br><br>Another common configuration problem is to 
rename to deployed web application war - for instance in order to keep the version number in the war name itself - and 
change the path on httpd's side. This is bad for at least for reasons:<br><ul><br><li>redirects will fail - you can 
configure ProxyReversePath which will fix some issues but does not affect all http headers<br><li>cookie paths break - 
you can configure CookiePathReverse here<br><li>links that are generated in the web app will fail - you can use 
mod_sed/ _substitute/ _proxy_html to fix that - however those configurations tend to become messy and are error 
prone<br><li>custom headers usually also break<br></ul><br><br>If the only reason for doing such a thing is to keep the 
version number in the file name it might be an option to use "foo##bar.1.2.3" as filename - tomcat will ignore anything 
after the hashtags.<br><br>When dealing with proxying traffic make sure to inform tomcat about https termination events 
in order to correctly handle secure cookies and sessions. This is done automatically with mode_jk and mod_ajp, 
mod_proxy needs some more manual work. When dealing with virtual hosting make sure to use ProxyPreserveHeader in order 
to be able to switch hosts on Tomcat's side.<br><br><br>Julien Nioche shared some details on the nutch crawler. Being 
the mother of all Hadoop projects (as in Hadoop was born out of developments inside of nutch) the project has become 
rather quite with a steady stream of development in the recent past. Julien himself uses the nutch for gathering 
crawled data for several customer projects - feeding this data into an NLP pipeline based on Behemoth that glues 
Mahout, UIMA and Gate together.<br><br>The basic crawling steps including building the web graph, computing a link 
based ranking method and indexing are still the same since last I looked at the project - just that for indexing the 
project now uses solr instead of their own lucene based solution.<br><br>The main advantage of nutch is its 
pluggability: the protocol parser, html filter, url filter, url normaliser all can be exchanged against your own 
implementations.<br><br>In their 2.0 version they moved away from using their own plain hdfs storage to a table schema 
- mapped to the real database through Gora, an abstraction layer to connect to e.g. Cassandra or HBase. The schema 
itself is based on Avro but can be adopted to your needs. The advantages are obvious: Though still distributed this 
approach is much easier and simpler in terms of logic kept in nutch itself. Also it is easier to connect to the data 
for third parties - all you need is the schema as well as Gora. The current disadvantage lies in it's configuration 
overhead and instability compared to the old solution. Most likely at least the latter one will go away as version 2.0 
stableises.<br><br>In terms of future work the project focuses on stabilisation, synchronising features of version 1.x 
and 2.x (link ranking is only available in version 1.x while support for elastic search is only available in version 
2.x). In terms of functionality the goal is to move to Solr Cloud, support sitemaps (as implemented by commons 
crawler), more (pluggable?) indexers.<br><br>The goal is to delegate implementations - it was already done for Tika and 
Solr. Most likely it will also happen for the fetcher, protocol handling, robots.txt handling, url normalisation and 
filtering, graph processing code and others.<br><br><br>The next talk in the Solr/Lucene talk dealt with scaling Solr 
to big data. The goal of the speaker was to index 100 million documents - the number of documents was expected to grow 
in the future. Being under heavy time pressure and having a bash wizard on the project they started building lots of 
their glue code and components in bash scripts: There were scripts for starting/stopping services, remote indexing, 
performance monitoring, content extraction, ingestion and deployment. Short term this was a very good idea - it allowed 
for fast iterations and learning. On the long run they slowly replaced their custom software with standard components 
(tika for content extraction, puppet for deployment etc.).<br><br>They quickly learnt to value property files in order 
to easily reconfigure the system even in production (relying heavily on bash xml was of course not an option). One 
problem this came in handy with was adjusting the sharding configuration - going from a simple random sharding to old 
vs new to  monthly they could optimise the configuration to their load. What worked well for them was to separate JVM 
startup from Solr core startup - they would start with empty solrs 
