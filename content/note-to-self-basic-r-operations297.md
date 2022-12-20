---
title: "Note to self: Basic R operations"
date: 2012-10-18T22:55:53+02:00
tags: [R,matrix,Note to Self,]
---

# Note to self: Basic R operations


After searching for that all too often and for too long (in particular the "add a column as index" 
bit):<br><br><ul><br><li>To read a file: <code>d <- read.table('/home/isabel/input', sep=',', header=T, 
quote='')</code><br><li>Useful for getting an overview of the data:<code>summary(d); head(d); tail(d)</code><br><li>For 
sorting some data frame: <code>s <- d[order(d[,2]),];</code><br><li>For adding a column to a data frame: <code>s$idx <- 
seq(0, nrow(s) - 1, 1)</code><br><li>For plotting a column:<code> ggplot(s, aes(idx, engagement)) + geom_point() 
+scale_x_log10()</code><br></ul>
