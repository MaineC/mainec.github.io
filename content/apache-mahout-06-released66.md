---
title: "Apache Mahout 0.6 released"
date: 2012-02-08T21:33:37+01:00
tags: Mahout,Apache,mongodb,Cassandra,
---

# Apache Mahout 0.6 released


As of Monday, February 6th a new Apache Mahout version was released. The new package features<br><br>Lots of 
performance improvments:<br><br><ul><br><li>A new LDA implementation using Collapsed Variational Bayes 0th Derivative 
Approximation - try that out if you have been bothered by the way less than optimal performance of the old 
version.<br><li>Improved Decision Tree performance and added support for regression problems<br><li>Reduced runtime of 
dot product between vectors - many algorithms in Mahout rely on that, so these performance improvements will affect 
anyone using them.<br><li>Reduced runtime of LanczosSolver tests - make modifications to Mahout more easily and have 
faster development cycles by faster testing.<br><li>Increased efficiency of parallel ALS matrix 
factorization<br><li>Performance improvements in RowSimilarityJob, TransposeJob - helpful for anyone trying to find 
similar items or running the Hadoop based recommender<br></ul><br><br>New features:<br><ul><br><li>K-Trusses, Top-Down 
and Bottom-Up clustering, Random Walk with Restarts implementation<br><li>SSVD enhancements<br></ul><br><br>Better 
integration:<br><ul><br><li>Added MongoDB and Cassandra DataModel support<br><li>Added numerous clustering display 
examples<br></ul><br><br>Many bug fixes, refactorings, and other small improvements. More information is available in 
the <a href="https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12310751&version=12316364">Release 
Notes</a>.<br><br>Overall great improvements towards better performance, better stability and integration. However 
there are still quite some outstanding issues and issues in need for review. Come join the project, help us improve 
existing patches, improve performance and in particular integration and streamlining of how to use the different parts 
of the project.
