---
title: "Clojure in Berlin"
date: 2012-02-02T00:01:53+01:00
tags: clojure,overtone,General,
---

# Clojure in Berlin


Though I had the chance to tinker with some Clojure code only briefly it's programming model and the resulting compact 
programs do fascinate me. As the resulting code runs on a JVM and does integrate well with existing Java libraries 
migration is comparably cheap and easy.<br><br>Today I finally managed to attend the local <a 
href="http://www.meetup.com/Clojure-Berlin/">Berlin Clojure meetup</a>, co-organised by Stefan Hübner and Fronx. Timing 
couldn't have been much better: In this evenings event Philip Potter from Thoughtworks introduced <a 
href="http://overtone.github.com/">Overtone</a> - a library for making music with Clojure.<br><br>After <a 
href="https://github.com/overtone/overtone/wiki/Installing-overtone">installing and configuring</a> jack for sound 
output, supercollider, and overtone outputting your first tone is as simple as registering the overtone library and 
typing<br><code><br>(definst foo [] (saw 220))<br>(foo)<br></code><br>To stop it type (stop).<br><br>Other types of 
waves of course are supported as well, so is playing different waves simultaneously and modifying them at runtime. Also 
expressing sounds as notes (c, d, e, f, g) that may have a certain length is possible of course – which makes it so 
much easier to design music than having to thing in frequencies.<br><br>A sample of what can easily be done with 
Overtone:<br><br><iframe width="100%" height="166" scrolling="no" frameborder="no" 
src="http://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F35276769&show_artwork=true"></iframe
><br><small>Original sound way better - this sample was taken with a mobile phone, compressed, re-coded and then put 
online. Checkout Overtone project for the real thing - and don't even try to listen to the sample with low-end laptop 
speakers ;)</small><br><br>Overall a well organised meetup (Thanks to Soundcloud for hosting it, to the organisers for 
putting it together and to the speaker for a really well done introduction to Overtone) and an interesting way to get 
started with Clojure with very fast (audio) feedback.
