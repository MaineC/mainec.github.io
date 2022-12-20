---
title: "Getting Hadoop trunk up and running from source"
date: 2009-10-04T20:18:27+02:00
tags: 0.21.0,Hadoop,dhb,Camp,Hacking,dumbo,
---

# Getting Hadoop trunk up and running from source


Having told Thilo about the possibility to write Hadoop jobs in Python with <a 
href="http://wiki.github.com/klbostee/dumbo/building-and-installing">Dumbo</a>, we spent some time getting Dumbo 0.21 
up and running over the past weekend. The first option the wiki proposes is to take a pre-0.21 release and patch that 
to work with the current Dumbo release. The second option described takes the not-yet-released version of Hadoop that 
can be used w/o any patches.<br><br>We decided to follow the latter suggestion. After the latest split of the project, 
we downloaded common, hdfs and mapreduce. Building each project was easy - assuming that ant, Sun JDK 6 (for Hadoop), 
Forrest (for the documentation pages) and Sun JDK 5 (for forrest) is installed.<br><br>Deviating from the 
documentation, the distributed filesystem as well as map reduce are now started from separate scripts (start-dfs.sh/ 
start-mapred.sh instead of start-all.sh). These scripts are located in the common project. In addition the variables 
HADOOP_HDFS_HOME and HADOOP_MAPRED_HOME must be set to point to respective projects for cluster setup to work. Other 
than that the setup currently is identical to the previous version.
