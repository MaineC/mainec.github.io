---
title: "JAX: Java performance myths"
date: 2013-05-22T20:37:07+02:00
tags: [performance,myth,Java,Event,JAX,]
---

# JAX: Java performance myths


This talk was one of the famous talks on Java performance myths by Arno Haase.<br>His main point - supported with 
dozens of illustrative examples was for<br>software developers to stop trusting in word of mouth, cargo cult like 
myths<br>that are abundant among engineers. Again the goal should be to write readable<br>code above all - for one the 
Java compiler and JIT are great at optimising. In<br>addition many of the myths being spread in the Java community that 
are claimed<br>to lead to better performance are simply not true.<br><br><P><br>It was interesting to learn how many 
different aspects of both software and<br>hardware contribute to code performance. Micro benchmarks are 
considered<br>dangerous for a reason - creating a well controlled environment that matches<br>what the code will 
encounter in production is influenced by things like just in<br>time compilation, cpu throttling, 
etc.<br><br><P><br>Some myths that Arno proved wrong include final making code faster (in case of<br>method parameters 
it doesn't make a difference up to bytecode being identical<br>with and without), inheritance being always expensive 
(even with an abstract<br>class between the interface and the implementation Java 6 and 7 can still<br>inline the 
method in question). Another one was on often wrongly scoped Java<br>vs. C comparisons. One myth resolved around the 
creation of temporary objects -<br>since Java 6 and 7 in simple cases even these can be optimised 
away.<br><br><P><br>When it comes to (un-)boxing and reflection there is a performance penalty. For<br>the latter 
mostly for method lookup, not so much for calling the method. What we<br>are talking about however are penalties in the 
range of about 1000 compute<br>cycles. Compared to doing any remote calls this is still dwarfed. Reflection 
on<br>fields is even cheaper.<br><br><P><br>One of the more wide spread myths resolved around string concatenation 
being<br>expensive - doing a ``A'' + ``B'' in code will be turned into ``AB'' in<br>bytecode. Even doing the same with 
a variable will be turned into the use of<br>StringBuilder ever since -XX:OptimizeStringConcat was turned on by 
default.<br><br><P><br>The main message here is to stop trusting your intuition when reasoning about a<br>system's 
performance and performance bottlenecks. Instead the goal should be to<br>go and measure what is really going on. Those 
are simple examples where your<br>average Java intuition goes wrong. Make sure to stay on top with what the 
JVM<br>turns your code into and how that is than executed on the hardware you have<br>rolled out if you really want to 
get the last bit of speed out of your<br>application.<br>
