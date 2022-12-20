---
title: "Second steps with git"
date: 2012-04-22T20:34:46+02:00
tags: [Hacking,git,Note to Self,]
---

# Second steps with git


Leaving this here in case I'll search for it later again - and I'm pretty sure I will.<br><br>The following is a 
simplification of the <a href="http://blog.isabel-drost.de/index.php/archives/243/first-steps-with-git">git workflow 
detailed earlier</a> - in particular the first two steps and a little background.<br><br><ul><br><li>When dealing with 
remotes the <a href="http://gitref.org/remotes/">git remote documentation</a> is very useful.<br><li>When sharing your 
changes with others the <a href="http://schacon.github.com/git/user-manual.html#public-repositories">git tutorial on 
sharing changes</a> is very helpful.<br></ul><br><br>Instead of starting by cloning the upstream repository on github 
and than going from there as follows:<br><br><code><br>#clone the github repository<br>git clone 
git@github.com:MaineC/mahout.git<br><br>#add upstream to the local clone<br>git remote add upstream 
git://git.apache.org/mahout.git<br></code><br><br>you can also take a slightly different approach and start with an 
empty github repository to push your changes into instead:<br><br><code><br>#clone the upstream repository <br>git 
clone git://git.apache.org/mahout.git<br><br>#add upstream your personal - still empty - repo to the local clone<br>git 
remote add personal git@github.com:MaineC/mahout.git<br><br>#push your local modifications branch mods to your personal 
repo<br>git push personal mods<br></code><br><br>That should leave you with branch mods being visible in your personal 
repo now.<br><br>
