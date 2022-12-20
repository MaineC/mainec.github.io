---
title: "Notes on storage options - FOSDEM 05"
date: 2013-02-17T20:43:06+01:00
tags: Free Software,Hadoop,MySQL,hbase,Fosdem,Event,
---

# Notes on storage options - FOSDEM 05


<b>On MySQL</b><br><br>Second day at FOSDEM for me started with the MySQL dev room. One thing that made me smile was in 
the MySQL new features talk: The speaker announced support for “NoSQL interfaces” to MySQL. That is kind of fun in two 
dimensions: A) What he really means is support for the memcached interface. Given the vast number of different 
interfaces to databases today, announcing anything as “supports NoSQL interfaces” sounds kind of silly. B) Given the 
fact that many databases refrain from supporting SQL not because they think their interface is inferior to SQL but 
because they sacrifice SQL compliance for better performance, Hadoop integration, scaling properties or others this 
seems really kind of turning the world upside-down.<br><br>As for new features – the new MySQL release improved the 
query optimiser, subquery support. When it comes to replication there were improvements along the lines of performance 
(multi threaded slaves etc.), data integrity (replication check sums being computed, propagated and checked), agility 
(support for time delayed replication), failover and recovery.<br><br>There were improvements along the lines of 
performance schemata, security, workbench features. The goal is to be the go-to-database for small and growing 
businesses on the web.<br><br>After that I joined the systemd in Debian talk. Looking forward to systemd support in my 
next Debian version.<br><br><b>HBase optimisation notes</b><br><br>Lars George's talk on HBase performance notes was 
pretty much packed – like any other of the NoSQL (and really also the community/marketing and legal dev room) 
talks.<br><br><iframe src="http://www.slideshare.net/slideshow/embed_code/13564899" width="427" height="356" 
frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 
0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe> <div 
style="margin-bottom:5px"> <strong> <a href="http://www.slideshare.net/larsgeorge/hbase-sizing-notes" title="HBase 
Sizing Notes" target="_blank">HBase Sizing Notes</a> </strong> from <strong><a 
href="http://www.slideshare.net/larsgeorge" target="_blank">larsgeorge</a></strong> </div><br><br>Lars started by 
explaining that by default HBase is configured to reserve 40% of the JVM heap for in memory stores to speed up reading, 
20% for the blockcache used for writing and leaves the rest as breath area.<br><br>On read HBase will first locate the 
correct region server and route the request accordingly – this information is cached on the client side for faster 
access. Prefetching on boot-up is possible to save a few milliseconds on first requests. In order to touch as little 
files as possible when fetching bloomfilters and time ranges are used. In addition the block cache is queried to avoid 
going to disk entirely. A hint: Leave as much space as possible for the OS file cache for faster access. When 
monitoring reads make sure to check the metrics exported by HBase e.g. by tracking them over time in 
Ganglia.<br><br>The cluster size will determine your write performance: HBase files are so-called log structured merge 
trees. Writes are first stored in memory and in the so-called Write-Ahead-Log (WAL, stored and as a result replicated 
on HDFS). This information is flushed to disk periodically either when there are too many log files around or the 
system gets under memory pressure. WAL without pending edits are being discarded.<br><br>HBase files are written in an 
append-only fashion. Regular compactions make sure that deleted records are being deleted.<br><br>In general the WAL 
file size is configured to be 64 to 128 MB. In addition only 32 log files are permitted before a flush is forced. This 
can be too small a file size or number of log files in periods of high write request numbers and is detrimental in 
particular as writes sync across all stores, so large cells in one family will cause a lot of writes.<br><br>Bypassing 
the WAL is possible though not recommended as it is the only source for durability there is. It may make sense on 
derived columns that can easily be re-created in a co-processor on crash.<br><br>Too small WAL sizes can lead to 
compaction storms happening on your cluster: Many small files than have to be merged sequentially into one large file. 
Keep in mind that flushes happen across column families even if just one family triggers.<br><br>Some handy numbers to 
have when computing write performance of your cluster and sizing HBase configuration for your use case: HDFS has an 
expected 35 to 50 MB/s throughput. Given different cell size this is how that number translates to HBase write 
performance:<br><table><br><tr><td>Cell 
size</td><td>OPS</td></tr><br><tr><td>0.5MB</td><td>70-100</td></tr><br><tr><td>100kB</td><td>250-500</td></tr><br><tr><
td>10kB</td><td>with 800 less than expected as this HBase is not optimised for these 
sizes</td></tr><br><tr><td>1kB</td><td>6000, see above</td></tr><br></table><br><br>As a general rule of thumb: Have 
your memstore be driven by size number of regions and flush size. Have the number of allowed WAL logs before flush be 
driven by fill and flush rates.. The capacity of your cluster is driven by the JVM heap, region count and size, key 
distribution (check the talks on HBase schema design). There might be ways to get rid of the Java heap restriction 
through off-heap memory, however that is not yet implemented.<br><br>Keep enough and large enough WAL logs, do not 
oversubscribe the memstore space, keep the flush size in the right boundaries, check WAL usage on your cluster. Use 
Ganglia for cluster monitoring. Enable compression, tweak the compaction algorithm to peg background I/O, keep uneven 
families in separate tables, watch the metrics for blockcache and memstore.<br>
