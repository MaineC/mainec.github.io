---
title: "JAX: Tales from production"
date: 2013-05-23T20:38:57+02:00
tags: [logging,Java,Event,JAX,]
---

# JAX: Tales from production


In a second presentation Peter Ro&#195;&#159;bach together with Andreas Schmidt provided<br>some more detail on what 
the topic logging entails in real world projects.<br>Development messages turn into valuable information needed to 
uncover issues<br>and downtime of systems, capacity planning, measuring the effect of software<br>changes, analysing 
resource usage under real world usage. In addition to these<br>technical use cases there is a need to provide business 
metrics.<br><br><P><br>When dealing with multiple systems you deal with correlating values across<br>machines and 
systems, providing meaningful visualisations to draw the correct<br>decisions.<br><br><P><br>When thinking of your log 
architecture you might want to consider storing not<br>only log messages. In addition facts like release numbers should 
be tracked<br>somewhere - ready to join in when needed to correlate behaviour with release<br>version. To do that also 
track events like rolling out a release to production.<br>Launching in a new market, switching traffic to a new system 
could be other<br>events. Introduce not only pure log messages but also provide aggregated<br>metrics and counters. All 
of these pieces should be stored and tracked<br>automatically to free operations for more important 
work.<br><br><P><br>Have you ever thought about documenting not only your software, it's interfaces<br>and input/output 
format? What about documenting the logged information as well?<br>What about the fields contained in each log message? 
Are they documented or do<br>people have to infer their meaning from the content? What about valid ranges<br>for values 
- are they noted down somewhere? Did you store whether a specific<br>field can only contain integers or whether some 
day it also could contain<br>letters? What about the number format - is it decimal, hexadecimal?<br><br><P><br>For a 
nice architecture documentation of the BBC checkout<br><br><a 
href="http://www.guardian.co.uk/info/developer-blog/2012/oct/04/winning-the-metrics-battle">Winning the metrics 
battle</a> by the BBC dev blog.<br><br><P><br>There's an abundance of tools out there to help you with all sorts of 
logging<br>related topics:<br><br><P><br><br><UL><br><LI>For visualisation and transport: Datadog, kibana, logstash, 
statsd,<br>graphite, syslog-ng<br></LI><br><LI>For providing the values: JMX, metrics, Jolokia<br></LI><br><LI>For 
collection: collecd, statsd, graphite, newrelic, datadog<br></LI><br><LI>For storage: typical RRD tools including 
RRD4j, MongoDB, OpenTSDB based<br>on HBase, Hadoop<br></LI><br><LI>For charting: Munin, Cacti, Nagios, Graphit, 
Ganglia, New Relic, Datadog<br></LI><br><LI>For Profiling: Dynatrace, New Relic, Boundary<br></LI><br><LI>For events: 
Zabbix, Icinga, OMD, OpenNMS, HypericHQ, Nagios,JbossRHQ<br></LI><br><LI>For logging: splunk, Graylog2, Kibana, 
logstash<br></LI><br></UL><br><br><P><br>Make sure to provide metrics consistently and be able to add them with 
minimal<br>effort. Self adaption and automation are useful for this. Make sure developers,<br>operations and product 
owners are able to use the same system so there is no<br>information gap on either side. Your logging pipeline should 
be tailored to<br>provide easy and fast feedback on the implementation and features of the<br>product.<br><br><P><br>To 
reach a decent level of automation a set of tools is needed for:<br><br><UL><br><LI>Configuration management (where to 
store passwords, urls or ips, log<br>levels etc.). Typical names here include Zookeeper,but also CFEngine, 
Puppet<br>and Chef.<br></LI><br><LI>Deployment management. Typical names here are UC4, udeploy, glu, 
etsy<br>deployment.<br></LI><br><LI>Server orchestration (e.g. what is started when during boot). Typical<br>names 
include UC4, Nolio, Marionette Collective, rundeck.<br></LI><br><LI>Automated provisioning (think ``how long does it 
take from server failure<br>to bringing that service back up online?''). Typical names include kickstart,<br>vagrant, 
or typical cloud environments.<br></LI><br><LI>Test driven/ behaviour driven environments (think about adjusting 
not<br>only your application but also firewall configurations). Typical tools that<br>come to mind here include Server 
spec, rspec, cucumber, c-puppet, chef.<br></LI><br><LI>When it comes to defining the points of communication for the 
whole<br>pipeline there is no tool you can use that is better than traditional pen and<br>                           
paper, socially getting both development and operations into one room.<br></LI><br></UL><br><br><P><br>The tooling to 
support this process goes from simple self-written bash scripts<br>in the startup model to frameworks that support the 
flow partially, up to<br>process based suites that help you. No matter which path you choose the goal<br>should always 
be to end up with a well documented, reproducable step into<br>production. When introducing such systems problems in 
your organisation may<br>become apparent. Sometimes it helps to just create facts: It's easier to ask 
for<br>forgiveness than permission.<br><br>                                                                             
                                                                    
