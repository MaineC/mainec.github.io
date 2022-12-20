---
title: "Talking people into submitting patches - results"
date: 2012-01-01T18:42:16+01:00
tags: [Apache,Open Source,contributing,Apache Con,]
---

# Talking people into submitting patches - results


Back in November I gave a talk at Apache Con NA in Vancouver on talking friends and colleagues into contributing 
patches to open source projects. The intended audience for this talk were experienced committers to Apache projects, 
the goal was to learn more on their tricks for talking people into patching. First of all thanks for an interesting 
discussion on the topic - it was great to get into the room with barely enough slides to fill 10 min and still have a 
lively discussion 45min later.<br><br>For the impatient - the written feedback is <a 
href="https://docs.google.com/document/d/1BUFAM-gPAeI2RLx-fpmsfIHgnhKimVa7D8xUgcHU-9c/edit">available as Google 
Doc</a>. Most common advise I heard involved patience, teaching, explaining, fast feedback and reward.<br><br>One 
warning before going into more detail on the talk: All assumptions and observations stated are highly subjective, 
influenced by my personal experience or by whatever the experience of the audience was. Do not expect an objective, 
balanced, well research analysis of the problems in general. That said, lets start with the talk itself. Before the 
talk I decided to limit scope to getting people in that have limited experience with open source. That intentionally 
excluded anyone downstream projects depending on one's code. Though in particular interaction with common Linux 
distributions and their package maintainers is vital, that issue warrants for a separate talk and discussion.<br><br>I 
divided those inexperienced with open source into three groups to keep discussion somewhat focused: 
<br><ul><br><li>Students learning about open source projects during their education and have neither background in 
software engineering nor in open source but are generally very eager to lean and open to new ideas.<br><li>Researchers 
learning about the concept as part of a research grant who have some software engineering experience, some experience 
with open source - in particular with using it - but in general do not have writing open source software as their main 
objective, but have to participate as part of their research grant.<br><li>Software engineers having experience with 
software engineering, some experience in particular with using open source and in general both strong opinions on what 
the right way of doing things is and  who have a strong position in their team that helps them in no way when starting 
to contribute.<br></ul><br><br><h2>One very common way</h2><br><br>To understand some of the issues below let me first 
highlight what seems to be the most common way to become involved with any Apache project: Usually it starts with using 
one of their software packages. After some time what is shipped does no longer fit your needs, reveals bugs that stop 
you from reaching your goals or is missing one particular feature - even if that is just one particular method being 
protected instead of private.<br><br>People fix those issues. As the best software developers are utterly lazy the 
contribute stuff back to the project to avoid the work of having to maintain their private fork just for some simple 
modification. The more features of  a project are being used, the more likely it gets that also larger contributions 
become possible. Overall this way of selecting issues to fix has a lot to do with scratching your own itch. In the end 
this kind of issue prioritisation also influences the general direction of a project: Whatever is most important to 
those actively contributing is driving the design and development. So the only way to change a project's direction to 
better fit your needs is to start getting active yourself: Those that do are the ones that 
decide.<br><br><h2>Students</h2><br><br>Lets take a closer look at students aspiring to work on an open source project. 
They are very keen on contributing new stuff, learning the process and open to new ways of doing things. However for 
the most part they are no active users of the projects they selected so they do not directly see what is important to 
fix. In addition they have only limited software development experience - at least when looking at German universities, 
bug trackers, source version control, build systems, release management, maintaining backwards compatibility, unit test 
frameworks are on no schedule - and most likely shouldn't be neither. So your average student has to learn to deal with 
checking out code, compiling it, getting it into their favourite editor, adding tests and making them 
pass.<br><br>Apart from teaching, giving even simple feedback it helps to provide the right links to literature at the 
right times, and generally mentor students actively. In addition it can be helpful to leave non-critical, easy to fix 
issues open and mark them as "beginner level" to make it easier for new-comers to get started. One last advise: Get 
students to publish what they do as early and as often as possible. Back in the days I used to do projects at TU Berlin 
with the goal of getting students to contribute to Mahout. In the first semester I left the decision on when to open up 
the code to the students - they never went public. In the second semester I forced them to publish progress on a weekly 
basis (and made that part of how their final evaluation was done) - suddenly what was developed turned into a patch 
committed to the code base.<br><br><h2>Researchers</h2><br><br>A second group of people that has an increasing interest 
in open source projects are researchers. In particular for EU project research grant the promise of providing results 
and software developed with the help of European tax-payers money under and open source license has become an important 
plus when asking for project grants.<br><br>However before becoming all too optimistic it might make sense to take a 
closer look: Even though there is an open source check box on your average research grant that by no means leads to 
highly motivated, well educated new contributors for your project: With software development only being a means to 
reach the ultimate goal of influential publications researchers usually do not have the time and motivation to polish 
software to the level needed for a successful and useful contribution. In addition the concept of maintaining your 
contribution for a longer time usually does not fit the timeline and timeframe of a research project.<br><br>Apart from 
teaching and mentoring projects themselves should start asking for the motivation of the contribution. There are a few 
popular arguments to contribute patches back. However not all of them really work for the research use case: The cost 
of maintaining a fork is close to zero if you intend to never upgrade to a new version and do not need security fixes. 
Another common argument is an improved visibility of your work and an improved reputation of yourself as software 
developer. If software development for you is just a means to reach a much higher goal those arguments may not mean 
much to you. A third common argument is that of improving code quality by having more than one pair of eyes review it - 
and where would you get a better review than in the project bringing together the original code authors? However if 
ultimate stability, security and flexibility is not your goal than also that may not mean much to you.<br><br>Key is to 
find out where the interest for working on open source comes from and build up arguments from 
there.<br><br><h2>Software engineers</h2><br><br>The third group I identified was professional software developers - as 
clarified after a question from the audience: Yes, I consider people who are unable to create, read, apply patches as 
professional software developers. If I would exclude these people there would be noone left who earns his living with 
software development and does not already work on open source projects.<br><br>In contrast to the above groups these 
people have extensive software development experience. However that also means that after having seen a lot of stuff 
that works and that does not work they do have a strong position in their teams. Usually those fixing issues in 
libraries they use re the ones that have established work-flows that work for them very well and who are used to being 
pretty influential. When going into an open source community however no-one knows them. In general they are only judged 
based on their patch. They get open feedback - in the context of that project. Projects tend to have established coding 
guidelines, best practices, build systems - that may differ from what you are used to in your corporate 
environment.<br><br>Getting up to speed in such an environment can be intimidating at best in particular if everything 
you do is public, searchable and findable by definition. All the more it is important to get involved and get feedback 
early by even putting online early sketches of what your plan is.<br><br>However with everything being open there is 
also one major positive side to motivating contributors: Give credit where credit is due - add praise to the issue 
tracker by assigning issues to the one providing he patch, add the name of the contributor to your release notes. When 
substantial, mention the contribution with name in talks, presentations and publications.<br><br>Another important 
issue here is the influence of deadlines: If it takes half a year to get feedback on your particular improvement the 
reason why you made it may no longer exist - the project may have been cancelled, the developer moved to a different 
team, the patch applied internally as is fixing the existing issues. Fast feedback on new patches, in particular if 
they are clean and come with tests is vital. One positive example for providing feedback on formal issues quickly is 
the automated review bot at Apache Hadoop: It checks stuff like style, addition of tests, checks against existing tests 
and the like quickly after the patch is submitted in an automated way. Just one nitpick from the audience: The output 
of that bot could be either marked more clearly as "this is automated" or the text formulated a bit friendlier - if a 
human had done the review it would have mentioned the positive things first before criticising what is 
wrong.<br><br>Last but not least (applies to researchers as well), there may be legal issues lurking: Most if not all 
contracts entail that at least what you do during working hours belongs to your employer - so it's up to them what gets 
open sourced and what doesn't. Suddenly your very technical new contributor has to convince management, deal with legal 
departments and work his way through the employers processes - most likely without deep prior knowledge on open source 
licenses - let alone contributor agreements (or did you know what the <a 
href="http://www.apache.org/licenses/cla-corporate.txt">Apache CCLA</a> entails, let alone being able to explain it to 
others before really getting active?)<br><br><h2>General advise</h2><br><br>To briefly summarise the most important 
points:<br><br><ul><br><li>Give feedback fast - projects only run for so long, interest only lasts for so long. The 
faster a contributor is told what is not too great about his patch, the more likely those issues are fixed as part of 
the contribution. (Inspired by Avro and Zookeeper who were amazingly fast in providing feedback, committing and in the 
case of Avro even releasing a fixed version).<br><li>When it comes to new contributors be patient, remain friendly even 
when faced with seemingly stupid mistakes.<br><li>Give credit where credit is due - or could be due. Mention 
contributors in publications, press releases, release notes, the bug tracker. Let them know that you do. (Inspired by 
Drools, Tomcat, Zookeeper, Avro). Pro-tip: Make sure to have no typo in people's names even if checking takes one extra 
minute. (Learned from Otis).<br><li>Use any chance you get to teach the uninitiated about the whole patch process. I 
know that this seems trivial to those who work with open source on a daily basis. However when getting dependencies 
through Maven it may already be cumbersome to figure out where to get the source from. When used to git in the daily 
workflow it may be a hurdle to remember how to checkout stuff from svn ;) Back in June we had a Hadoop Hackathon in 
Berlin that was well attended - mostly by non-committers. Jakob Homan proposed a rather unusual but very well received 
format: In the Hadoop bug tracker there are several issues marked as trivial (typos in documentation and the like). 
Attendees were asked to choose one of these issues, checkout the source, create a patch and contribute it back to the 
project. Optionally they got explained how the process continues from there on the committer side of things. It may 
seem trivial to mechanically go through the patch process, however it help lower the bar in case you have a real issue 
to fix to first get accustomed to just how it works.  If instead of contributing to Apache you are more into working on 
the Linux kernel I'd like to advise you to watch <a href="http://www.youtube.com/watch?v=LLBrBBImJt4">Greg Kroah 
Hartman on writing and submitting your first Linux kernel patch (FOSDEM)</a>.<br><li>Last but not least make sure to 
lower the bar for contribution - do not require people to jump through numerous loops, in general even just getting a 
patch ready is complicated enough. Provide a how to contribute page (e.g. see <a 
href="https://cwiki.apache.org/confluence/display/MAHOUT/How+To+Contribute">how to contribute</a> and <a 
href="https://cwiki.apache.org/confluence/display/MAHOUT/How+To+Become+A+Committer">how to become a committer</a> pages 
in the Apache Mahout wiki.<br><li>In particular when your project is still very young lower the bar by turning 
contributors into committers quickly - even if they are "just" contributing documentation fixes - in my view one of the 
most important contribution there is as only users spot areas for documentation improvement.<br></ul><br><br>In case 
you yourself are thinking about contributing and need some additional advice as to why and for what purposes: Dr Dobbs 
has more information on <a href="http://drdobbs.com/open-source/231000080">reasons why developers tend to start to 
contribute to Apache software</a>, Shalin explains <a 
href="http://shal.in/post/285909694/why-you-should-contribute-to-open-source">why he contributes to open source</a>, on 
the Mahout mailing list we hade a discussion on <a 
href="http://lucene.472066.n3.nabble.com/GSOC-Ranking-Process-td635717.html"> why also students should consider 
contributing</a>, on the Apache community mailing list there was an interesting discussion on <a 
href="http://www.mail-archive.com/community@apache.org/msg04837.html">whether developers working on open source are 
happier than those that don't</a>.
