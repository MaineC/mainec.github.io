---
title: "Elastic Search meetup Berlin"
date: 2012-11-28T00:39:01+01:00
tags: Lucene,elasticsearch,Get Together,
---

# Elastic Search meetup Berlin


Today <a href="http://www.retresco.de/">Retresco</a> hosted the (to my knowledge fourth) <a 
href="http://www.meetup.com/ElasticSearch-UG-Berlin/">Elastic Search User Group Berlin</a> - a group dedicated to using 
Lucene as part of Elastic Search. With roughly fifteen attendees the meetup attracted a decent crowd - most 
interestingly many of the people there were already using the software either in production or for closed beta 
projects.<br><br>The fist talk given was by people from <a href="http://www.ferret-go.com/">ferret-go</a> - a company 
doing media monitoring for brands focused on the German market. They are pretty new to the search topic, on top they 
aren't fluent Java developers but do most stuff in Python. Essentially their whole application is built on top of 
Elastic Search - most features are implemented as more or less complex search queries. In recent weeks they had to deal 
with typical problems related to growing data set sizes, nodes getting hot in particular when load balancing isn't 
configured quite right and balancing shards on a per index level instead of doing it globally for all shards 
(particularly bad in their case as they added an index with smaller shards and one with significantly larger shards 
into ES).<br><br>The second talk gave a really nice overview on <a 
href="http://asquera.de/opensource/2012/11/25/elasticsearch-pre-flight-checklist/">things to keep in mind before 
putting ES to production</a> - as is usually the case, the default configuration makes it easy to get started but most 
likely is not what you want in your production environment.<br><br>Really nice, technically focused event. Thanks to 
Retresco for hosting the meetup including beer and Club Mate and to <a 
href="http://www.elasticsearch.com/">ElasticSearch.com</a> for paying for the pizza. Check their meetup page for the 
next event - most likely to be scheduled in January.<br><br>Also if you'd like to learn more on Lucene 4 (talk by Simon 
Willnauer) - make sure to attend the <a href="https://www.xing.com/events/hadoop-get-together-1165460">Apache Hadoop 
Get Together December 2012</a> (if you need another ticket, it might make sense to politely ask the organiser, make 
sure you are registered, otherwise most likely you won't get through security). Other two talks scheduled:  Pere Urbon 
Bayes on NoSQL and Graph, a love story! as well as myself on How to Fail Your Big Data Project Quick and Rapidly.
