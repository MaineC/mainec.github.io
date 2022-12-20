---
title: "Note to self: Clojure with Vim and Maven"
date: 2012-07-17T20:07:55+02:00
tags: [Hacking,clojure,Cascalog,Note to Self,vim,]
---

# Note to self: Clojure with Vim and Maven


Steps to get a somewhat working Clojure environment with vim:<br><br><ul><br><li>Install the current <a 
href="http://www.vim.org/scripts/script.php?script_id=2501">vimclojure</a> plugin.<br><li>Get and install a <a 
href="https://bitbucket.org/kotarak/vimclojure/">nailgun client</a>.<br><li>Add vimclojure to your <a 
href="https://bitbucket.org/kotarak/vimclojure/">clojure project pom.xml</a>.<br><li>Start the nailgun server from 
within your maven project with <code>mvn clojure:nailgun</code> with the <a 
href="https://github.com/talios/clojure-maven-plugin">maven clojure plugin</a>.<br><li>Finally start vim, open your 
favourite clojure file - you can open a REPL with \sr, when in a function definition you can evaluate that with \et - 
see also <a href="http://blog.darevay.com/2010/10/how-i-tamed-vimclojure/">tamining vim 
clojure</a><br></ul><br><br>Note: There is more convenient tooling for emacs (see also <a 
href="http://dev.clojure.org/display/doc/Getting+Started+with+Emacs">getting started with clojure and emacs</a>) - its 
just that my fingers are more used to interacting with vim...<br><br>2nd note: This post is not an introduction or walk 
through on how to get Clojure setup in vim - it's not even particularly complete. This is intentional - if you want to 
start tinkering with Clojure: Use Emacs!  This is just my way to re-discover through Google what I did the other day 
but forgot in the mean time.
