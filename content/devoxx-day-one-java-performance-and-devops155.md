---
title: "Devoxx – Day one – Java, Performance and Devops  "
date: 2010-12-15T21:22:06+01:00
tags: [Java,devops,General,performance,optimisation,Devoxx,]
---

# Devoxx – Day one – Java, Performance and Devops  


In his keynote Mark Reinhold provided some information on the very interesting features to be included in the Java 7 
release. Generics will be easier to declare with the diamond operator. Nested try-finally constructs that are nowadays 
needed to safely close resources will no longer be necessary – their will be the option of implementing a Closeable 
interface supporting a method close() that get's called whenever objects of that class's type go out of scope. That way 
resources can be freed automatically. Though different in concept, it still reminds me a lot of the functionality 
typically provided by destructors in C++.<br><br>The support for lambda operators and direct method references that 
will greately help reducing clutter due to nested inner classes has been postponed for later Java releases. Though it 
took 4 years to come up with the Java 7 release new features are pretty much limited. However the current roadmap looks 
pretty much release date driven. The intention seems to be to get developers focussed on a limited set of reachable 
features to finally get the release out into the hands of users.<br><br>The speaker claimed Oracle to remain committed 
to Java development – first and foremost because of being a heavy Java user themselves. However also in order to 
generate revenue indirectly (through selling support and consulting for Java related products), directly (through Java 
support) and reducing internal development cost and Java friction.<br><br>Though Oracle had a JVM implementation of its 
own (jRocket) development of HotSpot will be continued – mostly due to a larger number developers being familiar with 
HotSpot. However monitoring and diagnosis tooling that was superior at jRocket is supposed to be ported to 
HotSpot.<br><br>In the core Java session I also went to the talk on Java performance analysis by Joshua Bloch. He a 
good job bringing the topic of performance analysis on complex systems to software developers. In ancient times it was 
quite easy to estimate a piece of code's static performance by static code analysis. Looking at the expression <code>if 
(condition && secondCondition)</code> it is still commonly considered to be faster to use “&&” over “&”. However 
looking at current CPU architectures that make heavy use of instruction pipelines it heavily depends on their branch 
prediction heuristics whether this statement is still true. Dirtying the pipeline by using && may well be more 
expensive than doing the extra evaluation. General message: The performance of your code in a real world system depends 
on the hardware it runs on, the operating system as well as the exact VM version used. Estimating performance based on 
static analysis only is no longer possible.<br><br>However even when doing benchmarks one might well reach false 
conclusions. It is common knowledge that running a benchmark on a VM is required to be run multiple times – VM warmup 
phases are well known to developers, so the common performance pattern for on specific function usually looks like 
that:<br><br>However even when repeating the test on the same machine multiple times, the values seen after warm-up may 
be skewed substantially. The only remedy to reaching false conclusions is to do several VM runs, average of the runs 
(and provide median etc. that are less susceptible to outliers) and provide error bars for each averaged run. When 
comparing two different implementations the only way to reliably tell which one is better than the other is to do 
statistical significance tests. Consider the diagram below. When leaving error bars out, the left implementation seems 
clearly better than the right. However when taking into account how widely skewed the performance numbers are and 
adding error bars to the entries, this is no longer the case: Both runs are no longer statistically significantly 
different. <br>
