---
title: "Devoxx University – MongoDB, Mahout"
date: 2010-12-05T21:19:39+01:00
tags: Mahout,mongodb,NOSQL,
---

# Devoxx University – MongoDB, Mahout


The second tutorial was given by Roger Bodamer on MongoDB. It concentrates on being horizontally scalable by avoiding 
joins and complex, multi document transactions. It supports a new data model that allows for flexible, changeable 
"schemas". <br><br>The exact data layout is determined by the types of operations you expect for your application, by 
the access patterns (reading vs. writing data; types of updates and types of queries). Also don't forget about indexing 
tables by columns to speed up frequently run queries. <br><br>Scaling MongoDB is supported by replication in a 
master/slave setup quite as any traditional system. In a replica set of n nodes, any of these can be elected as the 
primary (taking writes). If that one goes down, new master election happens. For durability all writes are required to 
go to at least a majority of all nodes, if that does not happen, now guarantee is given as to the availability of the 
update in case of primary failure. Write sharding comes with MongoDB as well.<br>Java support for Mongo is pretty 
standard - Raw Mongo driver comes in a Map<..., ... > flavour. Morphia supports Pojo mapping, annotations etc. for 
MongoDB Java integration, Code generators for various other JVM languages are available as well. <br><br>See also: <a 
href="http://blog.wordnik.com/12-months-with-mongodb">http://blog.wordnik.com/12-months-with-mongodb </a><br><br>My 
talk was scheduled for 30min in the afternoon. I went into some detail on what is necessary to build a news clustering 
system with Mahout and finished the presentation by a short overview of the other use cases that could be solved with 
the various algorithms. In the audience, nearly all had heard about Hadoop before – most likely in the introductory 
session that same morning. Same for Lucene. Solr was known to about half of the attendees. Mahout to just a few. 
Knowing that only very few attendees had any Machine Learning background I tried to provide a very high level overview 
of what can be done with the library, not going into too much mathematical details. There were quite a few interested 
questions after the presentation – both online and offline, including requests for examples on how to integrate the 
software with Solr. In addition connectors for instance to HBase as a data-source were interesting to people. 
Show-casing integration of Mahout, possibly even providing not only Java- but also REST interfaces might be one route 
to easier integration and faster adoption of Mahout.<br>
