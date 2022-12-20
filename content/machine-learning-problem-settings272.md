---
title: "Machine learning problem settings"
date: 2011-08-06T07:10:15+02:00
tags: Apache Mahout,Science,Theory,Machine Learning,
---

# Machine learning problem settings


Together with Sebastian Schelter I held a Nokia sponsored (Thank you!) <a 
href="http://lsf.tubit.tu-berlin.de/qisserver/servlet/de.his.servlet.RequestDispatcherServlet?state=verpublish&status=in
it&vmfile=no&publishid=116540&moduleCall=webInfo&publishConfFile=webInfo&publishSubDir=veranstaltung">lecture on large 
scale data analysis and data mining</a> during the past few months. <br><br>After supervising a few successful 
university projects based on Apache Mahout the goal of this lecture was to introduce students to some of the basic 
concepts and problems encountered today in a world where huge datasets are generally available and are easy to process 
with Apache Hadoop. As such the course is targeted at an entry level audience - thorough treatment of the mathematical 
background of latest machine learning technology is left to the machine learning research groups in <a 
href="http://www.cs.uni-potsdam.de/~scheffer/">Potsdam</a>, at <a 
href="http://www.ml.tu-berlin.de/menue/machine_learning/">TU Berlin</a> and <a href="http://www.ni.tu-berlin.de/">the 
neural information processing group at TU</a>.<br><br>Slides and exercises are <a 
href="https://github.com/MaineC/aim3-tu-berlin">available online</a> via git. Please let me know if you want to re-use 
them in your lecture.<br><br><iframe width="500" height="350" frameborder="0" scrolling="no" marginheight="0" 
marginwidth="0" src="http://www.piritiles.com/map/6146433?embed=1"></iframe><br><br>The very first problem that users 
of machine learning algorithms usually come across is mapping their application problem to one of the various machine 
learning problems. In 2010 Michael Brückner gave a lecture on <a 
href="http://www.cs.uni-potsdam.de/ml/teaching/ws10/ida.html">Intelligent Data Analysis with Matlab</a> (slides and 
videos in German) including a simple taxonomy of algorithms:<br><br>According to <br><br><ul><br><li>the types of input 
data an algorithm can handle (either independent instances, also called examples, sequences or graphs of 
instances)<br><li>the type of training data available (e.g. instances with assigned nominal target attribute, no labels 
at all, a partial sorting of sets of instances)<br><li>and the learning goal<br></ul> algorithms can be nicely 
partitioned by the learning problem that they solve. Based on that very first step of identifying exactly what the 
problem setting is, deciding which algorithm to use becomes much easier. Based on that taxonomy I came up with the 
above graphic giving a first overview of which tasks can be solved with machine learning:<br><br>Boxes in dark blue are 
what in general is called supervised learning, yellow unsupervised and light blue semi supervised - based on the amount 
of labeled training data available. Red boxes indicate settings with the goal of knowledge discovery. Green are any 
ranking problems.<br>
