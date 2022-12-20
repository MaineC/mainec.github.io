---
title: "Devoxx – Day two – Hadoop and HBase "
date: 2010-12-08T21:24:40+01:00
tags: hbase,Hadoop,Devoxx,General,
---

# Devoxx – Day two – Hadoop and HBase 


In his session on the current state of Hadoop Tom went into a little more detail not only on the features released in 
the latest release or on the roadmap for upcoming releases (including Kerberos based security, append support, warm 
standby namenode and others).<br>He also gave a very interesting view on the current Hadoop ecosystem. More and more 
projects are currently being created that either extend Hadoop or are built on top of Hadoop. Several of these are 
being run as projects at the Apache Software Foundation, however some are available outside of Apache only. Using 
graphviz he created a graph of projects depending on or extending Hadoop and from that provided a rough classification 
of these projects. <br><br>As to be expected HDFS and Map/Reduce are part of the very basis of this ecosystem. Right 
next to them sits <a href=”http://zookeeper.apache.org”>zookeeper</a>, a distributed coordination and looking 
service.<br><br>Storage systems extending the capabilities of HDFS include <a href=”http://hbase.apache.org”>HBase</a> 
that adds random read/write as well as realtime access to the otherwise batch-oriented distributed file-system. With <a 
href=”http://pig.apache.org”>PIG</a> and <a href=”http://hive.apache.org”>Hive</a> and Cascading three projects are 
making it easier to formulate complex queries for Hadoop. Among the three, PIG is mainly focussed on expressing data 
filtering and processing, with SQL support being added over time as well. Hive came from the need for SQL formulation 
on Hadoop clusters. Cascading goes a slightly different way, providing a Java API for easier query formulation. The new 
kid on the block sort of is Plume, a project initiated by Ted Dunning that has the goal of coming up with a Map/Reduce 
abstraction layer inspired by Google's Flume Java publication.<br><br>There are several projects for data import into 
HDFS. Sqoop can be used for interfacing with RDMBS. Chukwa and Flume deals with feeding log data into the filesystem. 
For general co-ordination and workflow orchestration there is the release of Oozie, originally developed at Yahoo! as 
well as support for workflow definition in Cascading.<br><br>When storing data in Hadoop it is a common requirement to 
find a compact, structured representation of the data to store. Though human readable, xml files are not very compact. 
However when using any binary format, schema evolution commonly is a problem: Adding, renaming or deleting fields in 
most cases causes the need to upgrade all code interacting with the data as well as re-formatting already stored data. 
With Thrift, Avro and Protocol Buffers there are three options available for storing data in a compact, structured 
binary format. All three projects come with support for schema evolution by providing users no only to deal with 
missing data but also by providing a means to map old to new fields and vice versa.<br>
