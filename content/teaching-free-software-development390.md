---
title: "Teaching Free Software Development"
date: 2010-06-20T12:55:07+02:00
tags: Mahout,Teaching,University,Free Software,TU Berlin,
---

# Teaching Free Software Development


In Summer last year I was invited to give a presentation on Apache Mahout at TU Berlin. After the talk was over some of 
the research group members asked me to design and give a course on scalable machine learning with open source software 
during the winter semester.<br><br>The project attracted four to five students - not very many - but then again it is a 
course people can take voluntarily. During the first semester participants were asked to integrate Mahout to build a 
system that crawls web pages, assigns them to clusters and makes the content searchable with Lucene. The intention was 
to get students to publish any patches they have to make at Mahout. In addition the code behind the system was supposed 
to be published after the project was over.<br><br>This setup turned out to be sub-optimal: The participants never grew 
confident enough to publish not only their ideas and design on the mailinglist but also send in the access data to the 
SCM system that hosted the project source code.<br><br>Some similar setup was run at HPI Potsdam by Christoph Böhm: He 
let students implement various information retrieval and machine learning algorithms on top of Apache Hadoop. After the 
course was over he tried to motivate students to publish their code at Apache Mahout. So far I have seen no 
submissions.<br><br>Being aware of these problems next time I setup the course for the summer semester at TU I chose a 
slightly different model: Having only four students who do not have enough free cycles to work on the project full time 
I set the goal to implement an HMM - including tests, example and documentation. Being roughly aligned with GSoC I 
asked students to publish their <a href="https://issues.apache.org/jira/browse/mahout-396">timeline in JIRA</a>. As 
soon as coding started I urged them to publish even incremental progress and ask the community for feedback. 
<br><br>Now we do have an open JIRA issue with a patch attached to it. People also got some code review feedback 
already. Having Berlin Buzzwords in town while the course was still running I used my chance to get students in touch 
with other Mahout developers. Looks like at least one of them is planning to stay with the project for a little longer. 
For me it would be a great success if at least one student could be turned into a longer term contributor to the 
project.<br><br>So far it looks like applying the general principle of releasing code early and often helps people do 
integrate into some project. My own lesson learned from those experiences however is to urge students early on to get 
in touch and release their code: It was not particularly easy to get them to send e-mails to public mailing lists. 
However if they had done this just once, feedback usually was very positive - and surprised by how friendly and helpful 
in the free software community generally are.
