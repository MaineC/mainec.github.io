---
title: "The 7 deadly sins of (Java) software developers"
date: 2010-01-23T09:09:46+01:00
tags: SwEng,anti-patterns,Scrum,Free Software,Lucene,Hacking,Solr,sin,
---

# The 7 deadly sins of (Java) software developers


On Lucid Imaginations Blog <a href="http://www.lucidimagination.com/blog/author/jay-hill/">Jay Hill</a> published a 
great article on <a href="http://www.lucidimagination.com/blog/2010/01/21/the-seven-deadly-sins-of-solr/">The seven 
deadly sins of solr</a>. Basically it is a collection of his experiences "analyzing and evaluating a great many 
instances of Solr implementations, running in some of the largest Fortune 500 companies". It is a collection of common 
mistakes, mis-configurations and pitfalls in Solr installations in production use.<br><br>I loved the article very 
much. However, many of the symptoms that Jay described in his article do not apply to Solr installations only. In the 
following I will try to come up with a more general classification of errors that occur when your average Java 
developer starts using a sufficiently large framework that is supposed to make his work easier. Happy about any input 
on your favourite production issues.<br><br>Remark: What is printed in italic is quoted as is.<br><br><h2>Sin number 1: 
Sloth - I'll do it later</h2><br><br>Let’s define sloth as laziness or indifference. This one bites most of us at some 
time or another. We just can’t resist the impulse to take a shortcut, or we simply refuse to acknowledge the amount of 
effort required to do a task properly. Ultimately we wind up paying the price, usually with interest. </i><br><br>There 
is even a name for it in Scrum: Technical debt. It may be ok to take a shortcut, given this is done based on an 
informed decision. As with regular debt, you may get a big advantage like launching way earlier than your competitor. 
However as with real debt, it does come at a prize.<br><br><h3>Lack of commitment</h3><br>Jay describes the problems 
that are especially frequent when switching search applications: Humans in general do not like giving up their habits. 
A nice example described in more detail in a recent <a href="http://www.zeit.de/2010/03/Interview-Schlag?page=all">Zeit 
article</a> is what happens each year in December/ January when the first snow falls: It is by no means irregular or 
not to be expected that it starts snowing in December in Germany. However there will be lots of people who are not 
prepared for that. They refuse to put on winter tiers in late autumn. They use their car instead of public transport 
despite warnings in public press. The conclusion of the article was simple: People are simply not willing to change 
habits they got used to. It does take longer and is a bit less flexible to get to work by public transport instead of 
your own car. It does require adjusting your daily routine, optimising your processes.<br><br>Something similar happens 
to a developer that is "forced" to switch technology, be it the search server, the database, the build system or simply 
the version control system: The old ways of doing stuff simply may not work as expected. New tools might be called for. 
New technologies to learn. However in not so seldom cases developers just blame the new tools: "But with the old setup 
this would always work."<br><br>Developing software - probably more than anything else - means constant development, 
constant change. Technologies shift as tasks shift, tools are improved as workflows change. Developing software means 
to constantly watch closely what you are doing, reflecting on what works and what doesn't and changing things that 
don't work. Accepting change, seeing it as a chance rather than an obstacle is critical.<br><br>If however change is 
imposed on developers though good arguments in favour of the old approach exist, it may be worth the effort to at least 
take the technical view into account to make an informed decision.<br><br><h3>Not reviewing, editing, or changing the 
default configuration files.</h3><br>I have extended this one a bit: Developers not changing default configuration 
files are not that uncommon. Be it the default database configuration, default logging configuration for your modules 
or default configuration of your servlet container. Even if you are using software pre-packed by your distribution, it 
is still worth the effort to review configuration files for your services and adjust them to your needs. Usually they 
are to be used as examples that still need tweaking and customization after roll-out.<br><br><h3>JVM settings and 
GC</h3><br>If you are running Java application there is no way around to adjust GC settings as well as general JVM 
settings to your particular use case. There are great tutorials at sun.com that explain both the settings themselves as 
well as several rules-of-thumb of where to start. Still nothing should stop you from measuring your particular 
application and its specific needs - both, before and after tuning. Along with that goes the obvious recommendation to 
simply "know-your-tools" - learning load testing tools shortly before launch time is certainly no good choice. Trying 
to find out more on Java memory analysis late in the development cycle just because you need to find that stupid memory 
leak like *now* is no good idea neither.<br><br>There are several nice talks as well as several tutorials available 
online on the topic of JVM tuning, debugging memory as well as threading issues, one of them being <a 
href="http://streaming.linux-magazin.de/events/froscon08/archive/rjung">the talk by Rainer Jung at Frocson 
2008</a>.<br><br><h2>Sin number 2: Greed</h2><br>Running a service on insufficient hardware (be it main memory, 
harddisks, bandwidth, ...) is not only an issue with Solr installations. There are many cases where just adding 
hardware may help in the short run, but is a dead-end in the long run:<br><ul><br><li>Given a highly inefficient 
implementation, identifying bottlenecks, profiling, benchmarking and optimization go a long way.<br><li> Given an 
inappropriate architecture, redesign, reimplementation and maybe even switching base technologies does 
help.<br></ul><br>However as Jay pointed out, running production servers with less power than your average desktop Mac 
has does not help neither.<br><br><h2>Sin number 3: Pride</h2><br><i>Engineers love to code. Sometimes to the point of 
wanting to create custom work that may have a solution in place already, just because: a) They believe they can do it 
better. b) They believe they can learn by going through the process. c) It “would be fun”. This is not meant to 
discourage new work to help out with an open-source project, to contribute bug fixes, or certainly to improve existing 
functionality. But be careful not to rush off and start coding before you know what options already exist. Measure 
twice, cut once.<br></i><br><br><h3>Don’t re-invent the wheel.</h3><br>As described in Jay's post, there are developers 
who seem to be actively searching for reasons to re-invent the wheel. Sure, this is far easier with open source 
software than with commercial software. Access to code here makes the difference: Understanding, learning from, sharing 
and improving the software is key to free software.<br><br>However there are so many cases where improve does not mean 
re-implement but submitting patches, fixing bugs, adding new features to the orignal project or just refactoring the 
original code and ironing out some well known bumbs to make life easier for others.<br><br>Every now and then a new 
query abstraction language for map reduce pops up. Some of those really solve distinct problem settings that cannot 
(and should not) be solved within one language. Especially if a technology is young, this is pretty usual as people try 
out different approaches to see what works and what does not work out so well. Good and stable things come from that - 
in general the fittest approach survives. However, too often I have heard developers excusing their re-invention by 
"having had too few time to do a throughough evaluation of existing frameworks and libraries". The irony here really is 
that usually, coding up your own solution does take time as well. In other cases the excuse was missing support for 
some of the features needed. How about adding those features, submitting them upstream and benefitting from what is 
already there and an active community supporting the project, testing it, applying fixes and adding further 
improvements?<br><br><h3>Make use of the mailing lists and the list archives.</h3><br>Communication is key to success 
in software development. According to Conway's law "Organizations <br>which design systems are constrained to produce 
systems which are copies of the communication structures of these organizations." I guess it is pretty obvious that 
developing software today generally means designing complex systems.<br><br>In Open source, mailing lists (and bug 
trackers, the code itself, release notes etc.) are all ways for communication. (See also Bertrand's brilliant talk on 
<a href="http://www.youtube.com/watch?v=XdNyzNCRLd8">open source collaboration tools</a> for that). With in-house 
development there is even added benefit as face-to-face communication or at least teleconferencing is possible. 
<br><br>However software developers in general seem to be reluctant to ask questions, to discuss their design, their 
implementation and their needs for changes. It just seems simpler to work-around a situation that disturbs you instead 
of propagating the problem to its source - or just asking for the information you need. A nice article on a related 
topic was published recently <a 
href="http://it-republik.de/jaxenter/artikel/Schatz-was-denkst-du-gerade-%96-Warum-Gedankenlesen-das-Gegenteil-von-Feedb
ack-ist-2867.html">it-republik</a>.<br><br>However asking these questions, taking part in these discussions is what 
makes software better. It is what happens regularly within open source projects in terms of design discussions on 
mailing lists, discussions on focussed issues in the bug tracker as well as in terms of code review.<br><br>There are 
several best practices that come with Agile Development that help starting discussions on code. Pair programming is one 
of these. Code reviews are another example. Having more than two eye balls look at a problem usually makes the solution 
more robust, gives confidence in what was implemented and as a nice side effect spreads knowledge on the code avoiding 
a single point of failure with just one developer being familiar with a particular piece of code.<br><br><h2>Sin number 
4: Lust</h2><br><i>Must have more!You’ll have to grant me artistic license on this one, or else we won’t be able to 
keep this blog G-rated. So let’s define lust as “an unnatural craving for something to the point of self-indulgence or 
lunacy”. OK.</i><br><br><h3>Setting the JVM Heap size too high, not leaving enough RAM for the OS.</h3><br>Jay 
describes how setting the JVM RAM allocation too high can lead to Java eating up all memory and leaving nothing for the 
OS. The observation does not apply to Solr deployments only. Tomcat is just yet another application where this applies 
as well. Especially with IO-bound applications giving too much memory to the JVM is grave as the OS does not longer 
have enough space for disk caches.<br><br>The general take-away probably should be to measure and tune according to the 
real observed behaviour of your application. A second take-home message would be to understand your system - not only 
the Java part of it, but the whole machine from Java, the OS down to the hardware - to tune it effectively. However 
that should be a well known fact anyway. For Java developers, it sometimes helps to simply talk to your operations guys 
to get the bigger picture.<br> <br><h3>Too much attention on the JVM and garbage collection.</h3><br>There are actually 
two aspects here: For one, as described by Jay it should not be necessary to try every arcane JVM or GC setting unless 
you are a JVM expert. More precisely, simply trying various options w/o understanding, what they mean, what 
side-effects they have and in which situations they help obviously isn't a very good idea.<br><br>The second aspect 
would be developers starting with JVM optimization only to learn later on that the real problem is within their own 
application. Tuning JVM parameters really should be one of the last steps in your optimization pipeline. First should 
be benchmarking and profiling your own code. At the same stage you should review configuration parameters of your 
application (size of thread pools, connection pools etc.) as well your libraries and frameworks (here come solr's 
configuration files, Tomcat's configuration, RDBMs configuration parameters, cache configurations...).  Last but not 
least should be JVM tuning - starting with adjusting memory to a reasonable amount, setting the GC configuration that 
makes most sense to your application.<br><br><h2>Sin number 5: Envy</h2><br>Bah!<br><h3>Wanting features that other 
sites have, that you really don’t need.</h3><br>It should be good engineering practice to start with your business 
needs and distill user stories from that and identify the technology that solves your problem. Don't go from problem to 
solution without first having understood your problem. Or even worse: Don't go from solution (that is from a technology 
you would love to use) to searching for a problem that this solution might solve: "But there must be a RDBMS somewhere 
in our architecture, right?"<br><br><h3>Wanting to have a bigger index than the other guy.</h3><br><i>The antithesis of 
the “greed” issue of not allocating enough resources. “Shooting for the moon” and trying to allow for possible growth 
over the next 20 years. </i> Another scenario would be to never fix your system but leave every piece open and 
configurable, in the end leading to a system that is harder to configure than sendmail is.  Yet another scenario would 
be to plan for billions of users before even launching: That may make sense for a new Google gadget, however for the 
"new kid on the block"? Probably unlikely, unless you have really good marketing guys. Plan for what is reasonable in 
your project, observe real traffic and identify real bottlenecks once you see them. Usually estimations of what 
bottlenecks could be are just plain wrong unless you have lot's of experience with the type of application you are 
building. As Jeff Dean pointed out in his <a href="http://research.google.com/people/jeff/WSDM09-keynote.pdf">WSDM 2009 
keynote</a>, the right design for X users may still be right with 10x the amount of users. But do plan a rewrite at 
about the time you start having 100x and more the amount of users. <br><br><h2>Sin number 6: 
Gluttony</h2><br><i>“Staying fit and trim” is usually good practice when designing and running Solr applications. A lot 
of these issues cross over into the “Sloth” category, and are generally cases where the extra effort to keep your 
configuration and data efficiently managed is not considered important.</i><br><br><h3>Lack of attention to field 
configuration in the schema.</h3><br><i>Storing fields that will never be retrieved. Indexing fields that will never be 
searched. Storing term vectors, positions and offsets when they will never be used. Unnecessary bloat. Understand your 
data and your users and design your schema and fields accordingly.</i><br><br>On a more general scale that might be 
wrapped into the general advise of keeping only data that is really needed: Rotate logs on a schedule fit to your 
business, operations needs and based on available machines. Rotate data written into your database backend: It may make 
sense to keep users that did not interact with your application for 10 years. If you have a large datacenter for 
storage that may make even more sense. However usually keeping inactive users in your records simply eats up 
space.<br><br><h3>Unexamined queries that are redundant or inefficient.</h3><br>Queries that catch too much 
information, are redundant or multiple queries that could be folded into one are not only a problem for Solr users. 
Anyone using data sources that are expensive to query probably knows how to optimize those queries for reduced 
cost.<br><br><h2>Sin number 7: Wrath</h2><br><i>Now! While wrath is usually considered to be synonymous with anger, 
let’s use an older definition here: “a vehement denial of the truth, both to others and in the form of self-denial, 
impatience.”</i><br><br><h3>Assuming you will never need to re-index your data.</h3><br>Hmm - don't only backup. 
Include recovery in your plans! Admittedly with search applications, this includes keeping the original documents - it 
is not unusual to add more fields or to want to parse data differently from the first indexing run. Same applies if you 
are post-processing data that has been entered by users or spidered from the web for tasks like information extraction, 
classifier training etc.<br><br><h3>Rushing to production.</h3><br><i>Of course we all have deadlines, but you only get 
one chance to make a first impression. Years ago I was part of a project where we released our search application 
prematurely (ahead of schedule) because the business decided it was better to have something in place rather than not 
have a search option. We developers felt that, with another four weeks of work we could deliver a fully-ready system 
that would be an excellent search application. But we rushed to production with some major flaws. Customers of ours 
were furious when they searched for their products and couldn’t find them. We developed a bad reputation, angered some 
business partners, and lost money just because it was deemed necessary to have a search application up and running four 
weeks early.</i><br><br>Leaving that as is - just adding, this does not apply to search applications only ;)<br><br>So 
keep it simple and separate, stay smart, stay up to date, and keep your application on the straight-and-narrow (YAGNI 
;) ). Seek (intelligently) and ye shall find.
