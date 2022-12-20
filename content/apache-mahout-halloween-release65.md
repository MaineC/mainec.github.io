---
title: "Apache Mahout 0.4 release"
date: 2010-11-03T15:21:28+01:00
tags: Mahout,release,Apache Mahout,
---

# Apache Mahout 0.4 release


On last Sunday the <a href="http://mahout.apache.org/">Apache Mahout</a> project published the 0.4 release. Nearly 
every piece of the code has been refactored and improved since the last 0.3 release. The release was timed to happen 
exactly before Apache Con NA in Atlanta. As such it was published on October 31st - the Halloween release, 
sort-of.<br><br>Especially mentionable are the following improvements:<br><ul><br><li>Model refactoring and CLI changes 
to improve integration and consistency<br><li>Map/Reduce job to compute the pairwise similarities of the rows of a 
matrix using a customizable similarity measure<br><li>Map/Reduce job to compute the item-item-similarities for 
item-based collaborative filtering<br><li>More support for distributed operations on very large matrices<br><li>Easier 
access to Mahout operations via the command line<br><li>New vector encoding framework for high speed vectorization 
without a pre-built dictionary<br><li>Additional elements of supervised model evaluation framework<br><li>Promoted 
several pieces of old Colt framework to tested status (QR decomposition, in particular)<br><li>Can now save random 
forests and use it to classify new data<br></ul><br><br>New features and algorithms include:<br><ul><br><li>New 
ClusterEvaluator and CDbwClusterEvaluator offer new ways to evaluate clustering effectiveness<br><li>New Spectral 
Clustering and MinHash Clustering (still experimental)<br><li>New VectorModelClassifier allows any set of clusters to 
be used for classification<br><li>RecommenderJob has been evolved to a fully distributed item-based 
recommender<br><li>Distributed Lanczos SVD implementation<br><li>New HMM based sequence classification from GSoC 
(currently as sequential version only and still experimental)<br><li>Sequential logistic regression training 
framework<br><li>New SGD classifier<br><li>Experimental new type of NB classifier, and feature reduction options for 
existing one<br></ul><br><br>There were many, many more small fixes, improvements, refactorings and cleanup. Go check 
out the new release, give the new features a try and report back to us on the user mailing list.
