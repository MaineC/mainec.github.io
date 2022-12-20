---
title: "JAX: Logging best practices"
date: 2013-05-22T20:37:59+02:00
tags: logging,Java,Event,JAX,
---

# JAX: Logging best practices


The ideal outcome of Peter Ro&#195;&#159;bach's talk on logging best practices was to have<br>attendees leave the room 
thinking ``we know all this already and are applying<br>it successfully'' - most likely though the majority left 
thinking about how to<br>implement even the most basic advise discussed.<br><br><P><br>From his consultancy and fire 
fighter background he has a good overview of what<br>logging in the average corporate environment looks like: No 
logging plan, no<br>rules, dozens of logging frameworks in active use, output in many different<br>languages, no 
structured log events but a myriad of different quoting,<br>formatting and bracketing standards 
instead.<br><br><P><br>So what should the ideal log line contain? First of all it should really be a<br>log line 
instead of a multi line something that cannot be reconstructed when<br>interleaved with other messages. The line should 
not only contain the class<br>name that logged the information (actually that is the least important piece 
of<br>information), it should contain the thread id, server name, a (standardised and<br>always consistently formatted) 
timestamp in a decent resolution (hint: one new<br>timestamp per second is not helpful when facing several hundred 
requests per<br>second). Make sure to have timing aligned across machines if timestamps are<br>needed for correlating 
logs. Ideally there should be context in the form of<br>request id, flow id, session id.<br><br><P><br>When thinking 
about logs, do not think too much about human readability - think<br>more in terms of machine readability and 
parsability. Treat your logging system<br>as the db in your data center that has to deal with most traffic. It is 
what<br>holds user interactions and system metrics that can be used as business<br>metrics, for debugging performance 
problems, for digging up functional issues.<br>Most likely you will want to turn free text that provides lots of 
flexibility<br>for screwing up into a more structured format like json, or even some binary<br>format that is storage 
efficient (think protocol buffers, thrift, avro).<br><br><P><br>In terms of log levels, make sure to log development 
traces on trace, provide<br>detailed problem analysis stuff on debug, put normal behaviour onto info. In<br>case of 
degraded functionality, log to warn. In case of things you cannot<br>easily recovered from put them on error. When it 
comes to logging hierarchies -<br>do not only think in class hierarchies but also in terms of use cases: 
Just<br>because your http connector is used in two modules doesn't mean that there<br>should be no way to turn logging 
on just for one of the modules alone.<br><br><P><br>When designing your logging make sure to talk to all stakeholders 
to get clear<br>requirements. Make sure you can find out how the system is being used in the<br>wild, be able to 
quantify the number of exceptions; max, min and average<br>duration of a request and similar 
metrics.<br><br><P><br>Tools you could look at for help include but are not limited to splunk, jmx,<br>jconsole, 
syslog, logstash, statd, redis for log collection and queuing.<br><br><P><br>As a parting exercise: Look at all of your 
own logfiles and count the different<br>formats used for storing time.
