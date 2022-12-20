---
title: "Agile, inner source, open development, open source development"
date: 2017-05-07T17:53:53+02:00
tags: agile, lean, inner source, open development, apache way, open source development 
categories: Hacking people
---

# Agile, inner source, open development, open source development


Last week I had the honour of giving a keynote at Adobe's Open Source Summit EU
in Basel. Among many interesting talks they hosted a panel to answer questions
around all things open source, strategy, inner source, open development. One
of the questions I found intersting is how inner source/ open development and
agile are related.

<br><br>
To get everyone on the same page, what do I mean when talking about inner
source/ open development? I first encountered the concept at ApacheCon EU
Amsterdam in 2008: Bertrand Delacretaz, then Day Software, now Adobe was talking
about how to apply open source development principles in a corporate
environment. A while ago I ran across the term 
http://innersourcecommons.org that essentially wants to
achieve the same thing. What I find intersting about it is the idea of applying
values like transparency, openess to contributions as well as concepts like
asynchronous communication and decision making at a wider context.

<br><br>
What does that have to do with Agile? Looking at the mere mechanics of Agile
like being co-located, talking face to face frequently, syncing daily in in
person meetings this seems to be pretty much opposite of what open source teams
do.

<br><br>
Starting with the values and promises of Agile though I think the two can
compliment each other quite nicely:

<br><br>
"Individuals and interactions over processes and tools" - there's a saying in
many successful popular projects that the most important ingredient to a
successful open source project is to integrate people into a team working
towards a shared vision. Apache calls this Community over code, ZeroMQ's C4
calls it "People before code", I'm sure there are many other incarnations of the
same concept.

<br><br>
Much like in agile, this doesn't mean that tools are neglected alltogether.
Git was created because there was nothing quite like this tool before. However
at the core of it's design was the desire for ideal support for the way the
Linux community works together.

<br><br>
"Working software over comprehensive documentation" - While people strive for
good documentation I'd be so bold as to suggest that for the open source
projects I'm familiar with the most pressing motivation to provide good
documentation is to lower the number of user questions as well as the amount of
questions people involved with the project have to answer.

<br><br>
For projects like Apache Lucene or Apache httpd I find the documentation
that comes with the project to be exceptionally good. In addition both projects
are supported with dead tree documentation even. My guess would be that working
on geographically distributed teams who's members work on differing schedules
is one trigger for that: Given teams that are geographically distributed over
multiple time zones means that most communication will happen in writing anyway.
So instead of re-typing the same answers over and over, it's less cost intensive
to type them up in a clean way and post them to a place that has a stable URL
and is easy to discoveri. So yes, while working software clearly is still in
focus, the lack for frequent face to face communication can have a positive
influence on the availability of documentation.


<br><br>
"Customer collaboration over contract negotiation" - this is something open
source teams take to the extreme: Anybody is invited to participate. Answers to
feature requests like "patches welcome" typically are honest requests for
support and collaboration, usually if taken up resulting in productive work
relationships.


<br><br>
"Responding to change over following a plan" - in my opinion this is another
value that's taken to the extreme in open source projects. Without control over
your participants, no ability to order people to do certain tasks and no
influence over when and how much time someone else can dedicate to a certain
task reaciting to changes is core to each open source project cosisting of more
than one maintaining entity (be it single human being or simply one company
paying for all currently active developers).


<br><br>
One could look further, digging deeper into how the mechanics of specific Agile
frameworks like Scrum match against what's being done in at least some open
source projects (clearly I cannot speak for each and ever project out there
given that I only know a limited set of them), but that's a topic for a another post.


<br><br>
The idea of applying open source development practices within corporations has
been hanging in the air for over 15 years, driven by different individuals over
time. I think now that people are gathering to collect these ideas in one place
and role them out in more corporations discussions around the topic are going to
become interesting: Each open source community has their own specifics of
working together, even though all seem to follow pretty much the same style when
looked at from very high above. I'm curious to what common values and patterns
can be derived from that which work across organisations.
