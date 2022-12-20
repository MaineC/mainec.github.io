---
title: "Building online communities - from the 0MQ trenches"
date: 2013-11-13T21:38:58+01:00
tags: Uncategorized,
---

# Building online communities - from the 0MQ trenches


After seeing several talks on how open source communitites are organised at FOSDEM, on how to <a 
href="http://chemnitzer.linux-tage.de/2010/vortraege/detail.html?idx=472">license open source software 
strategically</a> at Chemnitzer Linuxtage and on how to <a href="http://vimeo.com/43759727">nurture open source 
communities</a> at Berlin Buzzwords over the past couple of years during the past year or so I've come to read quite a 
few articles and books on the art of building online communities. It all started with the now famous video on <a 
href="http://www.youtube.com/embed/Q52kFL8zVoM">poisonous people</a> of a talk given by Brian Fitzpatrick and Ben 
Collins-Sussman. Starting from there I went on to read their book <a 
href="http://shop.oreilly.com/product/0636920018025.do">"Team Geek"</a> - a great read not only if you are working in 
the open source space but also if you have to deal with tech geeks and managers on a daily basis as part of your 
job.<br><br>I continued the journey with reading <a href="http://producingoss.com/en/producingoss.html">"Producing Open 
Source Software"</a> - a book commonly recommended to read for those trying to understand how to run open source 
projects. Even though I started Apache Mahout back in 2008, first got in touch with the nutch/Lucene community in 2004 
and wrote my first mails to realtime Linux mailing lists to ask for help for some university assignment as far back as 
I guess 2001 the book still contained many ideas that were new and valuable to me. Most important of all it presented 
most of the important aspects of running an open source project in a very concise nicely presented format.<br><br>After 
going to a talk on engineering a <a href="http://programm.froscon.org/2013/events/1296.html">collaborative culture in 
the midst of flame wars</a> (including a side note on how to even turn trolls into valuable community members that help 
new comers substantially) given by Kristian Koehntopp earlier at Froscon this year I started reading a book that he 
recommended: <a href="http://mitpress.mit.edu/books/building-successful-online-communities">Building Successful online 
communities</a> by MIT press.<br><br>Many of these texts come from people that either have an Apache background one way 
or another - or are of more general nature. Yesterday I was happy to take the <a 
href="http://zguide.zeromq.org/page:all">ZeroMQ guide</a> (also available on <a 
href="http://shop.oreilly.com/product/0636920026136.do">dead trees</a>) and as <a 
href="https://github.com/imatix/zguide">github project</a> you can contribute to) that <a 
href="http://en.wikipedia.org/wiki/Pieter_Hintjens">Pieter Hintjens</a> had kindly given to my husband earlier this 
year during FOSDEM and find a whole chapter on how he manages ZeroMQ.<br><br>The text is unique in that iMatix got into 
a very influential position in the project very early on. However based on decades of open source experience Pieter 
managed to avoid many of the mistakes beginners make from the very outset. Also having built several online communities 
before (ranging from open source projects to the NGO FFII) he deliberately designed the ZeroMQ development in a<br>way 
that would encourage a healthy community.<br><br>There are several essential aspects that I find interesting: 
<br><br>The ZeroMQ development model is explicitly codified - they call this <a 
href="http://rfc.zeromq.org/spec:16">C4</a>: After the painful experience of discussing what seemed obvious but 
unspoken rules before codification the development team came up with a protocol for developing ZeroMQ - the protocol 
definition formulation being based on the rules IETF RFC are written. Many rules at Apache are not written down - 
especially when explaining how the Apache Way works to new projects in the incubator this becomes obvious again and 
again. Granted - apart from a handful of core values - Apache projects are essentially free to define their own way of 
working.  However even within one project your mileage may very depending on who you ask how things are done. This 
makes it hard for newcomers to understand what's going on - but also can become an issue when problems arise.<br><br>A 
concept that I find interesting about the way ZeroMQ works is the separation between maintainers and contributors: 
Maintainers are people who pull code into mainline - contributors are those doing the actual coding. Essentially this 
means that in order to get a patch in it needs at least two people to look at it. This isn't too much different from a 
review-than-commit policy - just enforced and written down as good practice. It helps avoid panic errors of people 
committing code in a hurry. But it also makes sure that those writing code actually get the positive feedback they 
deserve - which in turn might help<br>avoiding fast contributor burn out.<br><br>Also this kind of split in roles makes 
sure that there are no people with special privileges - just because someone has commit access to the main repository 
doesn't mean he can take any shortcuts process wise: They still have to come up with a decent problem description, file 
a ticket, create a patch, submit the patch through a pull request and have it reviewed like anyone else. I found it 
interesting that though ZeroMQ is backed and initiated by iMatix Pieter considers it to be very important to keep a 
balance in power and delegate to non-iMatix contributors both, coding and design decisions.<br><br>With iMatix being a 
small company the stance on making ZeroMQ an LGPL license project is a very clear decision. It's the only way to ensure 
that downstream users cannot just take the project, make modifications to it, re-package and ship it to users without 
the accompanying source code under the same license. In turn this tends to make it much more likely that even capable 
users tend to contribute to upstream. Of course taking the idea itself and turning it into some proprietary project 
would still be very possible. However the one thing that sets ZeroMQ apart from other efforts is not the source code or 
the architecture alone - it's the way the community works and blossoms.<br><br>One part where this choice of license is 
particularly handy is the deliberate decision to not go through any copyright assignment process. Instead each patch 
gets licensed to the project under the regular LGPL terms. This means that even should iMatix one day be sold or change 
their minds re-licensing the whole project is utterly hard. The impact on the community is clear: It makes sure that 
contributors' patches remain their own - including all merit and praise that comes with it. This approach prevents 
re-licensing but encourages a sense of shared ownership. Essentially this model of copyright handling is not unlike the 
way the Linux kernel works.<br><br>The last point that I found important is the way the project itself is structured: 
Instead of having everyone work on one single project ZeroMQ makes it easy to write extensions to the core library. 
There is a whole guide on how to write language bindings. Those writing these bindings aren't regulated at all - they 
are hosted in their own repositories with their own governance if they want - in the end it's up to the user to decide 
which ones are good and which ones will never become popular. In turn this lead to many people contributing indirectly 
to the value of ZeroMQ in significant ways. This is not unlike other projects: Apache HTTPd provides APIs to write 
modules against. ElasticSearch provides a clean REST API that encourages people speaking other languages to develop 
plugins that will translate the REST API into whatever their preferred language is. Open/Libre Office deliberately 
encourages writing extensions and plugins - even providing hosting facilities where users can search and download 
extensions from third parties.<br><br>I leave it as an exercise to the reader to check out the whole book. Even in the 
community chapter there are several other interesting concepts as well: The experience ZeroMQ went through with 
actively encouraging even developers with commit access to the main repository to work with forks instead of feature 
branches for experimental development, the trouble they went through with making backwards in-compatible changes to 
user facing APIs way too often, the exact definition of the C4 development process.<br><br>Overall a really interesting 
perspective on open source development from the trenches with lots of experience to back the advise given. If you are 
interested in learning more on how open source projects work - and if you are using any you definitely should be, 
otherwise you are betting part of your business on something you do not understand which generally isn't the best idea 
of all.<br>
