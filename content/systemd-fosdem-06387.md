---
title: "Systemd - FOSDEM 06"
date: 2013-02-18T20:45:29+01:00
tags: systemd,Fosdem,Event,
---

# Systemd - FOSDEM 06


As sort of a “go out of your comfort zone and discover new stuff” exercise I went to the systemd – two years later talk 
next. It's just plain amazing to see a machine boot in roughly one second (that is not counting the 7s that the BIOS 
needs for initialization). The whole project started as a init-only project but has since grown to a much larger 
purpose: An init platform ranging from mobile, embedded, desktop devices to servers many features were just over-due 
across the board.<br><br>Essentially the event-based system brings together what was split and duplicated before in 
things like console-kit, sysVinit, initscripts, inetd, pm-utils, acpid, syslog, watchdog services, cgrulesd, cron and 
atd. It brings support for event based container spawning, suspending and shutdown which brings whole new opportunities 
for optimisations. In addition for the first time in the history of Linux there is the possibility of grouped resource 
management: Instead of having nice levels bound to processes you now can group services to cgroups and give them 
guaranteed resources (which makes resource management of e.g multiple Apache processes plus some MySQL instances all 
running on the same machine so much easier).<br><br>(Post kindly proof-read and corrected by <a 
href=”http://www.thilo-fromm.de”>Thilo Fromm</a>)
