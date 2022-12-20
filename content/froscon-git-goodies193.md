---
title: "FrOSCon - Git Goodies"
date: 2012-09-05T20:34:14+02:00
tags: [Hacking,git,FrOSCon,]
---

# FrOSCon - Git Goodies


In his talk on <a href="http://programm.froscon.de/2012/events/1000.html">Git Goodies</a> Sebastian Harl introduced not 
only some of the lesser known git tooling but also gave a brief introduction as to how git organises its database. 
Starting with an explanation of how patches essentially are treated as blobs identified by SHA1 hashes (thus avoiding 
duplication not only in the local database but allover the git universe), pointed to by trees that are in turn 
generated and extended by commits that are in turn referenced by branches (updates on new commits) and tags (don't 
update on new commits). With that concept in mind it suddenly becomes trivial to understand that HEAD simply is a 
reference to wherever you next commit is going to in your working directory. It also becomes natural to understand that 
HEAD pointing just to a commit-id but not to a branch is called a de-tached head.<br><br>Commits in git are tracked in 
three spaces: In the repository (this is where stuff goes after a commit), in the index (this is where stuff goes after 
an add or rm) and in the working directory. Reverting is symetric: git checkout takes stuff from the repository and 
puts it into the current working copy. reset --mixed/--hard only touches the index.<br><br>When starting to work more 
with git start reading the man and help pages. They contain lots of goodies that make daily work easier: There are 
options that allow for colored diffs, setting external merge tools (e.g. vimdiff), setting the push default (just 
current branch or all matching branches). There are options to define aliases for commands (diff here has a large 
variety of options that can be handy like coloring only different words instead of lines). There are options to set the 
git-dir (where .git lies) as well as the working directory which makes it easy to track your website in git but not 
have the git directory lie in your public_html folder.<br><br>There is a git archive to checkout your stuff as tar.gz. 
When browsing the git history tig can come in handy - it allows for browsing your repository with an ncurses interface, 
show logs, diffs and the tree of all commits. You can ask it to only show logs that match a certain pattern. 
<br><br>Make sure to also look at the documentation of ref-parse that explains how to reference commits in an even more 
flexible manner (e.g. master@{yesterday}). Also checkout the git reflog to take a look at the version history of your 
versioning. Really handy if you ever mess up your repository and need to get back to a sane state. Also a good way to 
recover detached commits. Take a look at git-bisect to learn more on how to binary-search for commits that broke your 
build. Use a fine granular way to add changes to your repository with git  add -p - do not forget to take a look at git 
stash as well as cherry-pick.<br><br>
