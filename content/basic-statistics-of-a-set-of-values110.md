---
title: "Basic statistics of a set of values"
date: 2009-03-09T11:21:51+01:00
tags: [Hacking,Statistics,]
---

# Basic statistics of a set of values


Just in order to find that when searching for it yet another time:<br><br>Problem: You have a set of values (for 
instance time it took to process various queries). You want a quick overview of how the values are 
distributed.<br><br>Solution: Store the values in a file separated by newline, read the file with R and output summary 
statistics.<br><br>R: times <- scan("times", list(0))<br>Read 30000 records<br>R: summary(times[[1]])<br>   Min. 1st 
Qu.  Median    Mean 3rd Qu.    Max.<br>   6.00   12.00   13.00   16.75   14.00 8335.00<br><br>That's it.
