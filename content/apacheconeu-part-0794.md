---
title: "ApacheConEU - part 07"
date: 2012-11-16T20:51:08+01:00
tags: nutch,Apache Con,ApacheCon,Lucene,gora,apacheconeu,Solr,
---

# ApacheConEU - part 07


Julien Nioche shared some details on the nutch crawler. Being the mother of all Hadoop projects (as in Hadoop was born 
out of developments inside of nutch) the project has become rather quite with a steady stream of development in the 
recent past. Julien himself uses the nutch for gathering crawled data for several customer projects - feeding this data 
into an NLP pipeline based on Behemoth that glues Mahout, UIMA and Gate together.<br><br>The basic crawling steps 
including building the web graph, computing a link based ranking method and indexing are still the same since last I 
looked at the project - just that for indexing the project now uses solr instead of their own lucene based 
solution.<br><br>The main advantage of nutch is its pluggability: the protocol parser, html filter, url filter, url 
normaliser all can be exchanged against your own implementations.<br><br>In their 2.0 version they moved away from 
using their own plain hdfs storage to a table schema - mapped to the real database through Gora, an abstraction layer 
to connect to e.g. Cassandra or HBase. The schema itself is based on Avro but can be adopted to your needs. The 
advantages are obvious: Though still distributed this approach is much easier and simpler in terms of logic kept in 
nutch itself. Also it is easier to connect to the data for third parties - all you need is the schema as well as Gora. 
The current disadvantage lies in it's configuration overhead and instability compared to the old solution. Most likely 
at least the latter one will go away as version 2.0 stabelises.<br><br>In terms of future work the project focuses on 
stabilisation, synchronising features of version 1.x and 2.x (link ranking is only available in version 1.x while 
support for elastic search is only available in version 2.x). In terms of functionality the goal is to move to Solr 
Cloud, support sitemaps (as implemented by commons crawler), more (pluggable?) indexers.<br><br>The goal is to delegate 
implementations - it was already done for Tika and Solr. Most likely it will also happen for the fetcher, protocol 
handling, robots.txt handling, url normalisation and filtering, graph processing code and others.<br><br><br>The next 
talk in the Solr/Lucene talk dealt with scaling Solr to big data. The goal of the speaker was to index 100 million 
documents - the number of documents was expected to grow in the future. Being under heavy time pressure and having a 
bash wizard on the project they started building lots of their glue code and components in bash scripts: There were 
scripts for starting/stopping services, remote indexing, performance monitoring, content extraction, ingestion and 
deployment. Short term this was a very good idea - it allowed for fast iterations and learning. On the long run they 
slowly replaced their custom software with standard components (tika for content extraction, puppet for deployment 
etc.).<br><br>They quickly learnt to value property files in order to easily reconfigure the system even in production 
(relying heavily on bash xml was of course not an option). One problem this came in handy with was adjusting the 
sharding configuration - going from a simple random sharding to old vs new to  monthly they could optimise the 
configuration to their load. What worked well for them was to separate JVM startup from Solr core startup - they would 
start with empty solrs and only point them to the data directories aafter verifying that the JVMs booted up 
correctly.<br><br>In terms of performance they learnt to go wide quickly - instead of spending hours on optimising 
their one huge box they ended up distributing their solrs to multiple separate machines.<br><br>In terms of ingestion 
pipelines: Theirs is currently based on an indexing directory convention, moving the indexing as soon as all data is 
ingested. The advantage here is the atomicity of mv that can be used - disadvantage is having to move around lots of 
data. Their goal is to go for hdfs for indexing soon and zookeeper for configuration handling.<br><br>In terms of 
testing: In contrast to having a dev-test-production environment their goal is to have an elastic compute cloud that 
can be adjusted accordingly. Though EC2 itstelf is very cost intensive, poses additional problems with firewalling and 
moving data their cloud computing could still be a solution - in particular given projects like cloud stack or open 
cloud. The goal would be to do cycle scavaging in their own datacenter, do heavy computations when there is not a lot 
of load on the system and turn those analysis of in case of incoming traffic.<br><br>When it comes to testing and 
monitoring changes they made good experiences with using JConsole (connecting it to several solrs at once through a 
simple ip discovery script) and solr meter as a performance debugging tool.<br><br>Some implementation details: They 
used Solr as some sort of NoSQL cache as well (for thousands of queries/s), push the schema definition to solr from the 
app, have common fields and the option for developers to add custom fields in the app. Their experience is to not do 
expensive stuff in solr but to move that outside - this applies in particular to content extraction. For storage they 
used an avro based binary file format (mainly in order to save storage space, have a versioned schema and fast 
compression and de-compression). They are starting to use tika as their pipeline and for auto content detection, 
scaling up with behemoth. They learnt to upgrade indexes without re-indexing using the lucene upgrade tooling. In 
addition they use Grimreaper to kill servers if anything goes wrong and restart it later.
