---
title: "Note to self: svn:ignore usage"
date: 2011-02-25T20:47:54+01:00
tags: svn,Hacking,cheat sheet,trivia,Note to Self,
---

# Note to self: svn:ignore usage


Putting the information here to make retrieving it a bit easier next time.<br><br>When working with svn and some random 
IDE I'd really love to avoid checking in any files that are IDE specific (project configuration, classpath, etc.). The 
command to do that:<br><code><br>svn propedit svn:ignore $directory_to_edit<br></code><br><br>After issuing this 
command you'll be prompted to enter file patterns for files to ignore or the directory names.<br><br>More detailed 
information in the <a href="http://svnbook.red-bean.com/en/1.1/ch07s02.html">official documentation on svn:ignore</a>.
