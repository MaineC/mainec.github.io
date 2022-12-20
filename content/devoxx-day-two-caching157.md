---
title: "Devoxx – Day two – Caching "
date: 2010-12-07T21:22:10+01:00
tags: caching,Hacking,Java,Devoxx,
---

# Devoxx – Day two – Caching 


Day two started with a really good talk on caching architectures by Greg Luck. He first motivated why caching works: 
Even with SSIDs being available now there is still a huge performance gap between RAM access times and having to go to 
disk. The issue is even  worse in systems that are architected in a distributed way making frequent calls to remote 
systems. <br><br>When sizing systems for typical load, what is oftentimes forgotten is that there is no such thing as 
typical load: Usually the load distribution observed over one day for a service used mainly in one time zone has the 
shape of an elephant – most queries are issued during lunch time (head of the elephant) with another but smaller peak 
during the afternoon. This pattern repeats when looking at the weekly distribution, repeats again when looking at the 
yearly distribution. When looking at the peak time of the year, at the peak day, at the peak time your lead may be 
increased by several orders of magnitude compared to average load.<br><br>Although query volume may be high in most 
applications that reach out for caching, these queries usually exhibit a power law distribution. This means that there 
are just a few queries being issued very frequently, however many queries are pretty seldom. This pattern allows for 
high cache hit rates thus reducing load substantially even during very busy times.<br><br>The speaker went into some 
more detail concerning different architectures: Usually projects start with one cache located directly on the frontend 
server. When scaling horizontally and adding more and more frontends this leads to an ever increasing load on the 
database during one period of lifetime for one cached item. The first idea employed to remedy this setup is to link the 
different caches to each other increasing cache hit rates. Problem here are updates racing to the various caches when 
the same query is issued to the backend by more than one frontend. The usual next step is to go for a distributed 
remote cache such as memcache. Of course this has the draw-back of now having to do a network call for each cache 
access slowing down response times by several milliseconds. Another problem with distributed caching systems is a 
theorem well known to people building distributed NoSQL databases: CAP says that you can get only two of the three 
desired properties consistency, availability and partition-tolerance. Ehcache with a terracotta back end lets you 
configure where your priority lies.<br>
