---
title: "ApacheConEU - part 11 (last part)"
date: 2012-11-20T20:35:21+01:00
tags: buildr,ApacheCon,Apache Con,log4j,apacheconeu,
---

# ApacheConEU - part 11 (last part)


One of the last sessions covered logging frameworks for Java. Christian Grobmeier started by detailing the common 
requirements for all logging frameworks:<br><br><ul><br><li>Speed - developers do not want to pay a disproportional 
penalty for using a logging framework.<br><li>Fail-safety and reliability - under no circumstances should your logging 
framework kill your application. In addition it would be most annoying to find that one log message that would help you 
de-cypher the problem your application ran into missing. As obvious as those requirements sound - there are counter 
examples to both: There is a memory leak in log4j1, when reconfiguring logback on the fly it may well lose 
messages.<br><li>Log frameworks should be backwards compatible: Both, changing the API as well as incompatible 
configuration file formats aren’t particularly great when wanting to upgrade the logging framework version you 
use.<br><li>On top of all the way you do logging ultimately is a matter of taste - by now there are several 
implementations even just for Java online catering needs ranging from pure simplicity to huge flexibility: log4j, 
logback, java.util.logging, AVSL, tinyLog. On top of that there are aggregators like SLF4j and commons logging - even 
though the speaker himself does contribute to the latter framework, at the current time he still recommends using SLF4J 
as it is actively being developed, more modern and better supported.<br></ul><br><br>Biggest news shared in the talk 
was the release of log4j2 which comes with commons-logging and slf4j integration. This version finally gets rid of the 
<code>if (debug.enabled()) { log.debug(...)}</code> idiom by introducing place holders and variable length argument 
lists essentially enabling format strings for logging. Markers can be added to the logging code to allow for later 
filtering. Writing plugins has been made a whole lot simpler. There is support for an easier to read xml configuration 
format as well as json configurations. In additions configurations can be set to be reloaded on change in a pre-defined 
interval. It is slightly slower than logback and log4j on average, though we are still talking about a few milliseconds 
for a large amount of log messages. Unfortunately those averages did not come with error bars which would have made 
interpreting them in comparison a bit easier.<br><br>However log4j is not just about logging. It does have sub projects 
for viewing logs of httpd, log4j and others (called chainsaw), logging for php and .net.<br><br>Log4j has a rather 
complex history: As soon as the leader of the project left, activity died away. By now activity has taken up again 
quite a bit with 4 contributors. They created 6 releases in the last year alone, on top of 600 mailing list messages 
and a huge amount of commits. Still also log4j is hiring - if you want to work for free on a fun project that affects 
nearly every Java developer world wide, work together with awesome coders this project is seeking new 
contributors.<br><br>If you consider logging boring just be reminded that logs are a valuable source of user activity 
leading to features like being able to recommend new products to customers, localise content offerings or even just 
adjusting the default settings of your web page to increase click through. Related to log4j there’s Apache Flume 
dealing with distributed logging, there’s challenges in the cloud and mobile space, Apache Mayhem for Logger 
ingestions.<br><br>The last technical session dealt with Apache Buildr - a build system for Java, though not only Java, 
written in Ruby. The advantage being that it delivers the artifact resolution and download from maven archives through 
ivy plugins, provides greater flexibility through ruby integration and can fall back to ant tasks if needed.<br><br>The 
final session was the closing plenary given by Nick Burch. Most noteably he invited attendees for ApacheCon2013 Europe. 
Looking forward to meeting all of you there. The community edition of ApacheCon was an awesome setup for people to meet 
and not only pitch their projects but to also provide deep technical detail and show off more of what the Apache 
community is all about. Looking forward to the audio recordings as well as to the videos taken during the conference. 
CU all next year!
