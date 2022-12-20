---
title: "GeeCon - Randomized testing"
date: 2012-05-21T08:02:55+02:00
tags: Science,testing,Free Software,randomized,geecon,Hacking,
---

# GeeCon - Randomized testing


I arrived late during lunch time on Thursday for GeeCon – however just in time to listen to one of the most interesting 
talks when it comes to testing. Did you ever have the issue of writing code that runs well in your development 
environment but crashes as soon as it's rolled out at customers only to find out that their Locale setting was causing 
the issues? Ever had to deal with random test failure because against better advise your tests did depend on execution 
order that is almost guaranteed to be different on new JVM releases?<br><br>The Lucene community has encountered many 
similar issues. In effect they are faced with having to test a huge number of different configuration combinations in 
order to make sure that their software runs in all client setups. In recent months they developed an approach called 
randomised testing to tackle this problem: Essentially on each run “random tests” are run multiple times, each time 
with a slightly different configuration, input, in a different environment (e.g. Locale settings, time zones, JVMs, 
operating systems). Each of these configurations are pseudo random – however on test failure the framework will reveal 
the seed that was used to initialize that pseudo random number generator and thus allow you to reproduce the failure 
deterministically.<br><br>The idea itself is not new: published in a paper by Ntafos, used in fuzzers to identify 
security holes in applications this kind of technique is pretty well known. However applying it to write tests is a new 
idea used at Lucene.<br><br>The advantage is clear: With every new run of the test suite you gain confidence that your 
code is actually stable to any kind of user input. The downside of course is that you will discover all sorts of 
different issues and bugs not only in your code but also in the JVM itself. If your library is being used in all sorts 
of different setups fixing these issues upfront however is crucial to avoid users being surprised that it does not work 
well in their setup. Make sure to fix these failures quickly though – developers tend to ignore flickering tests over 
time. Adding randomness – and thereby essentially increasing the number of tests in your testsuite – will add the 
amount of effort to invest in fixing broken code.<br><br>Dawid Weiss gave a great overview of how random tests can be 
used to harden a code base. He introduced the testframework written at carrot search that isolated the random test 
features: It comes with a RandomizedRunner implementation that can be used to subsitute junit's own runner. It's 
capable of tracking test isolation by tracking spawned threads that might be leaking out of tests. In addition it 
provides utilities for instance for creating random strings, locals, numbers as well as annotations to denote how often 
a test should run and when it should run (always vs. nightly).<br><br>So when having tests with random input – how do 
you check for correctness? The most obvious thing to do is when being able to check the exact output. When testing a 
sorting method, not matter what the implementation and the input is – the output should always be sorted, which is easy 
enough to check. Also checking against simpler, but maybe in practice more expensive algorithms is an option.<br><br>A 
second approach is to do sanity checks: Math.abs() at least should always return positive integers. The third approach 
is to do no checking at all in some cases. Why would that help? You'd be surprised by how many failures and exceptions 
you get by actually using your API in unexpected ways or giving your program unexpected input. This kind of behaviour 
checking does not need any assertions.<br><br>Note: Really loved the APad/ iMiga that Dawid used to give his talk! Been 
such a long time since I last played with my own Amiga...<br>
