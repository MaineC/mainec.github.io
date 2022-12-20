---
title: "NoSQL Berlin Meetup"
date: 2009-10-23T13:24:26+02:00
tags: [Camp,NoSQL Berlin,]
---

# NoSQL Berlin Meetup


Yesterday evening the NoSQL Berlin Meetup took place in newthinking store, Berlin Mitte. We had planned for some 50 to 
70 people. It quickly became clear that the room would be full - at startup I counted about 80 guests interested in 
NoSQL topics both locally from Berlin but also traveling here from New York.<br><br>Some pictures are available on <a 
href="http://www.flickr.com/photos/langalex/sets/72157622644603890/with/4037001022/">flickr</a> - thanks to @langalex 
for sending the url to me:<br><br>The meetup started with an introduction to basic principles on consistancy and 
agreement protocols that are the basis of many scalable storage solutions, including Scalaris. Monika Moser explained, 
why one can have only two of the three goals of consistency, availability and partition tolerance. After that she gave 
an introduction to Paxos - a scalable, partition tolerant agreement protocol.<br><br><img 
src="http://farm3.static.flickr.com/2751/4036248043_5cbd845cc1.jpg"><br><br>In the second talk, Mathias Meyer 
introduced Redis - a wicket fast key value store that supports strings, lists and sets as values. It is implemented in 
C, comes with a persistence mechanism. Only problem: All the data stored in Redis needs to fit in memory for this store 
to work.<br><br>After a short break Jan Lehnardt gave an overview of building P2P applications with CouchDB. He showed 
how CouchDB can be scaled to large deployments with modules that build distribution and sharding on top of CouchDB. But 
CouchDB can also be scaled down to run on mobile devices. As synchronization is so simple with that DB it is a perfect 
fit for Ubuntu One - the initiative of Canonical that brings a personal cloud to everyone for sharing and distributing 
your data.<br><br>Martin Scholl gave an overview of Riak - a highly distributed key-value store with support for 
map-reduce style queries, sharding of data and a rest-Interface.<br><br>The last session included a talk by Mathias 
Stearn on MongoDB - a key-value store that does not come with json formatted documents but uses bson for document 
encoding. This makes it easy to support for compact and fast object (de-)serialization.<br><br>The final talk was given 
by Prof. Stefan Edlich on object oriented databases.<br><br>After the event, speakers and attendees switched over to 
Cafe Aufsturz for some drinks, beer and food - and of course for further discussions.<br><br>Big thanks goes to the 
sponsors (Versant, Peritor (drinks at newthinking), StudiVZ (videos), Sociomantic (drinks at Aufsturz), Soundcloud 
(food at Aufsturz). Another big thanks to Jan Lehnardt and Thomas Nicolai for helping me set up this 
event.<br><br>Looking forward to seeing you guys either in Oakland this November or probably next year at the next 
NoSQL conference in Berlin.
