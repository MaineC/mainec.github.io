---
title: "Keeping changesets small"
date: 2009-06-21T20:48:19+02:00
tags: [svn,Hacking,]
---

# Keeping changesets small


One trick of successful and efficient software development is tracking changes in the sources in source code management 
systems, be it centralized systems like svn or perforce or decentralized systems like git or mercurial. I started 
working with svn while working on my Diploma thesis project in 2003, continued to use this systems while researcher at 
HU Berlin. Today I am using svn at work as well as for Apache projects and have come to like git for personal 
sandboxes.<br><br>One thing that bothered me for the last few months was the question of how to keep changesets 
reasonably small to be easy to code-review but also complete in that they contain enough to implement at least part of 
a feature fully.<br><br>So what makes a clean changeset for me: It contains at least one unit test to show that the 
implementation works. It contains all sourcecode needed to make that test work and not break anything else in the 
source tree. It might contain every change needed to implement one specific feature. The second sort of changeset that 
comes to my mind might be rather large and contains all changes that are part of refactoring the existing 
code.<br><br>There are a few bad practices that in my experience lead to large unwieldy changesets:<br><ul><br><li> 
Making two or more changes in one checkout. Usually this happens whenever you checkout your code, start working on a 
cool new feature but get distracted by some other incoming feature request, by some bugfix or by mixing your changes 
with a patch from another developer you are about to review. Mixing changes makes it extremely difficult to keep track 
of which change belongs to which task. Usually the result is not checking in some of your changes and breaking the 
build.<br><li> Refactoring while working on a feature. Imagine the following situation: You are happily working along 
implementing your new feature. But suddenly you realize that some of your code should be refactored to better match 
your needs. And whoops: Suddenly it is no longer clear whether changes were simply made due to the refactoring steps 
(that might even be automated) or due to your new feature. I tend to at least try to do refactorings either before my 
changes, in a new checkout or after I finished changing the code (if that is feasable).<br><li> The definition of 
feature is too large. I tend to get large changesets whenever I try to do too much in one go. That is, the "feature" 
that I am trying to implement simply is too large. Usually it is possible to break the task up into a set of smaller 
tasks that are easier to manage.<br></ul><br><br>If using git, there is a nice option to avoid to re-checkout a 
project: You can simply "stash" away changes up to the current point in time, do all that is needed for what distracted 
you, check that in and re-apply the changes for your previous task.<br><br>This list will be updated as I learn about 
(that is "make") more mistakes that can be cleanly classified into new categories.
