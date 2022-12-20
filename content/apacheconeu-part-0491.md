---
title: "ApacheConEU - part 04"
date: 2012-11-13T20:46:01+01:00
tags: ApacheCon,Apache Con,Hadoop,apacheconeu,
---

# ApacheConEU - part 04


The second talk I went to was the one on the <a 
href="http://www.slideshare.net/steve_l/inside-hadoopdev">dev@hadoop.a.o insights given by Steve Loughran</a>. 
According to Steve Hadoop has turned into what he calls an operating system for the data center - similar to Linux in 
that it's development is not driven by a vendor but by its users: Even though Hortenworks, Cloudera and MapR each have 
full time people working on Hadoop (and related projects), this work usually is driven by customer requirements which 
ultimately means that someone is running a Hadoop cluster that he has trouble with and wants to have fixed. In that 
sense the community at large has benefitted a lot from the financial crisis that Y! has slipped into: Most of the 
Hadoop knowledge that is now spread across companies like Linked.In, Facebook and others comes from engineers leaving 
Y! and joining one of those companies. With that also the development cycle of Hadoop has changed: While it was mostly 
driven by Y! schedule in the beginning - crunching out new releases nearly on a monthly basis with a dip around 
Christmas time it's got more irregular later - to pick up a more regular schedule just recently.<br><center><br><img 
src="http://isabel-drost.de/Bilder/wordpress/apache_2013_3.jpg"/><br><br>Image taken a few talks earlier in the same 
session.<br></center><br><br>In terms of version numbers: 1.x is to be considered stable, production ready with fixes 
and low risk patches applied only. For 2.x the picture is a bit different - currently that is in alpha stage, features 
and fixes go there first, new code is developed there first. However Hadoop is not just http://hadoop.apache.org - the 
ecosystem is much larger including projects like Mahout, Hama, HBase and Accumulo built on top of Hadoop and Hive, Pig, 
Sqoop and Flume for integraion and analysis, as well as oozie for coordination an zookeeper for distributed 
configuration. There's even more in incubation (or just recently graduated): Kafka for logging, whirr for cloud 
deployment, giraph for graph processing, ambari for cluster management, s4 for distributed stream processing, hcatalog 
and templeton for schema management, chuckwa for loggin purposes. All of the latter ones love helping hands. If you 
want to help out and want to "play Apache" those are the place to go to.<br><br>With such a large ecosystem one of the 
major pain points when rolling out your own Hadoop cluster is integrating all components you need: All projects release 
on separate release schedules, usually documenting against which version of Hadoop they were built. However finding a 
working combination is not always trivial. The first place to go to that springs to mind are the standard Linux 
distributions - however for their release and support cycles (e.g. Debian's guarantees for stable releases) the pace 
inside of Hadoop and the speed with which old versions were declared "no longer supported" still is too fast. So what 
alternatives are there? You can go with Cloudera who ship Apache Hadoop extended with their patches and additional 
proprietary software. You can opt for Hortenworks that ships the ASF Hadoop only. Or you can opt for Apache itself and 
either tame the zoo yourself or rely on BigTop that aims to integrate the latest versions.<br><br>Even though there are 
people working fulltime on the project there's still way more work to do than hands to help out. Some issues do fall 
through the cracks, in particular if you are the only person affected by the issue. Ultimately this may mean that if 
the bug only affects you you will have to be the one to fix the issue. Before going out and hacking the source itself 
it may make sense to go out and search for the stack trace you are looking at, the error message in front of you - look 
in JIRA and on the mailing list archives to see if there's someone else who has solved the problem already - and in an 
ideal case even provided a patch that just didn't make it into the distribution so far.<br><br>Also contributing to 
Hadoop is a great way to get to work on CS hard problems: There's distributed computing involved (clearly), there's 
consensus implementations like Paxos, there's work to optimise Hadoop for specific CPU architectures, there's 
scheduling and data placement problems to solve, machine learning and graph algorithm implementations and more. If you 
are into these topics - come and join, those are highly needed skills. People on the list tend to be friendly - they 
are "just" overloaded.<br><br>Of course there are barriers to entry - just like the Linux kernel Hadoop has become 
business critical for many of its users. Steve's recommendation for dealing with this circumstance was to not compete 
with existing work that is being done - instead either concentrate on areas that aren't covered yet or even better yet 
collaborate with others. A single lonely developer just cannot reasonably compete.<br><br>In terms of commit process 
Hadoop is running a review-than-commit protocol. Also it makes things seemingly more secure it also means that the 
development process is a lot slower, that things get neglected, that there is a lot of frustration also on the 
committers' side when having to update a patch oftentimes. In addition tests running for a long time doesn't make 
contributing substancially easier. With lots of valuable and critical data being stored in HDFS makeing radical changes 
there also isn't something that happens easily. The best way to really get started is to get trusted and have a track 
record: The maintanance cost for abandoned patches that are large, hard to grasp and no longer supported by the 
original author is just to high.<br><br>Get a track record by getting known on dev@ and meetups. Show your knowledge by 
helping out others, help with patches that are not your own, don't rewrite core initially, help with building plug-in 
points (like for shuffling implementations), help with testing across the whole configuration space, testing in unusual 
settings. Delegate the test at scale to those that have the huge clusters - there will always be issues revealed in 
their setup that do not cause any problems on a single machine or in a tiny cluster. Also make sure to download the 
package in the beta phase and test that it works in your problem space. Another way to get involved is by writing 
better documentation - either online or as a book. Share your experience. <br><br>One major challenge is work on major 
refactorings - there is the option to branch out, switch to a commit-than-review model but that only post-pones work to 
merge time. For independent works it's even more complicated to get the changes in. Also integrating post graduate work 
that can be very valuable isn't particularly simple - especially if there already is a lack in helping hand s- who's 
going to spend the work to mentor those students.<br><br>Some ideas to improve the situation would b the help with 
spreading the knowledge - in local university partnerships, google hangouts, local dev workshops, using git and gerrit 
for better distributed development and merging.
