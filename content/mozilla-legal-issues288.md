---
title: "Mozilla legal issues - FOSDEM 03"
date: 2013-02-15T22:39:35+01:00
tags: oss,mozilla,Fosdem,Event,legal,
---

# Mozilla legal issues - FOSDEM 03


In the next talk Gervase Markham talked about his experience working for Mozilla on legal and license questions. First 
the speaker summarized what kind of requests he gets most:<br><ul><br><li>There are lots of technical support 
requests.<br><li>Next on the top list is the question for whether or not shipping Mozilla with a set of modifications 
is ok.<br><li>Next is an internal question, namely: Can I use this code?<br><li>Related to that is the “We have a 
release in two weeks, can we ship with this code?”<br><li>Another task is finding code that was used but is not 
ok.<br><li>Yet another one is getting code licensed or re-licensed.<br><li>Maintaining the about:license page is 
another task.<br><li>Dealing with ECCV/CCATS requests is another issue that comes up often.<br></ul><br><br>However 
there are also bigger tasks: There was the goal of tri-licensing Mozilla. The only issue was the fact that they had 
accumulated enough individually copyrighted contributions to make that that task really tricky. In the end they wrote a 
tool to pull out all contributor names, send them mails asking for permission to tri-license. After little over three 
years they had responses from all but 30 contributors. As a result the “find this hacker” campaign was launched on /. 
and other news sites. In the end most could be found.<br><br>As another step towards easier licensing the MPL 2 
replacing 1.1 was introduced – it fixes GPL/ASL license incompatibilities, notification and distribution requirements, 
the difference for initial developers and the use of conditional/Jacobson language.<br><br>There are still a few issues 
with source files lacking license headers (general advise that never has been tested in court is the concept of license 
bleeding: If there are files with and without license headers in one folder, most likely those w/o have the same 
license as those with. “aehem” ;)<br><br>There are lots of questions on license interpretation. This includes questions 
from people wanting to use Mozilla licensed software that wasn't even developed within the Mozilla foundation. Also 
there are lots of people who do not understand the concept of “free does not mean non-commercial use 
only”.<br><br>Sometimes there a license archeology task where people ask “hey, is that old code yours and is it under 
the Mozilla license?”<br><br>Another interesting case was a big, completely unknown blue company asking whether the 
hunspell module, having changed licenses so often (from BSD forked to GPL, changed to LGPL, to CC-Attr, to the tri 
license of Mozilla, including changed GPL stuff with the author's permission) really can be distributed by Mozilla 
under the MPL. After lots of digging through commit logs and change logs they could indeed verify that the code is 
completely clean.<br><br>Then there was the case of Firefox OS which was a fast development effort, involving copying 
lots of stuff from all over the internet just to get things running. A custom license scanner written to verify all 
bits and pieces was finally implemented and used to give clearance on release. It found dozens of distinct versions of 
the Mozilla and BSD licenses (mainly due to the fact that people are invited to add their own name to it when 
releaseing code). As a result there now is a discussion on OSI to discourage that behaviour to keep the number of 
individual license files to ship with the software down to a minimal number.<br><br>The speaker's general 
recommendation on releasing small software projects under a non-copyleft license was to use the CC-0 license, for 
larger stuff his recommendation was to go for the ASL due to its patent grant clauses. Even at Mozilla quite a few 
projects have switched over to Apache.<br>There also were a few license puzzlers:<br><ul><br><li>OpenJDK asked for 
permission to use their root-store certificates. Unfortunately at the time of receiving them they had not been given 
any sort of contract under which they may use them. *ahem*<br><li>The case with search engine icons … really isn't … so 
much different.<br></ul><br><br>There also tend to be some questions on the Firefox/Mozilla trademarks ranging 
from<br><ul><br><li>“can I use your logo for purpose such'n'such”?<br><li>”Do you have 'best viewed in...' button”? - 
Nope, as we generally appreciate developers writing web sites that comply with web standards instead of optimizing for 
one single browser only.<br><li>They did run into the subscription on download scam trap and could stop those sites due 
to trademark infringement.<br><li>Most of this falls under fair use – especially cases like Pearson asking for 
permission (with a two-page mail + pdf letter) to link to the mozilla web site...<br></ul><br><br>In general when 
people ask for permission if they do not need to ask: Tell them so but give them permission anyway. This is in order to 
avoid an “always-ask-for-permission” culture, and really to keep the number of requests down to those that are really 
necessary. One thing that does need prior permission though is shipping Firefox with a bunch of plugins pre-installed 
as a complete package.<br><br>On Patents – Mozilla does not really have any and spends time (e.g. on OPUS) avoiding 
them. On a related note there sometimes even are IPO requests.
