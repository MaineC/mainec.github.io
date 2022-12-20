---
title: "Hadoop User Group UK"
date: 2009-04-21T20:34:15+02:00
tags: [Mahout,Hadoop,Software Foundation,]
---

# Hadoop User Group UK


On Tuesday the 14th the second <a href="http://huguk.org/">Hadoop User Group UK</a> took place in London. This time 
venue and pizza was sponsored by Sun. The room quickly filled 
http://www.thecepblog.com/2009/04/19/kmeans-clustering-now-running-on-elastic-mapreduce/with approximately 70 
people.<br><br>Tom opened the session with a talk on 10 practical tips on how to get the most benefit from Apache 
Hadoop. The first question users should ask themselves is which type of programming language they want to use. There is 
a choice between structured data processing languages (PIG or Hive), dynamic languages (Streaming or Dumbo), or using 
Java which is closest to the system.<br><br>Tom's second hint dealt with the size of files to process with Hadoop: Both 
- too large unsplittable and too small ones are bad for performance. In the first case, the workload cannot be easily 
distributed across the nodes in the latter case each unit of work is to small to account for startup and coordination 
overhead. There are ways to remedy these problems with sequence files and map files though. Another performance 
optimization would be to chain individual jobs - PIG and Hive do a pretty decent job in automatically generating such 
jobs. ChainMapper and ChainReducer can help with creating chained jobs.<br><br>Another important task when implementing 
map reduce jobs is to tell Hadoop the progress of your job. For once, this is important for long running jobs in order 
for them to remain alive and not be killed by the framework due to timeouts. Second, it is convenient for the user as 
he can view the progress in the web UI of Hadoop.<br><br>Usual suspects for tuning a job: Number of mappers and 
reducers, usage of combiners, compression customised data serialisation, shuffling tweaks. Of course there is always 
the option to let someone else do the tuning: Cloudera does provide support as well as pre-built packages init scripts 
and the like ;)<br><br>In the second talk I did a brief Mahout intro. It was surprising to me that half of the 
attendees already employed machine learning algorithm implementations in their daily work. Judging from the discussion 
after the talk and from questions I received after it the interest in the project seems pretty high. The slide I liked 
the most: The announcement of our first 0.1 release. Thanks to all Mahout committers and contributors who made this 
possible.<br><br>After the coffee break Craig  gave an introduction to Terrier an extensible information retrieval 
plattform developed at the university of Glasgow. He mentioned a few other open IR platforms namely Tuple Flow, 
Zettair, Lemur/Indri, Xapian, as well as of course nutch/Solr/Lucene.<br><br>What does Terrier have to do with the 
HugUK? Well index creation in Terrier is now based on an implementation that makes use of Hadoop for parallelization. 
Craig did some very interesting analysis on scalability of the solution: The team was able to achieve scaling near 
linear in the number of nodes added (at least as long as more than reducer is used ;) ).<br><br>After the pizza Paolo 
described his experiences implementing the vanilla pagerank computation with Hadoop. One of his test datasets was the 
Citeseer citation graph. Interestingly enough: Some of the nodes in this graph have self references (maybe due to 
extraction problems), duplicate citations, and the data comes in an invalid xml format.<br><br>The last talk was on 
HBase by Michael Stack. I am really happy I attended HugUK as I missed that talk in Amsterdam at the ApacheCon. First 
Michael gave an overview of which features of a typical RDBMS are not supported by HBase: Relations, joins, and of 
course JDBC being among the limitations. On the pro site HBase offers a multiple node solutions that has scale out and 
replication built in.<br><br>HBase can be used as source as well as as sink for map reduce jobs and thus integrates 
nicely with the Apache Hadoop stack. The framework provides a simple shell for administrative tasks (surgery on sick 
clusters forced flushes non sql get scan and put methods). In addition the master comes with a UI to monitor the 
cluster state.<br><br>Your typical DBA work though differs with HBase: Data locality and physical layout do matter and 
can be configured. Michaels recommendation was to start out testing with the XL instance on EC2 and decrease instances 
if you find out that it is too large.<br><br>The talk finished with an outlook of the features in the upcoming release 
the issues on the todo list and an overview of companies already using HBase. <br><br>After talks were finished quite a 
few attendees went over to a pub close by: Drinking beer, discussing new directions and sharing war stories.<br><br>I 
would to thank <a href="http://blog.oskarsson.nu/">Johan Oskarsson</a> for organising the event. And a special thanks 
to Tom for letting me use his Laptop for the Apache Mahout presentation: the hard disk of mine broke exactly one day 
before.<br><br>Last but not least thank you to Sylvio and Susi for letting me stay at their place - and thanks to 
Helene for crying only during daytime when I was out anyway ;)<br><br>Hope to see at least some of the attendees again 
at the next Hadoop Meetup in Berlin. Looking forward to the next Hadoop User Group UK.
