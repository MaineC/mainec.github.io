---
title: "FSFE booth at the Chemnitzer Linux Tage"
date: 2009-03-23T08:30:39+01:00
tags: Free Software,Event,FSFE,General,
---

# FSFE booth at the Chemnitzer Linux Tage


This year for the 11th time the "Linux Tage" were organized at the university of Chemnitz. Each year in March this 
means two days devoted to the topic of open and free software. It means an event that is very well organized by a 
pretty professional team of volunteers.<br><br>For the third time the FSFE had its booth at the event - this time run 
by Rainer Kersten, Uwe Zemisch and me. Recurring questions at the booth were<br><ul><br>  <li> "What the hack is FSFE 
and in which ways do you actually support free software?"<br>  <li> "I am already fellow, you keep telling me there are 
these great fellowship meetups. Do you know whether there is one near my town? How do these events start? How are they 
organized?"<br></ul><br><br>It was interesting to see that FSFE is one of the few organizations that try to fill the 
gap between those writing open source software and those actually making decisions that are relevant to the developers 
but know nothing of writing software whatsoever.<br><br>Besides running the booth there was some time left for a few 
talks. I decided to go to the OpenMP talk. The idea is to develop a highlevel API for marking code passages for 
parallel execution. It is not designed for parallel programming on clusters but on multi core machines. Somewhat 
related to the Java concurrency package but far more high level.<br><br>The second talk I went to was on personal data 
protection laws in Germany. One funny piece of information: Even the ministry of justice was sued sucessfully for 
storing to much information on the visitors of its webpage.<br><br>Last talk I went to was on Google Android. To me it 
looks like a nice mix of completly open source (like Open Moko) and completely closed source. If you need a phone you 
can use for making phone calls but still want to play with it and be root on the phone (399$ for the dev phone, sim 
unlocked, only available for registered developers, registration is 25,-$), Android G1 propably is the way to go. The 
phone is highly integrated with Google applications. The assumption when building it seems to have been, that people 
are online all the time with that phone.<br><br>For coding: Only a Java API is available, no C or C++. SDK is available 
for Lin/Mac/Win. The emulator does work, only thing it does not reflect is the real speed of the device itself. Each 
app gets its own VM, Dalvik supports process memory sharing that makes that less expensive. In case of memory shortage 
apps are killed in order of user impact (empty/precreated, background, service (mp3 player), visible apps, foreground 
apps). Idea is to kill those apps that are least visible to the user. The programmer needs to take care that apps 
constantly store state so restarting them gets them up in the same state they were in when killed.<br><br>More 
information online: http://www.htc.com; adoid.git.kernel.org;<br><br>All in all: Really nice weekend. Looking forwared 
to return next year.<br>
