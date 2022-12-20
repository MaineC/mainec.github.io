---
title: "ApacheConEU - part 03"
date: 2012-11-12T20:27:11+01:00
tags: [Httpd,ApacheCon,Apache Con,apacheconeu,]
---

# ApacheConEU - part 03


Tuesday started early with a plenary - run by the sponsor, not too many news there, except for the very last slide that 
raised a question that is being discussed often also within the ASF - namely how to define oneself compared to non-ASF 
projects. What is the real benefit for our users - and what is the benefit for people to go with the ASF. The speaker 
concentrated on pointing out the difference to github. Yes tooling changes are turning into a real game changer - but 
that is nothing that the foundation could not adopt over time. What I personally find interesting is not so much what 
makes us different from others but more what can be learnt from other projects - not only on github but also in a 
broader scope from the KDE, Python, Gnome, Debian, Open/Libre-Office communities, from people working on smaller but 
non-the-less successful projects as well as the larger foundations, maybe even the corporate driven projects. Over time 
lots of wisdom has accumulated within and outside of the foundation on how to run successful open source projects - now 
the question is how to transfer that knowledge to relatively young projects and whether that can help given the huge 
amount of commercial interest in open source - not only in using it but also in driving individual projects including 
all the benefits (more people) and friction around it.<br><br>The first talk I went to was an introduction to was 
Rainer Jung’s presentation on the new Apache httpd release. Most remarkably the event mpm available as “experimental” 
feature is now marked as default for the Apache distribution - though it is not being used for ssl connections. In 
addition there is support for async write completion, better support for sizing and monitoring. In particular when 
sizing the event mpm the new scoreboard comes in handy. When using it, keep in mind to adjust the number of allowed 
open file handles as well.<br><br>In order to better support server-to-client communication there is html5 web socket 
standardisation on it’s way. If you are interested in that check out the hybi standardisation list. Also taking a look 
at the <a href=”http://chromium.org/spdy”>Google SPDY</a> could be interesting. <br><br>Since 2.4 dynamic loadable 
modules are supported and easy to switch. When it comes to logging there is now support for sub second timestamp 
precision, per module log levels. Process and thread ids are kept in order to be able to untwist concurrent connection 
handling. There are unique message tokens in the error log to track requests. Also the error log format is configurable 
- including trace levels one to eight, configurable per directory, location and module.<br>They’ve added lots of trace 
messages to core, correlation ids between error and access log entries (format entry %L). In addition there is a 
mod_log_debug module to help you log exactly what you want when you want. <br><br>Speaking of modules - in order to 
upgrade them from 2.2 to 2.4 it’s in general sufficient to re-compile. With the new version though not all modules are 
going to be loaded as default anymore. New features include dynamic configurations based on mod_lua. AAA was changed 
again, there are filters to rewrite content before it’s sent out to clients (mod_substitute, mode_sed, mod_proxy_html). 
mod_remoteip helps to keep the original ip in your logs instead of the procy ip.<br><br>When it comes to documentation 
better check the English documentation - or better yet provide patches to it. mod_rewrite and mod_proxy improved a lot. 
In addition the project itself now has a new service for it’s users: via comments.apache.org you can send documentation 
comments to the project without the need to register for a bugzilla account and provide documentation patches. In 
addition there is now syntax highlighting in the documentation. One final hint: the project is very open and actively 
looking for new contributors - though they may be slow to respond on the user and dev list - they definitely are not 
unfriendly ;)<br>
