---
title: "Summary - December Get Together"
date: 2009-12-16T22:23:20+01:00
tags: [Berlin,Hadoop,Get Together,]
---

# Summary - December Get Together


Today the seventh Apache Hadoop Get Together took place in Berlin. The room was again packed with more than 40 people 
from various companies with and without practical experience with Hadoop: There were people from Nokia Gate 5, Sun, 
nurago, StudiVZ, Dawanda, Last.fm, nugg.ad. There were people from academia, e.g. HPI Potsdam. And a few Freelancers 
interested in the topic or providing help with Hadoop. <br><br>We had three very interesting talks. The first one was 
given by Richard Hutton from nugg.ad on their usage of Hadoop. They provide targeted advertisement services to their 
clients. Naturally they do need to process lots of user interactions to be able to draw reliable conclusions. nugg.ad 
started out with a traditional system setup: Erlang loggers in front, data got fed to well known data warehouse 
infrastructures, analysed and results pushed back to the frontends. However this architecture would scale only so far. 
So in the beginning of 2009 they started migrating their systems over to Hadoop. (A Thanks from the speaker to Tom 
White for publishing the Hadoop book at O'Reilly that obviously helped the developers a lot.). Today, nugg.ad is down 
from one to two days for analysis to one to two hours. I will link the slides of the talk as soon as I have the pdf 
version available.<br><br>Second talk was given by Jörg Möllenkamp on what Sun is doing with Hadoop. Sun does have 
"special hardware" - special in that the have systems with up to 512 virtual processors on one chip. With Solaris they 
do have an operating system that scales to that architecture. But now they are looking for applications that can use 
such hardware efficiently as well. Hadoop is well suited for distributing computations - so it looked like a great fit 
for Sun. <a href="http://www.isabel-drost.de/hadoop/slides/hadoop.sun.pdf">Slides are available 
online.</a><br><center><br><img src="/IMG_3688.jpg"><br></center><br>The last 
talk was given by Nikolaus Pohle from nurago. They switched to Hadoop only recently. Coming from online market 
analysis, they have to analyse lots of user interaction data. Currently they are moving away from a MySQL based 
architecture to a distributed system based on HDFS and Map/Reduce. In order to ease writing M/R jobs for their 
employees they built their own abstract language on top of Hadoop that helps formulating recurring jobs. That does 
sound a lot like what PIG or Cascading already does - but is specially targeted at the type of jobs they have. <a 
href="http://www.isabel-drost.de/hadoop/slides/nurago.pptx">Slides are available online.</a> <a 
href="http://www.isabel-drost.de/hadoop/slides/nurago.pdf">There is also a pdf version for users who prefer open 
formats.</a><br><br>If anyone should be interested in it, I also put my introductory slides <a 
href="http://www.isabel-drost.de/hadoop/slides/Danke_Hadoop_Dez_09.pdf">online</a>.<br><br>Next meetup will be in March 
2010. It will feature a talk by Zanox on their Hadoop usage, one talk by eCircle from Munich as well as one talk by 
Nokia. You are very welcome to join us. If you would like to give a presentation yourself - please do contact me. If 
you would like to sponsor the event, please send me an e-mail.<br><br>A big Thank You to all the speakers - Nikolaus 
Pohle from nurago, Jörg Möllenkamp from Sun and Richard Hutton from nugg.ad - without you, the event would not be 
possible. Another big Thank You to newthinking for providing the venue for free. And, last but not least, another big 
Thank You to StudiVZ for sponsoring the videos. They will be linked to from here as well as from the StudiVZ blog as 
soon as they are available.
