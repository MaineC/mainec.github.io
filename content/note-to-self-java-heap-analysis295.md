---
title: "Note to self - Java heap analysis"
date: 2012-02-09T21:30:21+01:00
tags: [Hacking,Java,troubleshooting,heap,Note to Self,]
---

# Note to self - Java heap analysis


As I keep searching for those URLs over and over again linking them here. When running into JVM heap issues (an out of 
memory exception is a pretty sure sign, so can be the program getting slower and slower over time) there's a few things 
you can do for analysis:<br><br>Start with telling the effected JVM process to output some statistics on heap layout as 
well as thread state by sending it a SIGQUIT (if you want to use the number instead - it's 3 - avoid typing 9 instead 
;) ).<br><br>More detailed insight is available via jConsole - remote setup can be a bit tricky but is well doable and 
worth the effort as it gives much more detail on what is running and how memory consumption really looks 
like.<br><br>For an detailed analysis take a heap dump with either jmap, jConsole or by starting the process with the 
JVM option <code>-XX:+HeapDumpOnOutOfMemoryError</code>. Look at it either with <a 
href="http://docs.oracle.com/javase/6/docs/technotes/tools/share/jhat.html">jhat</a> or the <a 
href="https://www.ibm.com/developerworks/community/groups/service/html/communityview?communityUuid=4544bafe-c7a2-455f-9d
43-eb866ea60091">IBM heap analyzer</a>. Also netbeans offers nice support for searching for memory leaks.<br><br>On a 
more general note on diagnosing java stuff see <a 
href="http://programm.froscon.org/2008/attachments/45_FrOSCon08_RJung_Troubleshooter_20080823.pdf">Rainer Jung's 
presentation on troubleshooting Java</a> applications as well as <a 
href="http://gotocon.com/dl/goto-amsterdam-2011/slides/AttilaSzegedi_JVMPerformanceOptimizationsAtTwittersScale.pdf">Att
ila Szegedi's presentation on JVM tuning</a>.<br>
