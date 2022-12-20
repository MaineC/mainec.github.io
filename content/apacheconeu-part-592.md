---
title: "ApacheConEU - part 05"
date: 2012-11-14T20:47:22+01:00
tags: [hbase,ApacheCon,Apache Con,Hadoop,apacheconeu,]
---

# ApacheConEU - part 05


The afternoon featured several talks on HBase - both it's implementation as well as schema optimisation. One major 
issue in schema design in the choice of key. Simplest recommendation is to make sure that keys are designed such that 
on reading data load will be evenly distributed accross all nodes to prevent region-server hot-spotting. General advise 
here are hashing or reversing urls.<br><br>When it comes to running your own HBase cluster make sure you know what is 
going on in the cluster at any point in time:<br><ul><br><li>Hbase comes with tools for checking and fixing 
tables,<br><li>tools for inspecting hfiles that HBase stores data in,<br><li>commands for inspecting the binary write 
ahead log,<br><li>web interfaces for master and region servers,<br><li>offline meta data repair 
tooling.<br></ul><br><br>When it comes to system monitoring make sure to track cluster behaviour over time e.g. by 
using Ganglia or OpenTSDB and configure your alerts accordingly.<br><br>One tip for high traffic sites - it might make 
sense to disable automatic splitting to avoid splits during peaks and rather postpone them to low traffic times. One 
rather new project presented to monitor region sizes was Hannibal.<br><br>At the end of his talk the speaker went into 
some more detail on problems encountered when rolling out HBase and lessons learnt:<br><ul><br><li>the topic itself was 
new so both engineering and ops were learning.<br><li>at scale nothing that was tested on small scale works as 
advertised.<br><li>hardware issues will occur, tuning the configuration to your workload is crucial.<br><li>they used 
early versions - inevitably leading to stability issues.<br><li>it's crucial to know that something bad is building up 
before all systems start catching fire - monitoring and alerting the right thing is important. With Hadoop there are 
multiple levels to monitor: the hardware, os, jvm, Hadoop itself, HBase on top. It's important to correlate the 
metrics.<br><li>key- and schema design are key.<br><li>monitoring and knowledgable operations are 
important.<br><li>there are no emergency actions - in case of an emergency it just will take time to recover: Even if 
there is a backup, even just transferring the data back can take hours and days.<br><li>HBase (and Hadoop) is DevOps 
technology.<br><li>there is a huge learning curve to get to a state that makes using these systems 
easy.<br></ul><br><br><br>In his talk on HBase schema design Lars George started out with an introduction to the HBase 
architecture. On the logical level it's best to think of HBase as a large distributed hash table - all data except for 
names are stored as byte arrays (with helpers to transform that data back into well known data types provided). The 
tables themselves are stored in a sparse format which means that null values essentially come for free.<br><br>On a 
more technical level the project uses zookeeper for master election, split tracking and state tracking. The 
architecture itself is based on log structured merge trees. All data initially ends up in the write ahead log - with 
data always being appended to the end this log can be written and ready very efficiently without any seek penalty. The 
data is inserted at the respected region server in memory (mem store, size of 64 MB typically) and synched to disk in 
regular intervals. In HBase all files are immutable - modifications are done only by writing new data and merging it in 
later. Deletes also happen by marking data as deleted instead of really deleting it. On a minor compaction the recently 
few files are being merged. On a major compaction all files are merged and deletes are being handled. Handling your own 
major compaction is possible as well. <br><br>In terms of performance lookup by key is the best you can do. If you do 
lookup by value this will result in a full-table scan. There is an option to give HBase a hint as to where to find the 
key when it is updated only infrequently - there is an option to provide a timestamp of roughly where to look for it. 
Also there are options to use Bloomfilters for better read performance. Another option is to move more data into the 
row key itself if that is the data you will be searching for very often. Make sure to de-normalize your data as HBase 
does not do any sophisticated joins, there will be duplication in your data as all should be pre-joined to get better 
performance. Have intelligent keys that make match your read/write patterns. Also make sure to keep your keys 
reasonably short as they are being repeated for each entry - so moving the whole data into the key isn't going to get 
you anything.<br><br>Speaking of read write patterns - as a general rule of thumb: to optimise for better write 
performance tune the memstore size. For better read performance tune the block cache size. One final hint: Anything 
below 8 servers really is just a test setup as it doesn't get you any real advantages.
