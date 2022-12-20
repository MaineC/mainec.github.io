---
title: "Large Scalability - Papers and implementations"
date: 2009-06-23T12:08:10+02:00
tags: search,Hacking,Free Software,Hadoop,Software Foundation,
---

# Large Scalability - Papers and implementations


In recent years the Googles and Amazons on this world have released papers on how to scale computing and processing to 
terrabytes of data. These publications have led to the implementation of various open source projects that benefit from 
that knowledge. However mapping the various open source projects to the original papers and assigning tasks that these 
projects solve is not always easy.<br><br>With no guarantee of completeness this lists provides a short mapping from 
open source project to publication.<br><br>There are <a 
href="http://www.metabrew.com/article/anti-rdbms-a-list-of-distributed-key-value-stores/">further</a> <a 
href="http://thinkvitamin.com/dev/should-you-go-beyond-relational-databases/">overviews</a> available online as well as 
a set of slides from the <a href="http://blog.oskarsson.nu/2009/06/nosql-debrief.html">NOSQL 
debrief</a>.<br><br><table><br><tr><br><td><a href="http://labs.google.com/papers/mapreduce.html">Map 
Reduce</a></td><br><td>Hadoop Core Map Reduce</td><td>Distributed programming on rails, <a 
href="http://www.cloudera.com/blog/2009/05/14/5-common-questions-about-hadoop/">5 Hadoop questions</a>, <a 
href="http://www.cloudera.com/blog/2009/05/18/10-mapreduce-tips/">10 Map Reduce Tips</a></td></tr><br><tr><td><a 
href="http://labs.google.com/papers/gfs.html">GFS</a></td><td>HDFS (Hadoop File System)</td><td>Distributed file system 
for unstructured data</td></tr><br><tr><td><a 
href="http://labs.google.com/papers/bigtable.html">Bigtable</a></td><td>HBase, Hypertable</a></td><td>Distributed 
storage for structured data, <a href="http://blog.rapleaf.com/dev/?p=26">When to use HBase.</td></tr><br><tr><td><a 
href="http://labs.google.com/papers/chubby.html">Chubby</a></td><td>Zookeeper</td><td>Distributed lock- and naming 
service</td></tr><br><tr><td><a href="http://labs.google.com/papers/sawzall.html">Sawzall</a></td><td>PIG, Cascading, 
JAQL, Hive</td><td>Higher level langage for writing map reduce jobs</td></tr><br><tr><td><a 
href="http://code.google.com/p/protobuf/">Protocol Buffers</a></td><td>Protocol Buffers, Thrift, Avro, more 
traditional: Hessian, Java serialization</td><td>Data serialization, <a 
href="http://blog.lucene.com/2009/05/12/some-early-avro-bencharks/">early benchmarks</a></td></tr><br><tr><td>Some 
NoSQL storage solutions</td><td>CouchDB, MongoDB</td><td>CouchDB: document database</td></tr><br><tr><td><a 
href="http://s3.amazonaws.com/AllThingsDistributed/sosp/amazon-dynamo-sosp2007.pdf">Dynamo</a></td><td>Dynomite, 
Voldemort, Cassandra</td><td>Distributed key-value stores</td></tr><br><tr><td>Index</td><td>Lucene</td><td>Search 
index</td></tr><br><tr><td>Index distribution</td><td>katta, Solr, nutch</td><td>Distributed Lucene 
indexes</td></tr><br><tr><td>Crawling</td><td>nutch, Heritrix, droids, Grub, Aperture</td><td>Crawling linked 
pages</td></tr><br></table><br><br><br>
