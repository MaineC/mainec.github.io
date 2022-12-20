---
title: "Tomcat Tuesday talk"
date: 2009-05-21T09:07:43+02:00
tags: [Free Software,Software Foundation,tomcat,Event,]
---

# Tomcat Tuesday talk


Since several months at neofonie we have a talk given by external or internal developers on various subjects each 
Tuesday. Usually these presentations are a nice way to get an overview of new emerging technologies, to get an overview 
of current conference topics or to gain insight into interesting internal projects.<br><br>This week we had Apache 
Tomcat Committer and PMC Peter Rossbach here at neofonie to talk about the Tomcat architecture and Tomcat clustering 
solutions. He gave two pretty in-depth presentations on the Tomcat internals, Tomcat optimization and extension 
points.<br><br>Some points that were especially interesting to me: The project started out in the late nineties, 
initiated by a bunch of developers who just wanted to see what it takes to write a web application container and that 
fullfills the spec. The goal basically was a reference implementation. Soon enough however users defined the resulting 
code as production ready and used it.<br><br>There are a few caveats from this history that are still visible. One is 
the lack of tests in the codebase. Sure, each release is tested agains the Sun TCK - but these tests cannot be opened 
to the general public. So if you as a developer make extensions or modifications to the code base there is no easy way 
of knowing whether you broke something or not.<br><br>For me as a developer it was interesting to see really how 
complex it quickly gets to cluster tomcat deployments and make them failure resistant. Some tools mentioned that help 
automatic with easier deployment are Puppet and FAI. One issue however that is still on the developer's agenda is 
Tomcat monitoring.<br><br>To summarize: The conference room was packed with developers expecting two very interesting 
talks. Thanks to Peter Rossbach for coming to neofonie and explaining more on the internals of the Tomcat software, the 
project and the community behind.
