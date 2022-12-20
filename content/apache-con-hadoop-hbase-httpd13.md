---
title: "Apache Con – Hadoop, HBase, Httpd"
date: 2010-11-24T23:19:10+01:00
tags: [Httpd,ApacheCon,Hadoop,Atlanta,Apache Con,hbase,]
---

# Apache Con – Hadoop, HBase, Httpd


The first Apache Con day featured several presentations on NoSQL databases (track sponsored by Day software), a Hadoop 
track as well as presentations on Httpd and an Open source business track. <br><br>Since its inception Hadoop always 
was intended to be run in trusted environments firewalled from hostile users or even attackers. As such it never really 
supported any security features. This is about the change with the new Hadoop release including better Kerberos based 
security.<br><br>When creating files in Hadoop a long awaited feature was append support. Basically up to now writing 
to Hadoop was a one-of job: Open a file, write your data, close it and be done. Re-opening and appending data was not 
possible. This situation is especially bad for HBase as its design relies on being able to append data to an existing 
file. There have been efforts for adding append support to HDFS earlier as well as an integration of such patches by 
third party vendors. However only with a current Hadoop version Append is officially supported by HDFS.<br><br>A very 
interesting use case-wise of the Hadoop stack was presented by $name-here from $name. They are using a Hadoop cluster 
to provide a repository of code released under free software licenses. The business case is to enable corporations to 
check their source code against existing code and spot license infringements. This does not only include linking to 
free software under incompatible licenses but also developers copying pieces of free code, e.g. copying entire classes 
or functions into internal projects that originally were available only under copyleft licenses.<br><br>The speaker 
went into some detail explaining the initial problems they had run into: Obviously it's no good idea to mix and match 
Hadoop and HBase versions freely. Instead it is best practice to use only versions claimed to be compatible by the 
developers. Another common mistake is to leave parameters of both projects at their defaults. The default parameters 
are supposed to be fool-proof. However they are optimised to work well for Hadoop newbies who want to try out the 
system on a single node cluster and in a distributed setting obviously need more attention. Other anti-patterns include 
storing only tiny little files in the cluster thus quickly running out of memory on the namenode (that stores all file 
information including block mappings in main memory for faster access).<br><br>In the NoSQL track Jonathan Grey from 
Facebook gave a very interesting overview on the current state of HBase. Turns out that Facebook would announce only a 
few days after that their internal use of HBase for the newly launched feature of Facebook messaging.<br><br>HBase has 
adopted a release cycle including development/ production releases to get their systems into interested users' hands 
more quickly: Users willing to try out new experimental features can use the development releases of HBase. Those who 
are not should go for the stable releases.<br><br>After focussing on improving performance in the past months the 
project is currently focussing on stability: Data loss is to be avoided by all means. Zookeeper is to be integrated 
more tightly for storing configuration information thus enabling live reconfiguration (at least to some extend). In 
addition also HBase is targeting to integrate stored procedures like behaviour: As explained in Googles Percolator 
paper $LINK batch oriented processing get's you only so far. If data that gets added constantly it makes sense to give 
up on some of the throughput batch-based systems provide and instead optimise for shorter processing cycles by 
implementing event triggered processing.<br><br>On recommendation of one of neofonie's sys-ops I visited some of the 
httpd talks: First Rich Bowen gave an overview of unusual tasks one can solve with httpd. The list included things like 
automatically re-writing http response content to match your application. There is even a spell checker for request 
URLs: Given marketing has given your flyer to the press with a typo in the url, chances are that the spellchecking 
module can fix these automatically for each request: Common mistakes covered are switched letters, numbers replaced by 
letters etc. The performance cost has to be paid only in case no hit could be found – so instead of returning a 404 
right away the server first tries to find the document by taking into account common mis-spellings.
