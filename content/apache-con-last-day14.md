---
title: "Apache Con – last day"
date: 2010-11-27T23:23:30+01:00
tags: [Solr,ApacheCon,Apache Con,fast,MySQL,]
---

# Apache Con – last day


Day three of Apache Con started with interesting talks on Tomcat 7, including an introduction to the new features of 
that release. Those include better memory leak prevention and detection capabilities – the implementation of these 
capabilities have lead to the discovery of various leaks that appear under more or less weird circumstances in famous 
open source libraries and the JVM itself. But also better management and reporting facilities are part of the new 
release.<br><br>As I started the third day over at the Tomcat track, unfortunately I missed the Tika and Nutch 
presentations by Chris Mattman – so happy, that at least the slides were published online: $LINK. The development of 
nutch was especially interesting for me as that was the first Apache project I got involved with back in 2004. Nutch 
started out as a project with the goal of providing an open source alternative internet-scale search engine. Based on 
Lucene as a indexer kernel, it also providing crawling, content extraction and link analysis.<br><br>Focussed on 
building an internet scale search engine the need for a distributed processing environment quickly became apparent. 
Initial implementations of a nutch distributed file system and a map reduce engine lead to the creation of the Apache 
Hadoop project.<br><br>In recent years it was comparably quiet around nutch. Besides Hadoop also content extraction was 
factored out of the project into Apache Tika. At the moment development is getting more momentum again. Future 
developments are supposed to be focussed on building an efficient crawling engine. As storage backend the project wants 
to leverage Apache HBase, for content extraction Tika is to be used, as indexing backend Solr. <br><br>I loved the 
presentation by Geoffrey Young on how they used Solr to replace their old MySQL search based system for better 
performance and more features at Ticketmaster. Indexing documents representing music CDs presents some special 
challenges when it comes to domain modeling: There are bands with names like “!!!”. In addition users are very likely 
to misspell certain artists names. In contrast to large search providers like Google these businesses usually have 
neither human resources nor enough log data to provide comparable coverage e.g. when implementing spell-checking. A 
very promising and agile approach taking instead was to parse log files for most common failing queries and from that 
learn more about features needed by users: There were many queries including geo information coming from users looking 
for an event at one specific location. As a result geo information was added to the index leading to happier users.
