---
title: "Devoxx – Day 2 HBase "
date: 2010-12-09T21:25:36+01:00
tags: adobe,NOSQL,twitter,General,Mahout,facebook,Hacking,hbase,Devoxx,
---

# Devoxx – Day 2 HBase 


Devoxx featured several interesting case studies of how HBase and Hadoop can be used to scale data analysis back ends 
as well as data serving front ends. <br><br><h2>Twitter</h2><br><br>Dmitry Ryaboy from Twitter explained how to scale 
high load and large data systems using Cassandra. Looking at the sheer amount of tweets generated each day it becomes 
obvious that with a system like MySQL alone this site cannot be run.  <br><br>Twitter has released several of their 
internal tools under a free software license for others to re-use – some of them being rather straight forward, others 
more involved. At Twitter each Tweet is annotated by a user_id, a time stamp (ok if skewed by a few minutes) as well as 
a unique tweet_id. In order to come up with a solution for generating the latter one they built a library called 
snowflake. Though rather simple algorithm even works in a cross data-centre set-up: The first bits are composed of the 
current time stamp, the following bits encode the data-centre, after that there is room for a counter. The tweet_ids 
are globally ordered by time and distinct across data-centres without the need for global synchronisation.<br><br>With 
gizzard Twitter released a rather general sharding implementation that is used internally to run distributed versions 
of Lucene, MySQL as well as Redis (to be introduced for caching tweet timelines due to its explicit support for lists 
as data structures for values that are not available in memcached).<br><br>FlockDB for large scale social graph storage 
and analysis. Rainbird for time series analysis, though with OpenTSDB there is something comparable available for 
HBase. Haplocheirus for message vector caching (currently based on memcached, soon to be migrated to Redis for its 
richer data structures). The queries available through the front-end are rather limited thus making it easy to provide 
pre-computed, optimised version in the back-end. As with the caching problem a tradeoff between hit rate on the pool of 
pre-computed items vs. storage cost can be made based on the observed query distribution.<br><br>In the back-end of 
Twitter various statistical and data mining analysis are run on top of Hadoop HBase To compute potentially interesting 
followers for users, to extract potentially interesting products etc.<br>The final take-home message here: Go from 
requirements to final solution. In the space of storage systems there is not such thing as a silver bullet. Instead you 
have to carefully evaluate features and properties of each solutions as your data and load 
increase.<br><br><h2>Facebook</h2><br><br>When implementing Facebook Messaging (a new feature that was announced this 
week) Facebook decided to go for HBase instead of Cassandra. The requirements of the feature included massive scale, 
long-tail write access to the database (which more or less ruled out MySQL and comparable solutions) and a need for 
strict ordering of messages (which ruled out any eventually consistent system. The decision was made to use 
HBase.<br><br>A team of 15 developers (including operations and frontend) was working on the system for one year before 
it was finally released. The feature supports for integration of facebook messaging, IM, SMS and mail into one single 
system making it possible to group all messages by conversation no matter which device was used to send the message 
originally. That way each user's inbox turns into a social inbox.<br><br><h2>Adobe</h2><br><br>Cosmin Lehene presented 
four use cases of Hadoop at Adobe. The first one dealt with creating and evaluating profiles of the Adobe Media Player. 
Users would be associated with a vector giving more information on what types of genre the meda they consumed belonged 
to. These vectors would then be used to generate recommendations for additional content to view in order to increase 
consumption rate. Adobe built a clustering system that would interface Mahout's canopy- and k-means implementations 
with their HBase backend for user grouping. Thanks Cosmin for including that information in your presentation!<br><br>A 
second use case focussed on finding out more on the usage of flash on the internet. Using Google to search for flash 
content was no good as only the first 2000 results could be viewed thus resulting in a highly skewed sample. Instead 
they used a mixture of nutch and HBase for storage to retrieve the content. Analysis was done with respect to various 
features of flash movies, such as frame rates. The analysis revealed a large gap between the perceived typical usage 
and the actual usage of flash on the internet.<br><br>The third use case involves analysis of images and usage patterns 
on the Photoshop-in-a-browser edition of Photoshop.com. The forth use case dealt with scaling the infrastructure that 
powers businesscatalyst – a turn-key online business platform solution including analysis, campaigning and more. When 
purchased by Adobe the system was very successful business-wise. However the infrastructure was by no means able to put 
up with the load it had to accommodate. Changing to a back-end based on HBase led to better performance, faster report 
generation.<br>
