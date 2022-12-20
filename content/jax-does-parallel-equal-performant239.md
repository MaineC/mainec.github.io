---
title: "JAX: Does parallel equal performant?"
date: 2013-05-21T20:34:40+02:00
tags: performance,Java,Event,JAX,
---

# JAX: Does parallel equal performant?


In general there is a tendency to set parallel implementations to being equal<br>to performant implementations. Except 
in the really naive case there is always<br>going to be some overhead due to scheduling work, managing memory sharing 
and<br>network communication overhead. Essentially that knowledge is reflected in<br>Amdahl's law (the amount of serial 
work limits the benefit from running parts<br>of your implementation in parallel, 
http://en.wikipedia.org/wiki/Amdahl's_law),<br>and Little's law (http://en.wikipedia.org/wiki/Little's_law) in case of 
queuing<br>problems.<br><br><P><br>When looking at current Java optimisations there is quite a bit going on 
to<br>support better parallelisation: Work is being done to provide for improving<br>lock contention situations, the GC 
adaptive sizing policy has been improved to<br>a usable state, there is added support for parallel arrays and 
lampbda's<br>splitable interface.<br><br><P><br>When it comes to better locking optimisations what is most notable is 
work<br>towards coarsening locks at compile and JIT time (essentially moving locks from<br>the inside of a loop to the 
outside); eliminating locks if objects are being<br>used in a local, non-threaded context anyway; and support for 
biased locking<br>(that is forcing locks only when a second thread is trying to access an<br>object). All three taken 
together can lead to performance improvements that<br>will almost render StringBuffer and StringBuilder to exhibit 
equal performance<br>in a single threaded context.<br><br><P><br>For pieces of code that suffer from false sharing (two 
variables used in<br>separate threads independently that end up in the same CPU cacheline and as a<br>result are both 
flushed on update) there is a new annotation: Adding the<br>"@contended" annotation can help the compiler for which 
pieces of code to add<br>cacheline padding (or re-arrange entirely) to avoid that false sharing from<br>happening. One 
other way to avoid false sharing seems to be to look for class<br>cohesion - coherent classes where methods and 
variables are closely related<br>tend to suffer less from false sharing. If you would like to view the 
resulting<br>layout use the "-XX:PrintFieldLayout" option.<br><br><P><br>Java 8 will bring a few more notable 
improvements including changes to the<br>adaptive sizing GC policy, the introduction of parallel arrays that allow 
for<br>parallel execution of predicates on array entries, changes to the concurrency<br>libraries, internalised 
iterators.<br><br><P><br>
