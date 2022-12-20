---
title: "ApacheConNA: Monitoring httpd and Tomcat"
date: 2013-05-13T20:23:23+02:00
tags: Httpd,ApacheConNA,ApacheCon,Apache Con,tomcat,
---

# ApacheConNA: Monitoring httpd and Tomcat


<P><br>Monitoring - a task generally neglected - or over done - during development.<br>But still vital enough to wake 
up people from well earned sleep at night when<br>done wrong. Rainer Jung provided some valuable insights on how to 
monitor Apache httpd and Tomcat.<br><br><P><br>Of course failure detection, alarms and notifications are all part of 
good<br>monitoring. However so is avoidance of false positives and metric collection,<br>visualisation, and collection 
in advance to help with capacity planning and<br>uncover irregular behaviour.<br><br><P><br>In general the standard 
pieces being monitored are load, cache utilisation,<br>memory, garbage collection and response times. What we do not 
see from all that<br>are times spent waiting for the backend, looping in code, blocked threads.<br><br><P><br>When it 
comes to monitoring Java - JMX is pretty much the standard choice. Data<br>is grouped in management beans (MBeans). 
Each Java process has default beans,<br>on top there are beans provided by Tomcat, on top there may be 
application<br>specific ones.<br><br><P><br>For remote access, there are Java clients that know the protocol - the 
server<br>must be configured though to accept their connection. Keep in mind to open the<br>firewall in between as well 
if there is any. Well known clients include<br>JVisualVM (nice for interactive inspection), jmxterm as a command line 
client.<br><br><P><br>The only issue: Most MBeans encode source code structure, where what you really<br>need is change 
rates. In general those are easy to infer though.<br><br><P><br>On the server side for Tomcat there is the JMXProxy in 
Tomcat manager that<br>exposes MBeans. In addition there is Jolohia (including JSon serialisation) or<br>the option to 
roll your own.<br><br><P><br>So what kind of information is in MBeans:<br><br><P><br><br><UL><br><LI>OS - load, process 
cpu time, physical memory, global OS level<br>stats. As an example: Here deviding cpu time by time  geves you the 
average cpu<br>concurrency.<br></LI><br></LI><br><LI>Runtime MBean gives uptime.<br></LI><br><LI>Threading MBean gives 
information on count, max available threads etc<br></LI><br><LI>Class Loading MBean should get stable unless you are 
using dynamic<br>languaes or have enabled class unloading for jsps in Tomcat.<br></LI><br><LI>Compliation contains 
HotSpot compiler information.<br></LI><br><LI>Memory contains information on all regions thrown in one pot. If you 
need<br>more fine grained information look out for the Memory Pool and GC MBeans.<br></LI><br></UL><br><br><P><br>As 
for Tomcat specific things:<br><br><P><br><br><UL><br><LI>Threadpool (for each connector) has information on size, 
number of busy<br>threads.<br></LI><br><LI>GlobalRequestProc has request counts, processing times, max time 
bytes<br>received/sent, error count (those that Tomcat notices that is).<br></LI><br><LI>RequestProcessor exists once 
per thread, it shows if a request is<br>currently running and for how long. Nice to see if there are long 
running<br>requests.<br></LI><br><LI>DataSource provides information on Tomcat provided database 
connections.<br></LI><br></UL><br><br><P><br>Per Webapp there are a couple of more 
MBeans:<br><br><P><br><br><UL><br><LI>ManagerMBean has information on session management - e.g. session<br>counter 
since start, login rate, active sessions, expired sessions, max active<br>sinse restart sessions (here a restart is 
possible), number of rejected<br>sessions, average alive time, processing time it took to clean up sessions,<br>create 
and required rate for last 100 sessions<br></LI><br><LI>ServletMBean contains request count, accumulated processing 
time.<br></LI><br><LI>JspMBean (together with activated loading/unloading policy) has<br>information on unload and 
reload stats and provides the max number of loaded<br>jsps.<br></LI><br></UL><br><br><P><br>For httpd the goals with 
monitoring are pretty similar. The only difference is<br>the protocol used - in this case provided by the status 
module. As an<br>alternative use the scoreboard connections.<br><br><P><br>You will find information 
on<br><br><P><br><br><UL><br><LI>restart time, uptime<br></LI><br><LI>serverload<br></LI><br><LI>total number of 
accesses and traffic<br></LI><br><LI>idle workers and number of requests currently processed<br></LI><br><LI>cpu usage 
- though that is only accurate when all children are stopped<br>which in production isn't particularly 
likely.<br></LI><br></UL><br><br><P><br>Lines that indicate what threads do contain waitinng, request read, send 
reply<br>- more information is documented online.<br><br><P><br>When monitoring make sure to monitor not only 
production but also your stress<br>tests to make meaningful comparisons.<br><br><P><br>
