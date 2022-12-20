---
title: "Using Scrum for software development"
date: 2010-06-25T15:31:11+02:00
tags: [Scrum,]
---

# Using Scrum for software development


A few months ago I entered a new team of until then two software developers. Being so small and with a rather busy 
product owner, until then people had followed the rituals of Scrum only loosely. When starting to work on a new 
component the three of us decided to change a few thing several weeks ago:<br><br><ul><br><li>We would setup 
infrastructure to be somewhat similar to what we knew from Apache projects: All issues to be accomplished were to be 
tracked in our issue tracker. We would have a dev list that mirrors whatever goes to JIRA, a commit list to mirror 
whatever goes into svn and a user list.<br><li>We would try to follow Scrum rituals more closely: Dailies were 
re-introduced, we setup estimation meetings and got a cooking timer to stick with 60min per meeting, review and 
planning was supposed to be prepared and done with paper and pens on a whiteboard. After each planning we would have a 
planning II as well as a retrospective to improve our processes.<br></ul><br><br>After the first weeks of following 
these ideas we did notice several improvements that are going to be described in upcoming blog posts.<br><br>Lets start 
with the first (trivial) change we made: Introducing a commit mailing list. With developers sitting all together in one 
room, communicating openly and regularly this may seem like a huge overkill. However there are a few changes that 
brought to how we develop:<br><br>People would suddenly start to think about what goes into svn: Being very obviously 
publicly readable, commit messages became much more readable, explaining what's going on. Changes would be checked-in 
only if they belong to one logical change set. In return others would review what was checked in sort of automatically 
- spotting problems or questionable code and configuration very early. Changes that got done were made transparent to 
other team members very easily.<br><br>Of course the information is available anyway. However to be honest - I never 
really closely check each change set that got committed after issuing an svn up. Getting the stuff pushed to my inbox 
hugely improved the situation while still keeping a faster development cycle than when working with a 
review-before-commit model. This is especially important for cases where only smaller adjustments are being made. Where 
larger refactoring steps were necessary we would still get the code reviewed by our colleagues before checking it in.
