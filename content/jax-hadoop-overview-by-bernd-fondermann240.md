---
title: "JAX: Hadoop overview by Bernd Fondermann"
date: 2013-05-18T20:29:57+02:00
tags: BigDataCon,Hadoop,JAX,Event,
---

# JAX: Hadoop overview by Bernd Fondermann


<P><br>After breakfast was over the first day started with a talk by Bernd on the<br>Hadoop ecosystem. He did a good 
job selecting the most important and<br>interesting projects related to storing data in HDFS and processing it with 
Map<br>Reduce. After the usual "what is Hadoop", "what does the general architecture<br>look like", "what will change 
with YARN" Bernd gave a nice overview of which<br>publications each of the relevant projects rely 
on:<br><br><P><br><br><UL><br><LI>HDFS is mainly based on the paper on GFS.<br></LI><br><LI>Map Reduce comes with it's 
own publication.<br></LI><br><LI>The big table paper mainly inspired Cassandra (to some extend), HBase,<br>Accumulo and 
Hypertable.<br></LI><br><LI>Protocol Buffers inspired Avro and Thrift, and is available as free<br>software 
itself.<br></LI><br><LI>Dremel (the storage side of things) inspired Parquet.<br></LI><br><LI>The query language side 
of Dremel inspired Drill and Impala.<br></LI><br><LI>Power Drill might inspire Drill.<br></LI><br><LI>Pregel (a graph 
database) inspired Giraph.<br></LI><br><LI>Percolator provided some inspiration to HBase.<br></LI><br><LI>Dynamo by 
Amazon kicked of Cassandra and others.<br></LI><br><LI>Chubby inspired Zookeeper, both are based on 
Paxos.<br></LI><br><LI>On top of Map Reduce today there are tons of higher level languages,<br>starting with Sawzall 
inside of Google, continuing with Pig and Hive at Apache<br>we are now left with added languages like Cascading, 
Cascalog, Scalding and<br>many more.<br></LI><br><LI>There are many other interesting publications (Megastore, Spanner, 
F1 to<br>name just a few) for which there is no free implementation yet. In addition<br>with Storm, Hana and Haystack 
there are implementations lacking canonical<br>publications.<br></LI><br></UL><br><P><br>After this really broad 
clarification of names and terms used, Bernd went into<br>some more detail on how Zookeeper is being used for defining 
the namenode in<br>Hadoop 2, how high availablility and federation works for namenodes. In<br>addition he gave a clear 
explanation of how block reports work on cluster<br>bootup. The remainder of the talk was reserved for giving an intro 
to HBase,<br>Giraph and Drill.<br>
