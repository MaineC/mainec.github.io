---
title: "Apache Hadoop in Debian Squeeze"
date: 2010-07-17T12:04:27+02:00
tags: [hbase,Zookeeper,Hadoop,Debian,]
---

# Apache Hadoop in Debian Squeeze


After using Mandrake for quite a while (still blaming my boyfriend <a href="http://entropiesenke.de">Thilo</a> for 
infecting not only my computer but also myself first with that system, then with the more general idea of Free Software 
- but that's another story.) after finishing my master's thesis I started using GNU Debian Linux (back then in the 
version code-named Woody). Since I always had a GNU Debian on my private box as my main operating system - even 
installed it on my MacBook following the steps in the <a href="http://wiki.debian.org/MacBook">Debian 
Wiki</a>.<br><br>As I am also an Apache Mahout committer, closely related to the Apache Hadoop project, I always found 
it kind of sad that there were no Hadoop packages in the official Debian repositories. I tried multiple times to find 
some time to get into Debian packaging myself, I learned what "debian/rules" is all about and discovered some of the 
intricacies of packaging Java based software. However I have to admit that I never was able to find enough time to 
really finish that task.<br><br>A few weeks before this year's <a href="http://fosdem.org/2010/">FOSDEM</a> I learned 
on the Apache Hadoop as well as on the Debian Java lists that a guy called Thomas Koch was working on solving bug <a 
href="http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=535861">535861 - ITP to package Hadoop</a>. We met at FOSDEM 
where I tried to raise some attention in the audience for Thomas' plans (back then he was in need for help with a few 
last missing pieces). In addition I invited him for Berlin Buzzwords to get in touch with other Hadoop developers and 
users for further input.<br><br>I am really happy that by now Hadoop has made it into the official Debian package 
repositories - as soon as Debian <a 
href="http://en.wikipedia.org/wiki/List_of_Toy_Story_characters#Squeeze_Toy_Aliens">Squeeze</a (currently at testing) 
gets released, installing Hadoop on your Debian box will be as easy as issuing <code>apt-get install [Hadoop component 
you need]</code>: <a 
href="http://packages.debian.org/search?keywords=hadoop&searchon=names&suite=testing&section=all">Debian package 
search</a>. <br><br><a href="http://www.flickr.com/photos/jemsphotos/522064956/"><img 
src="http://isabel-drost.de/Bilder/wordpress/squeeze.jpg" alt="Squeeze" /></a><br><br>If you want to speed up the 
process of Squeeze being released as stable version: Help fixing the remaining bugs in that distribution. There are 
various <a href="http://wiki.debian.org/BSPMarathonSqueeze">Debian Bug Squashing Parties</a> being organised around the 
world. Next one in Berlin is on <a href="http://wiki.debian.org/BSP2010/Berlin">next Monday</a>, the one for Munich is 
running <a href="http://wiki.debian.org/BSP2010/Munich">this weekend</a>. Just got the information that <a 
href="http://blog.fefe.de/?ts=b2be2d29">Fefe posted in his blog</a> a link to the <a 
href="http://www.mozilla.org/security/bug-bounty.html">Mozilla bug bounty</a>: <br><br>The packages are based on the 
upstream Apache Hadoop distribution, being comparably new they are intended for development machines at the moment. If 
you are using Debian and want to work with Hadoop - this is a great opportunity to help making the packages more stable 
by simply using them and reporting your experiences back to the Debian community.<br><br>In addition Debian now also 
provides packages for Zookeeper as well as HBase - though the HBase version is not yet production ready as the 
HDFS-append patch is still missing.<br><br>To follow the general state and progress of these packages feel free to 
follow the packages pages for <a href="http://packages.qa.debian.org/h/hadoop.html">Hadoop</a>, <a 
href="http://packages.qa.debian.org/h/hbase.html">HBase</a>, <a 
href="http://packages.qa.debian.org/z/zookeeper.html">Zookeeper</a> respectively.<br><br>Thomas currently plans to work 
more closely with upstream e.g. to tidy up the chaos in the start-up scripts and other minor glitches. So watch out for 
further improvements.<br><br>In addition I just saw another interesting <a href="">ITP</a> in the Debian bugtracker: <a 
href="http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=561948">Wishlist: katta</a>. I am sure there are quite a few 
others as well.<br><br>
