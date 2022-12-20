---
title: "Lucene Meetup Oakland"
date: 2009-11-04T06:05:23+01:00
tags: [Lucene,Apache Con,ApacheConUS09,]
---

# Lucene Meetup Oakland


Though pretty late in the evening the room is packed with some 100 people. Most of them solr or pure lucene java users. 
There are quite a few Lucene committers at the meetup from all over the world. Several even have heard about Mahout - 
some even used it :)<br><br>Some introductiory questions to index sizes and query volumn:  1 Mio documents seem pretty 
standard for Lucene deployments - several people run 10 Mio neither. Some people even use indexes with up to billions 
of documents in Lucene - but at low query volumn. Usually people run projects with about 10 queries per second, but up 
to 500.<br><br>Eric's presentation gives a nice introduction to what is going on with Lucene/Solr in terms of user 
interfaces. He starts with an overview of the problems that libraries face when building search engines - especially 
the facetting side of life.  Especially interesting seem <a href="http://www.lucidimagination.com/">Solaritas</a> - a 
velocity response writer that makes it easy to render search responses not in xml but in simple templated output. He of 
course also included an overview of the features of <a 
href="http://www.lucidimagination.com/search/?q=mahout">LucidFind</a>, the Lucid hosted search engine for all Lucene 
projects and sub-projects. Take Home message: The interface is the application, as are the urls. Facets are not just 
for lists.<br><br>Second talk is given by Uwe giving an overview of the implementation of numeric searches and range 
queries and numeric range filters in Lucene.<br><br>Third presenter is Stefan on katta - a project on top of Lucene 
that adds index splits, load balancing, index replication, failover, distributed TFIDF. The mission of katta is to 
build a distributed Lucene for large indexes under high query load. The project heavily relies on zookeeper for 
coordination. It uses Hadoop IPC for search communication.<br><br>Lighting talks include talks by <br><ul><br><li><a 
href="http://codegoogle.com/p/zoie/wiki/ZoieSystem">Zoie</a>: A realtime search extension for Lucene, developed inside 
of LinkedIn and now open sourced at google code.<br><li>Jukka proposed a new project: A Lucene-based content mangement 
system.<br><li>Next presenter highlighted the problem of document-to-document search. The problem here is that queries 
are not just one or two terms but more like 40 terms.<br><li>Next talk shared some statistics: more than 2s at average 
leads to 40% abandonance rate for sites. The presenter is very interested in the Lucene Ajax project. Before using solr 
the speaker set up projects with solutions like Endeca or Mercato. Solr to him is an alternative that supports 
facetting.<br><li>Andzrej gives an overview of index pruning in 5min - giving details on which approaches are currently 
being discussed in research as well as in the Lucene jira for index pruning.<br><li>Next talk was on Lucy - a lucene 
port to C.<br><li>Last talk gave an overview of the findings on analysing the Lucene community.<br><li>One other 
lightning talk by a guy using and deploying Typo3 pages. Typo3 does come with an integrated search engine. The 
presenter's group built an <a href="http://www.typo3-solr.com/en/home/">extension</a> to Typo3 that integrates the CMS 
with Solr search. <br><li>The final last talk is done by Grant Ingersoll on Mahout. Thanks for 
that!<br></ul><br><br>Big Thanks to <a href="http://www.lucidimagination.com/">Lucid</a> for sponsoring the meetup.
