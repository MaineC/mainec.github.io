---
title: "Linux vs. Hadoop - some inspiration?"
date: 2013-01-16T20:22:14+01:00
tags: Hadoop,brainstorming,standardisation,Linux,desgin,Hacking,
---

# Linux vs. Hadoop - some inspiration?


<blockquote>This (even for my blog’s standards) long-ish blog post was inspired by a talk given late last year at 
Apache Con EU as well as from discussions around what constitutes “Apache Hadoop compatibility” and how to make 
extending Hadoop easier. The post is based on conversations with at least <a href=”http://thilo-fromm.de”>one guy close 
to the Linux kernel community</a> and <a href=”http://steveloughran.blogspot.com/”>another developer working on 
Hadoop</a>. Both were extremly helpful in answering my questions and sanity checking the post below. After all I’m 
neither an expert on Linux kernel development and design, nor am I an expert on the detailed design and implementation 
of features coming up in the next few Hadoop releases. Thanks for your input.<br><br>Posting this here as I thought the 
result of my trials to understand the exact design commonalities and differences better might be interesting for others 
as well. Disclaimer: This is by no means an attempt to influence current development, it just summarizes some recent 
thoughts and analysis. As a result I’m happy about comments pointing out additions or corrections - preferably as 
trackback or maybe <a href="https://plus.google.com/118318306940098889940/posts/GPdz4C5v9tK">on Google Plus</a> as I 
had to turn of comments on this very blog for spamming reasons.</blockquote><br><br><br>In his slides on “Insides 
Hadoop dev” during Apache Con EU:<br><center><iframe src="http://www.slideshare.net/slideshow/embed_code/15048604" 
width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid 
#CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe> <div 
style="margin-bottom:5px"> <strong> <a href="http://www.slideshare.net/steve_l/inside-hadoopdev" title="Inside 
hadoop-dev" target="_blank">Inside hadoop-dev</a> </strong> from <strong><a href="http://www.slideshare.net/steve_l" 
target="_blank">Steve Loughran</a></strong> </div></center><br><br>Steve Loughran included a comparison that popped up 
rather often already in recent past but still made me think:<br><br><blockquote>“Apache Hadoop is an OS for the 
datacenter”</blockquote><br><br>It does make a very good point, even though being slightly misleading in my 
opinion:<br><br><ul><br><li>There are lots of applications that need to run in a datacenter that do not imply having to 
use Hadoop at all - think mobile application backends, content management systems of publishers, encyclopedia hosting. 
Growing you may still run into the need for central log processing, scheduling and storing data.<br><li>Even if your 
application benefits from a Hadoop cluster you will need a zoo of other projects not necessarily related to the project 
to successfully run your cluster - think configuration management, monitoring, alerting. Actually many of these topics 
are on the radar of Hadoop developers - with an intend to avoid the NIH principle and rather integrate better with 
existing proven standard tools.<br></ul><br><br>However if you do want to do large scale data analysis on largely 
unstructured data today you will most likely end up using Apache Hadoop.<br><br>When talking about operating systems in 
the free software world inevitably the topic will drift towards the Linux kernel. Being one the most successful free 
software projects out there from time to time it’s interesting and valuable to look at its history and present in terms 
of development process, architecture, stakeholders in the development cycle and the way conflicting interests are being 
dealt with.<br><br>Although interesting in many dimensions this blog post focuses just on two related aspects: 
<br><br><ul><br><li>How to balance innovation for stability in critical parts of the system.<br><li>How to deal with 
modularity and API stability from an architectural point of view taking project-external (read: non-mainline) module 
contributions into account.<br></ul><br><br>The post is not going to deal with just “everything map/reduce” but focus 
solely on software written specifically to work with Apache Hadoop. In particular Map/Reduce layers plugged on top of 
existing distributed file systems that ignore data locality guarantees as well as layers on top of existing relational 
database management systems that ignore easy distribution and fail over are intentionally being 
ignored.<br><br><h2>Balancing innovation with stability</h2><br><br>One pain point mentioned during Steve’s talk was 
the perceived need for a very stable and reliable HDFS that prevents changes and improvements from making it into 
Hadoop. The rational is very simple: Many customers have entrusted lots (as in not easy to re-create in any reasonable 
time frame) of critical (as in the service offered degrades substantially when no longer based on that data) data to 
Hadoop. Even when in a backup Hadoop going down for a file system failure would still be catastrophic as it would take 
ages to get all systems back to a working state - time that means loosing lots of customer interaction with the service 
provided.<br><br>When glancing over to Linux-land (or Windows, or MacOS really) the situation isn’t much different: 
Though both backup and recovery are much cheaper there, having to restore a user’s hard-disk just due to some weird 
programming mistake still is not acceptable. Where does innovation happen there? Well, if you want durability and 
stability all you do is to use one of the well proven file system implementations - everyone knows names like ext2, xfs 
and friends. A simple “man mount” will reveal many more. If on the contrary you need some more cutting edge features or 
want to implement a whole new idea of how a file system should work, you are free to implement your own module or 
contribute to those marked as EXPERIMENTAL.<br><br>If Hadoop really is the OS of the datacenter than maybe it’s time to 
think about ways that enable users to swap in their prefered file system implementation, maybe it’s time for developers 
to focus implementation of new features that could break existing deployed systems to separate modules. Maybe it’s time 
to announce an end-of-support-date for older implementations (unless there are users that not only need support but are 
willing to put time and implementation effort into maintaining these old versions that is.)<br><br><h2>Dealing with 
modularity and API stability</h2><br><br>With the vision of being able to completely replace whole sub-systems comes 
the question of how to guarantee some sort of interoperability. The market for Hadoop and surrounding projects is 
already split, it’s hard to grasp for outsiders and newcomers which components work with wich version of Hadoop. Is 
there a better way to do things?<br><br>Looking at the Linux kernel I see some parallels here: There’s components built 
on top of kernel system calls (tools like ls, mkdir etc. all rely on a fixed set of system calls being available). On 
the other hand there’s a wide variety of vendors offering kernel drivers for their hardware. Those come in three 
versions:<br><br><ul><br><li>Some are distributed as part of the mainline kernel (e.g. those for Intel graphics 
cards).<br><li>Some are distributed separately but including all source code (e.g. ….)<br><li>Some are distributed as 
binary blog with some generic GPLed glue logic (e.g. those provided by NVIDIA for their graphics 
cards).<br></ul><br><br>Essentially there are two kinds of programming interfaces: ABIs (Application Binary Interfaces) 
that are being developed against from user space applications like “ls” and friends. APIs (Application Programming 
Interfaces) that are being developed against by kernel modules like the one by NVIDIA.<br><br>Coming back to Hadoop I 
see some parallelism here: There are ABIs that are being used by user space applications like “hadoop fs -ls” or your 
average map/reduce application. There are also some sort of APIs that strictly only allow for communication between 
HDFS, Map/Reduce and applications on top.<br><br>The Java ecosystem has a history of having APIs defined and 
standardised through the JCP and implemented by multiple vendors afterwards. With Apache projects people coming from a 
plain Java world often wonder why there is no standard that defines the APIs of valuable projects like Lucene or even 
Hadoop. Even log4j, commons logging and build tooling follow the “defacto standardisation” approach where development 
defines the API as opposed to a standardisation committee.<br><br>Going one step back the natrual question to ask is 
why there is demand for standardisation. What are the benefits of having APIs standardised? Going through a lengthy 
standardisation process obviously can’t be the benefit.<br><br>Advantages that come to my mind:<br><ul><br><li>When 
having multiple vendors involved that do not want to or cannot communicate otherwise a standardisation committee can 
provide a neutral ground for communication in particular for the engineers involved.<br><li>For users there is some 
higher level document they can refer to in order to compare solutions and see how painful it might be to 
migrate.<br></ul><br><br>Having been to a DIN/ISO SQL meetup lately there’s also a few pitfalls that I can think 
of:<br><ul><br><li>You really have to make sure that your standard isn’t going to be polluted with things that never 
get implemented just because someone thought a particular feature could be interesting.<br><li>Standardisation usually 
takes a long time (read: mutliple years) until something valuable that than can be adopted and implemented in the 
industry is created.<br></ul><br><br>More concerns include but are not limited to the problem of testing the standard - 
when putting the standard into main focus instead of the implementation there is a risk of including features in the 
standard that are hard or even impossible to implement. There is the risk of running into competing organisations 
gaming the system, making deals with each other - all leading to compromises that are everything but technologically 
sensible. There clearly is a barrier to entry when standardisation happens in a professional standards body. (On a 
related note: At least the German group working on the DIN/ISO standard defining the standard query language in 
particular in big data environments. Let me know if you would like to get involved.)<br><br>Concerning the first 
advantage (having some neutral ground for vendors to meet): Looking at your average standardisation effort those 
committees may be neutral ground. However communication isn’t necessarily available to the public for whatever reasons. 
Compared to the situation little over a decade ago there’s also one major shift in how development is done on 
successful projects: Software is no longer developed in-house only. Many successful components that enable productivity 
are developed in the open in a collaborative way that is open to any participant. Httpd, Linux, PHP, Lucene, Hadoop, 
Perl, Python, Django, Debian and others are all developed by teams spanning continents, cultures and most importantly 
corporations. Those projects provide a neutral ground for developers to meet and discuss their idea of what an 
implementation should look like.<br><br>Pondering a bit more on where successful projects I know of came from reveals 
something particularly interesting: ODF first was implemented as part of Open Office and then turned into a 
standardised format. XMPP was first implemented and than turned into an IETF standardised protocol. Lucene never went 
for any storage format or even search API standardisation but defined very rigid backwards compatibility guidelines 
that users learnt to trust. Linux itself never went for ABI standardisation - instead they opted for very strict ABI 
backwards compat guidelines that developers of user space tools could rely on.<br><br>Looking at the Linux kernel in 
particular the rule is that user facing ABIs are supposed to be backwards compatible: You will always be able to run 
yesterday’s ls against a newer kernel. One advantage for me as a user is that this way I can easily upgrade the kernel 
in my system without having to worry about any of the installed user space software.<br><br>The picture looks rather 
different with Linux’ APIs: Those are intentionally not considered holy and subject to change if need be. As a result 
vendors providing proprietary kernel driver like NVIDIA have the burden of providing updated versions in case they want 
to support more than one kernel version.<br><br>I could imaging a world similar to that for Hadoop: A world in which 
clients run older versions of Hadoop but are still able to talk to their upgraded clusters. A world in which older 
MapReduce programs still run when deployed on newer clusters. The only people who would need to worry about API 
upgrades would be those providing plugins to Hadoop itself or replace components of the system. According to Steve this 
is what YARN promises: Turn MR into user layer code, have the lower level resource manager for requesting machines near 
the data.
