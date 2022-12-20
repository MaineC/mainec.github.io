---
title: "ApacheConNA: On Security"
date: 2013-05-12T20:22:19+02:00
tags: [ApacheConNA,ApacheCon,Apache Con,security,community,]
---

# ApacheConNA: On Security


<P><br>During the security talk at Apache Con a topic commonly glossed over by<br>developers was covered in quite some 
detail: With software being developed that<br>is being deployed rather widely online (over 50% of all websites are 
powered<br>by the Apache webserver) natually security issues are of large concern.<br><br><P><br>Currently there are 
eight trustworthy people on the foundation-wide security<br>response team, subscribed to security@apache.org. The team 
was started by<br>William A. Rowe when he found a volnarability in httpd. The general work mode -<br>as opposed to the 
otherwise ``all things open'' way of doing things at Apache -<br>is to keep the issues found private until fixed and 
publicise widely<br>afterwards.<br><br><P><br>So when running Apache software on your servers - how do you learn 
about<br>security issues? There is no such thing as a priority list for specific<br>vendors. The only way to get an 
inside scoop is to join the respective<br>project's PMC list - that is to get active yourself.<br><br><P><br>So what is 
being found? 90% of all security issues are found be security<br>researches. The remaining 10% are usually published 
accidentially - e.g. by<br>users submitting the issue through the regular public bug tracker of the<br>respective 
project.<br><br><P><br>In Tomcat currently no issues was disclosed w/o letting the project know. httpd<br>still is the 
prime target - even of security researchers who are in favour of<br>a full disclosure policy - the PMC cannot do a lot 
here other than fix issues<br>quickly (usually within 24 hours).<br><br><P><br>As a general rule of thumb: Keep your 
average release cycle time in mind - how<br>long will it take to get fixes into people's hands? Communicate 
transparently<br>which version will get security fixes - and which won't.<br><br><P><br>As for static analysis tools - 
many of those are written for web apps and as<br>such not very helpful for a container. What is highly dangerous in a 
web app<br>may just be the thing the container has to do to provide features to web apps.<br>As for Tomcat, they have 
made good experiences with Findbugs - most others have<br>too many false positives.<br><br><P><br>When dealing with a 
volnarability yourself, try to get guidance from the<br>security team on what is actually a security volnarability - 
though the final<br>decision is with the project.<br><br><P><br>Dealing with the tradeoff of working in private vs. 
exposing users affected by<br>the volnarability to attacks is up to the PMC. Some work in public but call the<br>actual 
fix a refactoring or cleanup. Given enough coding skills on the attacker<br>side this of course will not help too much 
as sort of reverse engineering what<br>is being fixed by the patches is still possible. On the other hand 
doing<br>everything in private on a separate branch isn't public development anymore.<br><br><P><br>After this general 
introduction Mark gave a good overview of the good, the bad<br>and the ugly way of handling security issues in Tomcat. 
For his slides<br>(including an anecdote of what according to the timing and topic looks like it<br>was highly related 
to the 2011 Java Hash Collision talk at Chaos Communication<br>Congress).<br><br><P><br>
