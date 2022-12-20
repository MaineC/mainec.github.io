---
title: "GeeCon - Solr at Allegro"
date: 2012-05-25T08:07:06+02:00
tags: [Lucene,geecon,Solr,]
---

# GeeCon - Solr at Allegro


One particularly interesting to me was on Allegro's (polish Ebay) Solr usage. In terms of numbers: They have 20Mio 
offers in Poland, another 10Mio active offers in partnering countries. In addition in their index there are 50Mio 
inactive offers in Poland and 40 Mio closed offers outside that country. They serve 8Mio updates a day, that is 100 
updates a second. Those are related to start/end of bidding phase, buy now actions, cancelled bids, bids 
themselves.<br><br>Per day they have 105Mio requests per day, on peak time in the evening that is 3.5k requests per 
second. Of those 75% are answered in less than 5ms, 90% in less than 20ms.<br><br>To achieve that performance they are 
using Solr. Coming from a database based system, going via a proprietary search product they are now happy users of 
Solr with much better customer support both from the community as well as from contractors than with their previous 
paid for solution.<br><br>The speakers went into some detail on how they solved particular technical issues: They had 
to decide to go for an external data feeder to avoid putting the database itself under too much load even when just 
indexing the updates. On updates they need to deal with having to reconstruct the whole document as updates for Solr 
right now mean deleting the old document and indexing the new one. In addition commits are pretty expensive, so they 
ended up delaying commits for as long as the SLA would allow (one minute) and committing them as batch.<br><br>They 
tried to shard indexes by category facetted by – that did not work particularly wrong as with their user behaviour it 
resulted in too many cross-shard requests. Index size was an issue for them so they reduced the amount of data indexed 
and stored in Solr to the absolute minimum – all else was out-sourced to a key-value store (in their case 
MongoDB).<br><br>When it comes to caching that proved to be the component that needed most tweaks – they put a varnish 
in front (Solr speaks xml over http which is simple enough to find caches for) – in relation with the index delay they 
had in place they could tune eviction times. Result were cache hit rates of about 30 to 40 percent. When it comes to 
internal caches: High eviction and low hit rates are a problem. Watch the Solr Admin Console for more statistics. Are 
there too many unique objects in your index? Are caches too small? Are there too many unique queries? They ended up 
binding users to solr backends by having a routing be sticky with the user's cookie – as users tend to drill down on 
the same dataset over and over again in their case that raised hit rates substancially. When tuning filter queries: 
Have them as independent as possible – don't use many unique combinations of the same filtering over and over again. 
Instead filter individually to better use that cache.<br><br>For them Solr proved to be  a stable, efficient, flexible, 
easy to monitor and maintain and change system that ran without failure for the first 8 months with the whole 
architecture being designed and prototyped (at near production quality) by one developer in six 
months.<br><br>Currently the system is running on 10 solr slaves (+ power backup) compared to 25 nodes before. A full 
index takes 4 hours, bottlenecked at the feeder, potentially that could be pushed down to one hour. Updates of course 
flow in continuously.<br>
