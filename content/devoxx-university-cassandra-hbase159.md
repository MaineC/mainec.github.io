---
title: "Devoxx – University – Cassandra, HBase  "
date: 2010-12-06T21:20:56+01:00
tags: [hbase,Cassandra,Devoxx,NOSQL,General,]
---

# Devoxx – University – Cassandra, HBase  


During the morning session FIXME Ellison gave an introduction to the distributed NoSQL database Cassandra. Being 
generally based on the Dynamo paper from Amazon the key-value store distributes key/value pairs according to a 
consistent hashing schema. Nodes can be added dynamically making the system well suited for elastic scaling. In 
contrast to Dynamo, Cassandra can be tuned for the required consistency level. The system is tuned for storing 
moderately sized key/value pairs. Large blobs of data should not be stored into it. A recent addition to Cassandra has 
been the integration with Hadoop's Map/Reduce implementation for data processing. In addition Cassandra comes with a 
Thrift interface as well as higher level interfaces such as Hector.<br><br>In the afternoon Michael Stack and Jonathan 
Grey gave an overview of HBase covering basic installation, going into more detail concerning the APIs. Most 
interesting to me was the HBase architecture and optimisation details. The systems is inspired by Google's BigTable 
paper. It uses Apache HDFS as storage back-end inheriting the failure resilience of HDFS. The system uses Zookeeper for 
co-ordination and meta-data storage. However fear not, Zookeeper comes packaged with HBase, so in case you have not yet 
setup your own Zookeeper installation, HBase will do that for you on installation.<br><br>HBase is split into a master 
server for holding meta-data and region servers for storing the actual data. When storing data HBase optimises storage 
for data locality. This is done in two ways: On write the first copy usually goes to the local disk of the client, so 
even when storage exceeds the size of one block and remote copies get replicated to differing nodes, at least the first 
copy gets stored on one machine only. During a compaction phase that is scheduled regularly (usually every 24h, jitter 
time can be added to lower the load on the cluster) data is re-shuffled for optimal layout. When running Map/Reduce 
jobs against HBase this data locality can be easily exploited. HBase comes with its own input and output formats for 
Hadoop jobs.<br><br>HBase comes not only with Map/Reduce integration, it also publishes a Thrift interface, a REST 
interface and can be queried from an HBase shell.<br>
