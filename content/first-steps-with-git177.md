---
title: "First steps with git"
date: 2010-10-30T19:47:00+02:00
tags: [svn,Hacking,git,version control,Note to Self,]
---

# First steps with git


A few weeks ago I started to use <a href="http://git-scm.com/">git</a> not only for tracking changes in my own private 
repository but also for Mahout development and for reviewing patches. My setup probably is a bit unusual, so I thought, 
I'd first describe that before diving deeper into the specifc steps.<br><br><b>Workflow to implement</b><br><br>With my 
development I wanted to follow Mahout trunk very closely, integrating and merging any changes as soon as I continue to 
work on the code. I wanted to be able to work with two different machines on the client side that are located at two 
distinct physical locations. I was fine with publishing any changes or intermediate progress online.<br><br><b>The 
tools used</b><br><br>I setup a clone of the official Mahout git repository on github as a place the check changes into 
and as a place to publish my own changes.<br><br>On each machine used, I cloned this github repository. After that I 
added the official Mahout git repository as upstream repository to be able to fetch and merge in any upstream 
changes.<br><br><b>Command set</b><br><br>After cloning the official Mahout repository into my own github account, the 
following set of commands was used on a single client machine to clone and setup the repository. See also the <a 
href="http://help.github.com/forking/">Github help on forking</a> git repositories.<br><code><br>#clone the github 
repository<br>git clone git@github.com:MaineC/mahout.git<br><br>#add upstream to the local clone<br>git remote add 
upstream git://git.apache.org/mahout.git<br></code><br><br>One additional piece of configuration that helped make life 
easier was to setup a list of files and file patterns <a 
href="https://git.wiki.kernel.org/index.php/GitFaq#How_do_I_tell_git_to_ignore_files.3F">to be ignored by 
git</a>.<br><br>Each distinct changeset (be it code review, code style changes or steps towards own changes) would then 
be done in their own branches locally. To share them with other developers as well as make them accessible to my second 
machine I would use the following commands on the machine used for initial development:<br><code><br>#create the 
branch<br>git branch MAHOUT-666<br><br>#publish the branch on github<br>git push origin MAHOUT-666<br></code><br><br>To 
get all changes both from my first machine and from upstream into the second machine all that was needed 
was:<br><code><br>#select correct local branch<br>git checkout trunk<br><br>#get and merge changes from upstream<br>git 
fetch upstream<br>git merge upstream/trunk<br><br>#get changes from github<br>git fetch origin<br>git merge 
origin/trunk<br><br>#get branch from above<br>git checkout -b MAHOUT-666 origin/MAHOUT-666<br></code><br><br>Of course 
pushing changes into an Apache repository is not possible. So I would still end up creating a patch, submit that to 
JIRA for review and in the end apply and commit that via svn. As soon as these changes finally made it into the 
official trunk all branches created earlier were rendered obsolete.<br><br>What still makes me stick with git 
especially for reviewing patches and working on multiple changesets is it's capability to quickly and completely 
locally create branches. This feature totally changed my so-far established workflow for keeping changesets 
separate:<br><br>With svn I would create a separate checkout of the original repository from a remote server, make my 
changes or even just apply a patch for review. To speed things up or be able to work offline I would keep one svn 
checkout clean, copy that to a different location and only there apply the patch.<br><br>In combination with using an 
IDE this workflow would result in me having to re-import each different checkout as a separate project. Even though 
both Idea and Eclipse are reasonably fast with importing and setting up projects it would still cost some 
time.<br><br>With git all I do is one clone. After that I can locally create branches w/o contacting the server again. 
I usually keep trunk clean from any local changes - patches are applied to separate branches for review. Same happens 
to any code modifications. That way all work can happen when disconnected from the version control server.<br><br>When 
combined with IntelliJ Idea fun becomes even greater: The IDE regularly scans the filesystem for updated files. So 
after each git checkout I'll find the IDE automatically adjust to the changed source code - that way avoiding project 
re-creation. Same is of course possible with Eclipse - it just involves one additional click on the Refresh 
button.<br><br>For me git helped speed up my work processes and supported use cases that otherwise would have involved 
sending patches to and fro between separate mailboxes. That way work with patches and changeset seemed way more natural 
and better supported by the version control system itself. In addition it of course is a great relief to be able to 
checkin, diff, log, checkout etc. even when disconnected from the network - which for me still is one of the biggest 
advantages of any distributed version control system. <br><br><strong>Update</strong><br>Lance Norskog recently pointed 
out one more step that is helpful:<br><blockquote>You didn't mention how to purge your project branch out of the github 
fork. From http://help.github.com/remotes/: Deleting a remote branch or tag<br><br>This command is a bit arcane at 
first glance… git push REMOTENAME :BRANCHNAME. If you look at the advanced push syntax above it should make a bit more 
sense. You are literally telling git “push nothing into BRANCHNAME on REMOTENAME”. And, you also have to delete the 
branch locally also.<br></blockquote>
