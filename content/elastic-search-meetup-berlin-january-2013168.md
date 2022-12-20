---
title: "Elastic Search meetup Berlin – January 2013"
date: 2013-02-01T18:34:17+01:00
tags: [Lucene,tfidf,Free Software,elastic search,]
---

# Elastic Search meetup Berlin – January 2013


The first meetup this year I went to started with a large bag of good news for Elastic Search users. In the offices of 
Sys Eleven (thanks for hosting) the meetup started at 7p.m. last Tuesday. Simon Willnauer gave <a 
href="https://speakerdeck.com/simonw/elasticsearch-usergroup-berlin-meetup">an overview of what to expect of the 
upcoming major release of Elastic Search</a>:<br><br>For all 0.20.x version ES features a shard allocator version that 
is ignorant of which index shards belong to, machine properties, usage patterns. Especially ignoring index information 
can be detrimental and lead to having all shards of one index on one machine in the end leading to hot spots in your 
cluster. Today this is solved by lots of manual intervention or even using custom shard allocator 
implementations.<br><br>With the new release there will be an EvenShardCountAllocator that allows for balancing shards 
of indexes on machines – by default it will behave like the old allocator but can be configured to take weighted 
factors into account. The implementation will start with basic properties like “which index does this shard belong to” 
but the goal is to also make variables like remaining disk space available. To avoid constant re-allocation there is a 
threshold on the delta that has to be passed for re-allocation to kick in.<br><br>0.21 will be released when Lucene 4.1 
is integrated. That will bring new codecs, concurrent flushing (to avoid the stop-the-world flush during indexing that 
is used in anything below Lucene 4 – hint: Give less memory to your JVM in order to cause more frequent flushes), there 
will be compressed sort fields, spellchecking and suggest built into the search request (though unigram only). There 
will be one similarity configurable per field – that means you can switch from TF-IDF to alternative built-in scoring 
models or even build your own. <br><br>Speaking of rolling your own: There is a new interface for FieldData (used for 
faceting, scoring and sorting) to allow for specialised data structures and implementations per field. Also the default 
implementation will be much more memory efficient for most scenarios be using UTF-8 instead of UTF-16 
characters).<br><br>As for GeoSpatial: The code came to Lucene as a code dump that the contributor wasn't willing to 
support or maintain. It was replaced by an implementation that wasn't that much better. However the community is about 
to take up the mess and turn it into something better.<br><br>After the talk the session essentially changed to an 
“interactive mailing list” setup where people would ask questions live and get answers both from other users as well as 
the developers. Some example was the question for recommendability of pyes as a library. Most people had used it, many 
ran into issues when trying to run an upgrade with features being taken away or behaviour being changed without much 
notice. There are plans to release Perl, Ruby and Python clients. However also using JRuby, Groovy, Scala or Clojure to 
communicate with ES works well.<br><br>On the benefit of joining the cluster for requests: That safes one hop for 
routing, result merging, is an option to have  a master w/o data and helps with indexing as the data doesn't go through 
an additional node. <br><br>As for plugins the next thing needed is an upgrade and versioning schema. Concerning plugin 
reloading without restarting the cluster there was not much ambition to get that into the project from the ES side of 
things – there is just too much hazzle when it comes to loading and unloading classes with references still hanging 
around to make that worthwhile.<br><br>Speaking of clients: When writing your own don't rely on the binary protocol. 
This is  a private interface that can be subject to change at any time.<br><br>When dealing with AWS: The S3 gateway is 
not recommended to be used as it is way too slow (and as a result very expensive). Rather backup with replicas, keep 
the data around for backup or use rsync. When trying to backup across regions this is nothing that ES will help you 
with directly – rather send your data to both sites and index locally. One recommendation that came from the audience 
was to not try and use EBS as the IO optimised versions are just too expensive – it's much more cost effective to rely 
on ephermeral storage. Another thing to checkout is the support for ES being zone aware to avoid having all shards in 
one availability zone. Also the node discovery timeout should be increased to at least one minute to work in AWS. When 
it comes to hosted solutions like heroko you usually are too limited in what you can do with these offers compared to 
the low maintenance overhead of running your own cluster. Oh, and don't even think about index encryption if you want 
to have a fast index without spending hours and hours of development time on speeding your solution up with custom 
codecs and the like :)<br><br>Looking forward to the <a href="http://www.meetup.com/ElasticSearch-UG-Berlin/">Elastic 
Search next meetup</a> end of February – location still to be announced. It's always interesting to see such meetup 
groups grow (this time from roughly 15 in November to over 30 in January).<br><br>PS: A final shout-out to <a 
href="http://people.apache.org/~hossman/">Hossman</a> - that psychological trick you played on my at <a 
href="http://people.apache.org/~hossman/ac2012eu/">your boosting and biasing talk</a> at Apache Con EU is slightly 
annoying: Everytime someone mentions TF-IDF in a talk (and that isn't too unlikely in any Lucene, Solr, Elastic Search 
talks) I panicingly double check whether there are funny pictures on the slide shown! ;) <br>
