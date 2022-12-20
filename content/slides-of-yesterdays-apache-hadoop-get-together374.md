---
title: "Slides of yesterday's Apache Hadoop Get Together"
date: 2011-01-28T21:40:18+01:00
tags: Apache Hadoop,Lucene4,Redis,Apache Lucene,Get Together,
---

# Slides of yesterday's Apache Hadoop Get Together


This time with little less than 24 hours delay - the usual, by some impatiently expected, summary of the Apache Hadoop 
Get Together. The meetup took place at Zanox' event campus. The room was well filled with some fourty attendees from 
various companies, experience with Hadoop ranging from interested beginners to experienced users.<br><br>Slides of all 
presentations:<br><ul><br><li><a href="http://isabel-drost.de/hadoop/slides/josh_hadoop_2011.pdf">Josh Devins on Hadoop 
at Nokia</a><br><li><a href="http://isabel-drost.de/hadoop/slides/simon_lucene_2011.pdf">Simon Willnauer on Lucene 
4</a><br><li><a href="http://dl.dropbox.com/u/6726517/hadoop_get_together.pdf">Paolo Negris on Scaling 
issues</a><br></ul><br><br><br>The first presentation was given by Josh Devins from Nokia in Berlin. He is working 
closely with the OVI maps team. After giving a general overview of the cluster setup as well as some information on 
what machines they are running Hadoop on. Currently Hadoop is used mostly to process log data and aggregate information 
from it. For that task scribe is used for log collection, standard Ganglia and Nagios for monitoring and graphing. When 
starting to process and aggregate log data the main challenge is a mixture of transforming the logs into some slightly 
consistant format, cleaning logs from noisy data and in some cases initiating the storage of further information from 
various services. Nokia is a heavy - and happy - user of Pig though they are looking into Hive for making data 
accessible to business analysts who usually are more familiar with SQL like languages.<br><br>As an example - the 
results of a few simple jobs on analysing location based searches were shown: Looking at where in the greater Berlin 
area searches for "Ikea" were issued - at least Ikea Tempelhof and Spandau were easy to make out. On a more serious use 
case similar information could be used for automatically detecting traffic jams.  Currently Nokia is only scratching 
the surface of all information that could possibly be extracted. So there is quite some interesting work 
ahead.<br><br><br>In the second presentation Simon Willnauer gave a deep dive introduction to the various stunning 
performance improvements of Lucene4 - the not yet released, not backwards compatible trunk version of Apache Lucene. 
For more flexible indexing column stride fields have been integrated. With the introduction of an automaton 
implementation fuzzy query performance could be improved significantly reducing complexity from n to log n. In addition 
Simon had a great surprise to share with the audience: He proudly announced that Ted Dunning (you know that guy who is 
active on nearly every Hadoop mailing list, shares a lot of in-depth theoretical knowledge that is backed by proven 
practical experience?) and Doug Cutting (founder of Lucene, Hadoop and many other Apache projects) are going to be 
keynote speakers at Berlin Buzzwords.<br><br><br>In the third presentation Paolo Negri shared some inside as to how 
Wooga's Ruby on Rails/ MySQL based system was scaled. Disclaimer: Redis did play a major role when upping performance. 
<br><br>Videos will be published as soon as they are processed - thanks again to Cloudera for supporting the event by 
sponsoring video taping.
