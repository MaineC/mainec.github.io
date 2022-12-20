---
title: "FOSDEM - Django"
date: 2011-02-16T20:17:38+01:00
tags: Django,Brussels,Fosdem,General,
---

# FOSDEM - Django


<p>The languages/ cloud computing track on Sunday started with the good, the bad and the ugly of Django's architecture. 
Without much ado the speaker started by giving a high level overview of the general package layout of Django - 
unfortunately not going into too much detail on the architecture itself.</p><p>What he loves about Django are the model 
layer abstractions that really are no ORM only - instead both relational and non-relational databases can be supported 
easily. Abstractions in Django are made by task solved - there are multiple implementations available for caching, 
mailing, session handling etc. There is great geo support with options for defining geo objects, querying single points 
on a map for all their overlaying geo objects. Being a community of test driven people Django features awesome 
debugging and testing tools. To avoid cross side request forgery Django comes with built in protection 
mechanisms.</p><p>There is multi database support for building applications. Being a small core implementation features 
can be turned on and off as needed. In addition the framework comes with great documentation: No feature addition is 
accepted unless it comes with decent documentation - which fits nicely with the common perception that anything that is 
untested and undocumented does not exist.</p><p>The bad things about Django according to the speaker? Well, the old 
CSRF protection implementation that might lead to token leakage. Schema changes and migrations currently really are 
hard to handle. Though there is south to handle at least some of the migrations pain. The templating implementation 
could use some improvement as well - being designed to make inclusion of logic in the templates hard some use cases are 
just to clumsy to implement.</p><p>As for the ugly things: There is quite a bit of magic at work which generally leads 
to harder tracing of applications - that is about to get better. Too many parts of Django rely on unwieldy regular 
expressions. Anything that spans more than 4 lines on a screen probably is to be considered unmanageable and 
unchangeable. Authentication cannot really be customised - the information that is stored per user is hard coded and 
fixed.</p><p>Over time what was learned: Refactoring cannot be avoided as requirements change. However being consistent 
in what you do makes it so much easier for users to pick up the framework. What helps with creating a great open source 
project: People that have the time to invest - never under estimate the time needed to really go from prototype to 
production ready.</p>
