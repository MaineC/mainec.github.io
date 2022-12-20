---
title: "Scientific debugging"
date: 2010-10-28T20:09:28+02:00
tags: [Science,Hacking,scientific method,debugging,]
---

# Scientific debugging


Quite some years ago I ready <a href="http://www.whyprogramsfail.com/">Why programs fail - a systematic guide to 
debugging</a> - a book written on the art of debugging programs written by Andreas Zeller (Prof. at University 
Saarbr&uuml;cken, researcher working on Mining Software Archives, Automated Debugging, Mutation Testing and Mining 
Models and one of the authors of famous <a href="http://www.gnu.org/software/ddd/">Data Display 
Debugger</a>).<br><br>One aspect that I found particularly intriguing about the book was up to then known to me only 
from the book <a href="http://en.wikipedia.org/wiki/Zen_and_the_Art_of_Motorcycle_Maintenance">Zen and the Art of 
Motorcycle Maintenance</a>: Scientific debugging as a way to find bugs in a piece of software in a structured way with 
methods usually known from the <a href="http://en.wikipedia.org/wiki/Scientific_method">scientific 
method</a>.<br><br>When working together with software developers one theme that often occured to me as very strange is 
other developers - especially Junior level developers' - ways of debugging programs: When faced with a problem they 
would usually come up with some hypothesis as to what the problem could be. Without verifying the correctness of that 
hypothesis they would jump directly to implementing a fix for the perceived problem. Not too seldom this led to either 
half baked solutions somewhat similar to the <a href="http://thedailywtf.com/Articles/Tweaking-the-Code.aspx">Tweaking 
the Code</a> behaviour on "The daily WTF", or - even worse - to no solution at all after days of implementation time 
were gone.<br><br>For the rest of this posting I'll make a distinction between the terms<br><ul><br><li><b >defect</b> 
for a programming error that might cause unintended behaviour.<br><li><b>failure</b> for an observed mis-behaviour of a 
program. Failures are caused by specific defects.<br></ul><br><br>For all but trivial bugs (for your favourite changing 
and vague definition of "trivial") I try to apply a more structured approach to identifying causes for failures. 
<br><br><ol><br><li><i>Identify a failure.</i> Reproduce the failure locally whenever possible. To get most out of the 
process write some automated test that reproduces the failure.<br><li><i>Form a hypothesis.</i> Usually this is done 
sub-consciously by most developers. This time around we explicitly write down what we think what the underlying defect 
is.<br><li><i>Devise an experiment.</i> The goal here is to show experimentally that your hunch about the defect was 
correct. This may involve debug statements, more extensive logging, using your favourite debugger with a break point 
set exactly at the position where you think the defect lies. However the experiment could also involve using <a 
href="http://www.wireshark.org/">wireshark</a> or <a href="http://www.tcpdump.org/">tcpdump</a> if you are debugging 
even simple distributed systems. On the other hand for extremely trivial defects the experiment could just be to fix 
the defect and see the test run through successfully.<br><li><i>Observe results.</i><br><li><i>Reach a conclusion.</i> 
Interpret the result of your experiment. If they reject your hypothesis move on to your next potential cause for the 
failure. If they don't you can go on to either devise more experiments in support of your hypothesis if the last one 
didn't convince you (or your boss) or fix the defect just found. In any case you should tidy up any remains of your 
experiment before moving on in most cases.<br></ol><br><br>When taking a closer look at the steps involved it's 
actually pretty straight forward. This makes this method so easy to use while still being most effective. When combined 
with automated testing it even helps when squashing bugs in code that is not written by the person fixing it. One way 
to make the strategy even stronger is to support the process by manually writing down a protocol of the debugging 
session with pen and paper. Not only does this help avoid checking the same hypothesis over and over again. It's also a 
way to quickly note down all hypothesis': In the process of debugging the person doing the analysis might be faster 
thinking of new possible causes than he can actually check. Noting them down helps keeping one's mind free and open as 
well as remembering all possible options.
