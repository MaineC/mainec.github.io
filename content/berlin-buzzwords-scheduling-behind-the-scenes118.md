---
title: "Berlin Buzzwords scheduling - behind the scenes"
date: 2012-04-17T21:23:39+02:00
tags: Berlin Buzzwords,
---

# Berlin Buzzwords scheduling - behind the scenes


Since roughly a week the <a href="berlinbuzzwords.de/program/session-schedule">Berlin Buzzwords schedule</a> is 
available online. <a href="http://berlinbuzzwords.de/content/tickets">Ticket</a>s are still available at the regular 
rate - make sure to book your ticket now - you've got another three weeks to purchase tickets at the regular rate, last 
minute rate will up the prize by another 100 Euros starting May 20th.<br><br>I thought it might be interesting to share 
some background on how Berlin Buzzwords scheduling worked out this year. We changed it quite a bit - adding more people 
to the conference committee, upping the acceptance rate while at the same time reducing speaking time for quite a few 
talks. This is to share some background information on some of the reasons and provide some detail on how rating was 
done.<br><br>Let me first state some constraints: <br><ul><br><li>We are hosting the conference in a venue where we can 
have 3 tracks at most - there aren't any other large rooms. We don't want to do another round of well- or rather 
not-so-well-informed random guessing of which talks will be un-popular stashing them in the small room. Switching 
schedule during the conference itself really isn't particularly professional nor is it very simple to do when you have 
to move about 200 people around to have them go to a different room than what the printed schedule says.<br><li>We are 
trying to keep the prize for the conference as low as possible to be able to attract the average developer who is not 
able to pay some 1.5k Euros to go to a conference. We are tech focused, no business involved - our attendees don't have 
big budgets for travelling to expensive conferences. With current attendee numbers for each day every attendee has to 
pay roughly 50% of the current regular ticket prize to make the budget work out. That means two things: a) We need all 
of you to pay for all days to make the budget work. b) If you would like to add another conference day because talks 
are so interesting, add another 50% of the current ticket prize and decide whether you'd be willing to pay that extra 
money. c) Increasing the number of tracks obviously means increasing the ticket prize which we would rather 
avoid.<br><li>Berlin Buzzwords was established as an event for professionals - quality of talks is high, attendees 
joining the conference know what they are talking about, we are happy to have students as well (did you notice there's 
a student ticket?) However that focus means that we are different from pure-open-source-community events. If you think 
there is too few coverage on scalability topics at existing community-only events please talk to them to increase that 
coverage or lead the effort of establishing such an event yourself - that isn't easy, but neither is it impossible. You 
could get started by hosting one of our meetups/workshops/hackathons - or alternatively run e.g. one of FOSDEM's 
DevRooms.<br><li>Buzzwords is organised by a team of several people. On the one hand there are volunteers (as in people 
not making a profit from the conference, working on it during working hours donated by their employer at best - Thank 
You Nokia**! Thank You Searchworkings!). They are familiar with what's going on in the search/store/scale space - you 
can find them on the program committee page. All administrative work is being done by newthinking communications - they 
have people very dedicated to what they are doing (there's even one girl who joined a Ruby-On-Rails getting started 
course last weekend to learn more on what Buzzwords people are working on*) - their main focus is that the whole 
conference runs as smoothly as possible.<br></ul><br><br><center><br><img 
src="http://berlinbuzzwords.de/sites/berlinbuzzwords.de/files/u36/BB12-Banner5_800x90med.jpg"/><br></center><br><br>Some
 of the assumptions above mean that we have to limit the number of talks we accept. Acceptance rate of last year was 
roughly 30%. Doing that again this year would have meant sending out decline mails to quite a few vital developers - 
many of them committers on the project they were talking about. That's not because the talks were bad or anything, it's 
just that there were way too many good talks. So we did an experiment this year: We upped that acceptance rate to 50% - 
but in turn had to reduce the length of many of the talks that were submitted as 40min versions. The result was that in 
order to fit more talks into the same space and time we had to shorten quite a few submissions. I did a bit of math 
this morning, of those reduced to 20min we would have had to reject 70% had we gone with a different schedule format 
w/o shortening submissions.<br><br>Talks selection was done according to a very simple algorithm: <br><br>Each talk was 
reviewed by at least three members of our program committee. Talk to reviewer assignment was done according to a pseudo 
random number generator - more precisely <a href="http://docs.python.org/library/random.html">this one</a>. Reviewers 
assigned scores ranging from 5 (want to have and am going to fight for it) to 1 (don't want to see and am going to 
fight against). After looking at the schedule constraints we decided to accept n talks in total, x of which would be 
40min, y of which would be 30 and z of which would be 20.<br><br>We sorted all talks by mean score and selected the top 
n for acceptance. Of those we took the first x/3 tagged as search, x/3 tagged as scale and x/3 from store to be 
accepted as 40 min talks. Same was done for the 30 and for the 20min slots. A mixture sort, grep, awk, head, and cut 
was quite helpful here and gave us n - 2 talks accepted. In our list of scores the following 5 talks had equal score, 
so we chose 2 of those at (pseudo-) random. Finally acceptance notification were sent out (Thanks to the Python mail 
support - that made things easier!). We asked speakers to confirm that they would still be available. Most got back 
right away, about 12 needed another nag mail or sms a week later to actually confirm.<br><br><center><br><img 
src="http://desmond.yfrog.com/Himg740/scaled.php?tn=0&server=740&filename=8m6oz.jpg&xsize=640&ysize=640"/><br></center><
br>Scheduling itself was done in a purely analog way: Take a pen, write all n talks on little pieces of paper, add 
information on track and length. After that those pieces of paper were arranged into the pre-defined schedule grid on a 
kitchen table: Re-arranging paper is just so much faster than anything you can do digitally - if only it wasn't for the 
creation of post-it notes beforehand ;)<br><br>Finally the schedule went out earlier this week - together with an 
appropriate press release, tweet etc. Again Buzzwords is a two day only conference. Most likely we won't grow the main 
conference beyond that any time soon. However in effect you yourself can extend that conference to any length you want. 
We have asked local companies to provide us with meeting space for at least 20 people each for free. We have several 
community members organise workshops, meetups, hackathons, code-retreats and barcamps in these areas already. If you 
think your topic is not covered well enough at the main conference, you'd like to learn more on a particular topic - 
please talk to us on how to organise one of those meetups yourself. You don't need to talk there if you don't want to - 
all you need to do is get an interesting schedule together that draws people to your meetup. Also if you think your 
talk should have been accepted - talk to us to get a meetup going on your topic and related themes to get them 
covered.<br><br>The main goal of Berlin Buzzwords is to involve you. We are very open to any ideas on how to 
collaborate or grow the conference. We do have several partner events throughout Europe this year. We offer companies 
the option to co-located and co-promote their trainings after Buzzwords. We offer community members the option to 
co-locate and co-promote their meetup with the conference. However we do need your time and dedication to make this 
work. Or to use a phrase that is well-known at least in the Apache world: Patches welcome!<br><br>* Her conclusion: 
Even w/o prior coding knowledge the course was easy enough to follow and at least made clear to her the difference 
between frontend and backend work. Observation: Buzzwords is very clearly backend. :)<br><br>** In particular Hannes 
Kruppa and the whole search recommendations team! 
