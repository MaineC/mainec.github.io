---
title: "GeeCon - failing software projects fast and rapidly"
date: 2012-05-23T08:04:56+02:00
tags: [management,Scrum,Free Software,geecon,]
---

# GeeCon - failing software projects fast and rapidly


My second day started with a talk on how to fail projects fast and rapidly. There are a few tricks to do that that 
relate to different aspects of your project. Lets take a look at each of them in turn.<br><br>The first measures to 
take to fail a project are organisational really: <br><ul><br><li>Refer to developers as resources – that will 
demotivate them and express that they are replaceable instead of being valuable human beings.<br><li>Schedule meetings 
often and make everyone attend. However cancel them on short notice, do not show up yourself or come 
unprepared.<br><li>Make daily standups really long – 45min at least. Or better yet: Schedule weekly team meetings at a 
table, but cancel them as often as you can.<br><li>Always demand Minutes of Meeting after the meeting. (Hint: Yes, they 
are good to cover your ass, however if you have to do that, your organisation is screwed anyway.)<br><li>Plans are 
nothing, planning is everything – however planning should be done by the most experienced, estimation does not have to 
happen collectively (that only leads to the team feeling like they promissed something), rather have estimations be 
done by the most experienced manager.<br><li>Control all the details, assign your resources to tasks and do not let 
them self-organise.<br></ul><br><br>When it comes to demotivating developers there are a few more things than the 
obvious critizing in public that will help destroy your team culture:<br><ul><br><li>Don't invest in tooling – the 
biggest screen, fastest computer, most comfortable office really should be reserved for those doing the hard work, 
namely managers.<br><li>Make working off-site impossible or really hard: Avoid having laptops for people, avoid setting 
up workable VPN solutions, do not open any ssh ports into your organisation.<br><li>Demand working overtime. People 
will become tired, they'll sacrifice family and hobbies, guess how long they will remain happy coders.<br><li>Blindly 
deploy coding standards across the whole company and have those agreed upon in a committee. We all know how effective 
committee driven design (thanks to Pieter Hintjens for that term) is. Also demand 100% test coverage, forbid test 
driven development, forbid pair programming, demand 100% Junit coverage. <br><li>And of course check quality and 
performance as the very last thing during the development cycle. While at that avoid frequent deployments, do not let 
developers onto production machines – not even with read only access. Don't do small releases, let alone continuous 
deployment.<br><li>As a manager when rolling out changes: Forget about those retrospectives and incremental change. 
Roll out big changes at a time.<br><li>As a team lead accept broken builds, don't stop the line to fix a build – rather 
have one guy fix it while others continue to add new features.<br></ul><br><br>When it comes to architecture there are 
a few certain ways to project death that you can follow to kill development:<br><ul><br><li>Enforce framework usage 
across all projects in your company. Do the same for editors, development frameworks, databases etc. Instead of using 
the right tool for the job standardise the way development is done.<br><li>Employ a bunch of ivory tower architects 
that communicate with UML and Slide-ware only.<br><li>Remember: We are building complex systems. Complex systems need 
complex design. Have that design decided upon by a committee.<br><li>Communication should be system agnostic and 
standardised – why not use SOAP's xml over http?<br><li>Use Singletons – they'll give you tightly coupled systems with 
a decent amount of global state.<br></ul><br><br>When it comes to development we can also make life for developers very 
hard:<br><ul><br><li>Don't establish best practices and patterns – there is no need to learn from past 
failure.<br><li>We need not definition of done – everyone knows when something is done and what in particular that 
really means, right?<br><li>We need not common language – in particular not between developers and business 
analysts.<br><li>Don't use version control – or rely on Clear Case.<br><li>Don't do continuous integration.<br><li>Have 
no code ownership – in contrast have a separate module modified by a different developer and forbid others to 
contribute. That leaves us with a nice bus factor of 1.<br><li>Don't do pair programming to spread the knowledge. See 
above.<br><li>Don't do refactoring – rather get it right from the start.<br><li>Don't do non-functional requirements – 
something like “must cope with high load” is enough of a specification. Also put any testing at the end of the 
development process, do lots of manual testing (after all machines cannot judge quality as well as humans can, right?), 
post-pone all difficult pieces to the end, with a bit of luck they get dropped anyway. Also test evenly – there is no 
need to test more important or more complex pieces heavier than others.<br></ul><br>Disclaimer for those who do not 
understand irony: The speaker Thomas Sundberg is very much into the agile manifesto, agile principles and xp values. 
The fun part of irony is that you can turn around the meaning of most of what is written above and get some good advise 
on not failing your projects.<br>
