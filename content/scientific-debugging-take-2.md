---
title: "Scientific debugging - take 2"
date: 2014-01-28T20:13:57+01:00
tags: []
---

# Scientific debugging - take 2


Back in - OMG was that really back in 2010? - 2010 I wrote a post on <a
href="http://blog.isabel-drost.de/posts/scientific-debugging337.html">scientific
debugging</a>. Today I was reminded of this post as I actually had the pleasure
of watching this principle carried out - except this was for a medical "bug"
instead of one in a piece of software.
<br><br>
To quote the book <a
href="http://my.safaribooksonline.com/book/software-engineering-and-development/software-testing/9781558608665/6-scienti
fic-debugging/63_applying_the_scientific_met">Why
programs fail</a> the method of scientific debugging consists of 5 easy to
follow steps:

<blockquote>
<ol>
<li>Observe a failure (i.e., as described in the problem description).
<li>Invent a hypothesis as to the failure cause that is consistent with the observations.
<li>Use the hypothesis to make predictions.
<li>Test the hypothesis by experiments and further observations:
<ul>
<li>If the experiment satisfies the predictions, refine the hypothesis.
<li>If the experiment does not satisfy the predictions, create alternate hypothesis.
</ul>
<li>Repeat steps 3 and 4 until the hypothesis can no longer be refined.
</ol>
</blockquote>

In the past I've often seen developers jump immediately from a problem
description in a user reported bug to implementing what looks like the obvious
solution only to find out later that the actual problem underlying the problem
description was something completely different.
<br><br>
I know that making sure one has found the true problem can take time. However
today I was reminded a) just how long that time can be and b) just how important
each step in that search can be:
<br><br>
So to start with the problem description (step 1 above): "On Saturday evening on my way into
the bath tub some pretty bad pain hit me and forced me to lie down flat on the
floor. After a few minutes the pain was gone, what remained until today's
Tuesday is a pain in my back that gets worse when I walk or lie down on my left
side. As a side-note: I'm expecting a baby - not sure if that has anything to do
with the above."*
<br><br>
husband urged me to get to our general practitioner. So off I went - told him
the story above. He couldn't do a whole lot for me but to him it seemed like the
typical sciatic pain syndrome (step 2 above) - so off he sent me to the
orthopaedic (he needed an expert's opinion to check his hypothesis apparently).
<br><br>
I called the one doctor I was recommended, was told to go there immediately,
went there. Some 15 minutes later I told the doctor the story above (step 1). She
followed the hypothesis - except for one tiny little problem: Given the location of
the pain and my condition she knew of at least one more hypothesis that would also fit
the observation (step 2). She made a manual check (step 3). Her observation was
still consistent with the hypothesis (step 4). Now in order to reject said
hypothesis she would have needed to do one more check - except she couldn't do
that one herself. So she sent me off to my gynecologist to get an expert's
opinion (and gave me an appointment for late this week/early next week in case really
only the original hypothesis is valid).
<br><br>
Off I went, called the third doctor. I told her the whole story (step 1), she
continued where the other doctor had left off and made the missing check (step
3) - and rejected the alternative hypotheses right away (step 4). 
<br><br>
So off she
went to step 5: Sometimes labour pains start in the back (step 2) - so she put
me on a CTG (step 3) - after several minutes that hypothesis was rejected as
well (step 4). So off she went to step 5: 
<br><br>
The last
non-trivial hypothesis would have been that something's wrong with kidneys
(step 2). So she checked with her medical ultrasonics (step 3) - she wasn't 100%
sure though it seemed to look ok so she send me off to one last expert for a second opinion. 
<br><br>
So on my
way home I got to tell the story above the fourth time (step 1). Again she
continued with where the other doctor had left off - namely step 3: One more medical
ultrasonic and a blood test later the last non trivial hypothesis was finally
rejected altogether (step 4) So what was left was the initial
hunch of there being some blockade in my back. Finally we can step from
observing to acting, namely keeping warm (hot water bottle),
relaxing and to keep moving regularly.
<br><br>
As annoying as the day for the system to be debugged was there's at least two
valuable lessons learnt in it:
<br><br>
Being absolutely certain about a certain problem cause can be expensive (in this
case in particular time consuming for me, rest is something the doctors involved
have to discuss with my public health insurance). However jumping directly from
problem description to bugfix can turn out to be much more expensive if said
bugfix takes a long time to implement (and show effects) but is treating the wrong problem.
<br><br>
Proving one hypothesis right sometimes involves ruling out options that are
easy to check but have bad consequences if left untreated. Translated back -
before jumping from problem description to bugfix it may make sense to stop for
a second and think whether the particular problem you see might actually be
caused by a bug far worse than what you anticipated.
<br><br>
Now off to search for my <a
href="http://www.warmies.de/warmestofftiere/klassiker/elefant.html">warm little
elephant</a>.

<br><br>

<br><br>
<small>* Yeah, that's why I didn't make it to the Berlin Open Source meetup on
Sunday that I organised - at least my husband had fun together with <a
href="http://0pointer.de/lennart/">Lennart</a> and others trying to explain to the <a
href="http://blixtra.org/blog/">non German speaker</a> what on earth is the
English translation for the term <a
href="http://en.wikipedia.org/wiki/Low_back_pain">Hexenschu&szlig;</a>.
</small>
