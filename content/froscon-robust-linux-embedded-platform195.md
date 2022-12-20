---
title: "FrOSCon - Robust Linux embedded platform"
date: 2012-09-04T20:05:03+02:00
tags: open embedded,FrOSCon,Event,General,
---

# FrOSCon - Robust Linux embedded platform


The second talk I went to at FrOSCon was given by <a href="http://thilo-fromm.de">Thilo Fromm</a> on <a 
href="http://programm.froscon.de/2012/events/950.html">Building a robust embedded Linux platform</a>. For more 
information on the underlying project see also <a href="http://github.com/DFE/HidaV/wiki">projec HidaV on github</a>. 
Slides of the talk <a href="http://thilo-fromm.de/~t-lo/slides/linux_platform.pdf">Building a robust Linux embedded 
platform</a> are already online.<br><br>Inspired by a presentation on <a 
href="https://archive.fosdem.org/2012/schedule/event/safe_upgrade_of_embedded_systems.html">safe upgrade prodedures</a> 
in embedded devices by <a href="https://archive.fosdem.org/2012/schedule/speaker/arnaut_vandecappelle.html">Arnaut 
Vandecappelle</a> in the <a href="https://archive.fosdem.org/2012/schedule/track/embedded_devroom.html">Embedded Dev 
Room FOSDEM</a> earlier this year Thilo extended the scope of the presentation a bit to cover safe kernel upgrades as 
well as package updates in embedded systems.<br><br>The main goal of the design he presented was to allow for 
developing embedded systems that are robust - both in normal operation but also when upgrading to a new firmware 
version or a set of new packages - the design included support for upgrading and rolling back to a known working state 
in an atomic way. Having systems deployed somewhere in the wild to power a wind turbine, inside of busses and trains or 
even within satellites pretty much forbids relying on an admin to press the "reset button".<br><br><a 
href="http://xkcd.com/705/"><img src=" http://imgs.xkcd.com/comics/devotion_to_duty.png"></a><br><br><font 
size="small">Original image <a href="http://xkcd.com/705/">xkcd.com/705</a></font><br><br>The reason for putting that 
much energy into making these systems robust also lies in the ways they are deployed. Failure vectors include not only 
your usual software bugs, power failures or configuration incompatibilities. Transmission errors, storage corruption, 
temperature, humidity add their share to increase the probability of failure.<br><br>Achieving these goals by building 
a custom system isn't too trivial. Building a platform that is versatile enough to be used by others building embedded 
systems adds to the challenges: Suddenly having easy to use build and debug tools, support for software life-cycle 
management and extend-ability are no longer nice-to-have features.<br><br>Thilo presented two main points to address 
the requirements: The first is to avoid trying to cater every use case. Setting requirements for a platform in terms of 
performance, un-brickability (see also <a href="http://www.urbandictionary.com/define.php?term=brickable">urban 
dictionary, third entry as of this writing</a>). Even setting a requirement for dual boot support or to the internal 
storage technology used. As a result designing the platform can become a lot less painful.<br><br>The second step is to 
harden the platform itself. Here that means that upgrading the system (both firmware and packages) is atomic, can be 
rolled-back atomically and thus no longer carries the danger of taking the device down for longer than intended: A 
device that does no longer perform it's task in the embedded world usually is considered broken and shipped back to the 
producer. As a result upgrading may be necessary but should never render the device useless.<br><br>One way to deal 
with that is to store boot configurations in a round robin manner - for each configuration a "was booted" (set by the 
bootloader on boot) and a "is healthy" (set by the system after either a certain time of stability or after running 
self tests) flags are needed. This way at each boot it is clear what the last healthy configuration was.<br><br>To do 
the same with your favourite package management system is slightly more complicated: Imagine running something like 
apt-get upgrade with the option to switch back to the previous state in an atomic way if anything goes wrong. One 
option to deal with that presented is to work with transparant overlay filesystems that allow for having a read-only 
base layer - and a "transparent" r/w layer on top. If a file does not exist in the transparent layer, the filesystem 
will return the original r/o version. If it does exist it will return the version in the transparent overlay. In 
addition there's also an option to mark files as deleted in the overlay.<br><br>With that upgrading becomes as easy as 
installing the upgraded versions into some directory in your filesystem and mounting said directory as transparent 
overlay. With that roll-back as well as snapshots are easy to do.<br><br>The third ingredient to achieving a re-usable 
platform presented was to use <a href="http://www.openembedded.org/wiki/Main_Page">Open Embedded</a>. Including an easy 
to extend layer-based concept, support for often recent software versions, versioning and dependency modelling, some 
BSP layers officially supported by hardware manufacturers building a platform on top of Open Embedded is one option to 
make it easily re-useable by others.<br><br>If you want to know more on the concepts described join <a 
href="http://github.com/dfe/hidav">HiDaV platform project</a> - many of the concepts described are already - or soon to 
be - implemented. <br>
