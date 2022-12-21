---
title: "Apache Hadoop Get Together - February 2012"
date: 2012-02-23T00:14:42+01:00
tags: [Storm,Kanban,Hadoop,Get Together,]
---

# Apache Hadoop Get Together - February 2012


Today the first Hadoop Get Together Berlin 2012 took place - David got the event hosted by and at <a 
href="http://www.axelspringer.de/">Axel Springer</a> who kindly also paid for the (soon to be published) videos. Thanks 
also to the <a href="http://www.unbelievable-machine.com/">unbelievable Machine company</a> for the tasty buffet after 
the meetup. Another thanks to Open Source Press for donating three of their <a 
href="https://www.opensourcepress.de/index.php?26&tt_products=343">Hadoop books</a>.<br><br><img 
src="/hgt_andre_feb_2012.jpg" 
style="float:left;padding-right:10pt"/><br><br>Today's selection was quite diverse: The event started with a 
presentation by <a href="http://twitter.com/#!/markusandrezak">Markus Andrezak</a> who gave an overview of Kanban and 
how it helped him change the development workflow over at <a href="http://www.mobile.de/">eBay/mobile</a>. Being well 
suited for environments that require flexibility Kanban is well suited to decrease risk associated with any single 
release by bringing the number of features released down to an absolute minimum. At Mobile his team got release cycles 
down to once a day. More than ten times a day however aren't unheard of as well. The general goal for him was to reduce 
the risk associated with releases by reducing the number of features released per release, reducing the number of 
moving parts in one release and as a result reducing the number of potential sources for problems: If anything goes 
wrong, rolling back is no issue - nor is narrowing down on the potential sources of bugs in the changed software that 
were introduced in that particular release.<br><br>This development and output focused part of the process is 
complemented by an input focused Kanban cycle for product design: Products are going from idea to vision to a more 
detailed backlog to development and finally live the same as issues in development itself move from Todo to in 
progress, under review and done.<br><br>With both cycles the main goal is to keep the number of items in progress as 
low as possible. This will result in more focus for each developer and greatly reduce overhead: Don't do more than one 
or two things at a time. Only catch: Most companies are focused on keeping development busy at all times - their goal 
is to reach 100% utilization. This however is in no way correlated to actual efficiency: By having 100% utilization 
there is not way you can deal with problems along the way, there is no buffer. Instead the idea should be to 
concentrate on a constant flow of released and live features instead.<br><br><img 
src="/hgt_all_feb2012.jpg" style="float:right"/><br><br>Now what is the link of 
all that to Hadoop? (Hint: No, this is no pun on the project's slow release cycle.) The process of Kanban allows for 
frequent releases, it allows for frequent feedback. This enables a model of development that starts out from a model of 
your business case (no matter how coarse that may be), start building some code, measure your performance with that 
code based on actual usage data and adjust the model accordingly. Kanban lets you iterate very quickly on that loop 
getting you ahead of competitors eventually. In terms of technology one strong tool in their toolbox to really do data 
analytics on their incoming data is to use Hadoop and scale up analysing business data.<br><br>In the second talk 
Martin Scholl started out by drawing a comparison from music vs. printed music sheets to the actual performance of 
musicians in a concert: The former represents static, factual data. The latter represents a process that may be 
recorded, but may not by copied itself as it lives by the interactions with the audience. The same holds true for 
social networks: Their current state and the way you look at them is deeply influenced by your way of interacting with 
the system in realtime.<br><br>So in addition to data storage solutions for static data, he argues, we also need a way 
to process streaming data in an efficient and fault tolerant way. The system he uses for that purpose is <a 
href="https://github.com/nathanmarz/storm">Storm</a> that was open-sourced by Twitter late last year. Built on top of 
zeroMQ it allows for flexible and fault tolerant messaging. Example applications mentioned are event analysis 
(filtering, aggregation, counting, monitoring), parallel distributed rpc based on message passing.<br><br>Two concrete 
examples include setting up a live A/B testing environment that is dynamically reconfigurable based on it's input as 
well as event handling in a social network environment where interactions might trigger messages being sent by mail and 
instant message but also trigger updates in a recommendation model.<br><br>In the last talk Fabian Hüske from TU Berlin 
introduced <a href="http://www.stratosphere.eu/">Stratosphere</a> - an EU founded research project that is working on 
an extended computational model on top of HDFS that provides more flexibility and better performance. Being developed 
before the rise of Apache Hadoop <a 
href="http://hadoop.apache.org/common/docs/r0.23.0/hadoop-yarn/hadoop-yarn-site/YARN.html">YARN</a> unfortunately 
essentially what they did was to re-implement the whole map/reduce computational layer and put their system into that. 
Would be interesting to see how a port to YARN performs and what sort of advantages it gives in production. 
<br><br>Looking forward to seeing you all in June for <a href="http://berlinbuzzwords.de">Berlin Buzzwords</a> - make 
sure to submit your presentation soon, call for presentations won't be extended this year.
