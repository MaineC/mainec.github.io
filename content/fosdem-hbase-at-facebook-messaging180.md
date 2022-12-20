---
title: "FOSDEM - HBase at Facebook Messaging"
date: 2011-02-17T20:17:48+01:00
tags: Apache Hadoop,Apache HBase,General,hbase,Brussels,Fosdem,
---

# FOSDEM - HBase at Facebook Messaging


<p>Nicolas Spiegelberg gave an awesome introduction not only to the architecture that powers Facebook messaging but 
also to the design decisions behind their use of Apache HBase as a storage backend. Disclaimer: HBase is being used for 
message storage, for attachements with Haystack a different backend is used.</p><p>The reasons to go for HBase include 
its strong consistency model, support for auto failover, load balancing of shards, support for compression, atomic 
read-modify-write support and the inherent Map/Reduce support.</p><p>When going from MySQL to HBase some technological 
problems had to be solved: Coming from MySQL basically all data was normalised - so in an ideal world, migration would 
have involved one large join to port all the data over to HBase. As this is not feasable in a production environment 
instead what was done was to load all data into an intermediary HBase table, join the data via Map/Reduce and import 
all into the target HBase instance. The whole setup was run in a dark launch - being fed with parallel life traffic for 
performance optimisation and measurement.</p><p>The goald was zero data loss in HBase - which meant using the Apache 
Hadoop append branch of HDFS. The re-designed the HBase master in the process to avoid having a single point of 
failure, backup masters are handled by zookeeper. Lots of bug fixes went back from Facebooks engineers to the HBase 
code base. In addition for stability reason rolling restarts were added for upgrades, performance improvements, 
consistency checks.</p><p>The Apache HBase community received lots of love from Facebook for their willingness to work 
together with the Facebook team on better stability and performance. Work on improvements was shared between teams in 
an amazing open and inclusive model to development.</p><br><p>One additional hint: <a 
href="http://video.fosdem.org/2011/">FOSDEM videos</a> of all talks including this one have been put online in the 
meantime.</p>
