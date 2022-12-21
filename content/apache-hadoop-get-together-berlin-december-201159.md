---
title: "Apache Hadoop Get Together Berlin December 2011"
date: 2011-12-08T01:50:26+01:00
tags: [GetTogether,Hadoop,Get Together,triposo,]
---

# Apache Hadoop Get Together Berlin December 2011


First of all a huge Thank You to David Obermann for organising today's Apache Hadoop Get Together Berlin: After a 
successful Berlin Buzzwords and a rather long pause following that finally a Christmas meetup took place today at 
Smarthouse, kindly sponsored by Axel Springer and organised by David Obermann from idealo. About 40 guests from 
Neofonie, Nokia, Amen, StudiVZ, Gameduell, TU Berlin, nurago, Soundcloud, nugg.ad and many others made it to the 
event.<br><br><img src="/hadoop_201112.jpg"/><br><br>In the first presentation 
Douwe Osinga from <a href="http://www.triposo.com/">triposo</a> went into some details on what Triposo is all about, 
how development for it differs in terms of scope and focus at larger corporations and what patterns they use for 
getting the data crawled, cleaned and served to users.<br><br>The goal of Triposo is to be able to build travel guides 
in a fully automated way. In contrast to simply creating a catalog of places to go to the goal is to have an 
application that is competitive to Lonely Planet books: Have tours, detailed background information, recommend places 
to visit based on wheather and seasonal signals, allow users to create travel books.<br><br>Joining Triposo from 
Google, Douwe gave a rather interesting perspective on what makes a startup interesting for innovative ideas. There are 
four interesting aspects of application development that according to his talk matter for Google projects: First is 
embracing failure. Not only can single hard disks fail, but servers might be switched off automatically for 
maintenance, even entire datacenters going offline must not affect your application. Second is a strong focus on speed: 
Developers working with dynamic languages like Python that allow for rapid prototyping at the expense of slower runtime 
are generally frowned upon. Third building block is the focus on search that is ingrained in every piece of 
architecture and thinking. Fourth and last is a strong mentality to build your own which may lead to great software but 
leaves software developers in an isolated island of proprietary software that can limit but at least shapes your way of 
thinking.<br><br>He gave Youtube as an example: Though built on top of MySQL, implemented in Python and certainly not 
failure proof in every aspect they succeeded by concentrating on users' needs, time to market and iteratively improving 
their software with a frequent (as in one week) develop-release-deploy cycle. When entering new markets and providing 
innovative applications it often is crucial to be able to move quickly at the expense of speed and stability. It 
certainly is important to consider different architectures and chose the one that is appropriate to solve the problem 
at hand. Same reasoning applies for Apache Hadoop as well: Do not try to solve problems with it that it is not made to 
solve. Instead first think what is the right tool for your job.<br><br>Triposo itself is built on top of 12 data 
sources. Most are freely available, integrated to build a usable and valuable travel guide application for iOS and 
Android. The features available in Triposo can be phrased in terms of a search and information retrieval problem 
setting and as such lend itself well for integrated sources. With offers from Amazon, Google itself, Dropbox and the 
like it has become easy to deploy applications in an elastic way and scale with your user base and demand for more 
country coverage. For them it proved advantages to go for an implementation based on dynamic languages for pure 
development speed. <br><br>When it comes to QA they take a semi-manual approach: There are scripts checking recall 
(Brandenburger Tor must be found for the Berlin guide) as well as precision (there must be only one Brandenburger Tor 
in Berlin). Those rules need to be manually tuned.<br><br>When integrating different sources you quickly run into a 
duplicate discovery problem. Their approach is pretty pragmatic: Merge anything that you are confident enough to say it 
is a duplicate. Kill everything that is likely a duplicate but you are not confident enough to merge. The general 
guideline is to rather miss a place than have it twice.<br><br>For the wikipedia source so far they are only parsing 
the English version. There are plans to also support other languages - in particular for parsing to increase data 
quality as e.g. for some places geo coordinates may be available in the German article but not in the English one. 
<br><br>Though not going into too many technical details the talk gave some nice insights as to the strengths and 
weaknesses of different company sizes and mindsets when it comes to innovation as well as stabilization. Certainly a 
startup to watch, glad to hear that though incorporated in the US most developers actually live in Berlin 
now.<br><br>The second talk was given by Max Jakob from Neofonie GmbH (working on EU funded research project Dicode) 
gave an overview of their pipeline for named entity extraction and disambiguation based on a language model extracted 
from the raw German wikipedia dump. They used Pig to scale a pipeline down from about a week to 1.5 hours with not much 
development overhead: Quite some logic could be re-used from the open source project pignlproc initiated by Olivier 
Grisel. This project already features a Wikipedia loader, a UDF for extracting information from Wikipedia documents and 
additional scripts for training and building corpora.<br><br><img 
src="/hadoop_201112_neo.jpg"/><br><br>Based on that they defined the ML 
probability of a surface form being a named entity. The script itself is not very magical: The whole process can be 
expressed as a few steps involving grouping and couting tuples. The effect in terms of runtime vs. development time 
however is impressive.<br><br>Checkout their <a href="http://github.com/dicode-project/pignlproc">DICODE github 
project</a> for further details on the code itself.<br><br>After the meetup about 20 attendees followed David to a bar 
nearby. It is always great to get a chance to talk to the speakers, exchange experiences with others and learn more on 
what people are actually working on with Hadoop after the event.<br><br>Slides of all talks are going to be posted 
soon, videos go online as soon as they are post processed so stay tuned for further information.<br><br>Looking forward 
to seeing you again for the next meetup. If you could not make it this time, there is a very easy way to not have that 
happen again next time: First speaker to submit a talk proposal to David sets the date and time of the meetup (taking 
into account any constraints with venue and video taping of course).
