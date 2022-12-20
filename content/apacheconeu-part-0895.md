---
title: "ApacheConEU - part 08"
date: 2012-11-17T20:53:23+01:00
tags: [ApacheCon,Apache Con,community,CouchDB,apacheconeu,]
---

# ApacheConEU - part 08


Jan Lehnardt's talk covered the history of CouchDB - including lessons learnt along the way. The first issue he went 
into: Shipping 1.0 is hard! They spent a lot of effort and time in order to have a stable database that won't loose 
your data - only to have a poorly patch slip in for 1.0 that resulted in data loss. The fury of action happening 
afterwards was truely amazing - people working on rolling shifts all over the planet to not only fix the issue but also 
provide recovery tooling for those affected by the bug. The lessons learnt form that are as obvious as they are often 
neglected: Both test coverage as well as code review are crucial for any software project.<br><br>The second topic Jan 
went into was the disctraction and tension that comes from having a company built around your favourite open source 
project. When going down this road keep in mind that the whole VC setup usually is very time consuming - the world 
starts revolving around the need to either gather more VC funding or make up a successful business case to support your 
company. All of this results in less time spent coding, friction around the fact that the corporate interests may not 
always be what is best for your open source project. In CouchDB the result was the explosion of the project founder who 
eventually left the project. This hit CouchDB particularly badly as the project essentially was built around the idea 
of the one brilliant coder, relied on his information channels for marketing. The lesson learnt was that having 
communications centralised that way can easily turn against you - don't trust your benevolent dictator.<br><br>Usually 
it is quite ok for users to move on - in particular if the project does no longer fit their needs. However having 
multiple key people leave at the same time can be detrimental, in particular if they are the vocal ones. In terms of 
lessons learnt: Embrace the fact that people will fail your software. Use the resulting knowledge about your 
application boundaries - or fix what failed them.<br><br>In terms of general advise: The world moved on after any of 
these cases. What does help is to ship what users need instead of running after the next big hype. Also good ideas will 
stick - using json as format and js for query formulation did make it into many other applications with the former also 
making it into the next SQL standard to be released in 2015. The goal should be to build stuff that is easy (and fun) 
to use.<br><br>In the mean time CouchDB grew up. Not only does it have another release and a new web site. It has 
turned into a project that is no longer a thing pushed forward by a single person but that moves on its own. The secret 
behind that development is to acknowledge that having just few people in the leading position will burn them out - make 
sure to enable others and that your strong leaders to get to lead. Oh and as any Apache project also CouchDB is happy 
about any new contributor joining the project.<br><br>When it comes to communication the Apache incubation process made 
sure to burn the "everything happens on the mailing list" mantra into their mind. Still IRC was a valuable way of 
communication for non-decision stuff like user support and community building. IRC is fun - in particular when you can 
train irc bots based on earlier communication to automatically answer incoming user questions.<br><br>Another option 
CouchDB used to fix the community issues was to meet with people face-2-face - for three days in Boston, later in 
Dublin, later in Vienna. In addition they added a roadmap for the next 2 to 3 years including points 
like:<br><ul><br><li>faster releases - they switched to time based instead of feature based releases except for 
security patches<br><li>they are the first to use git@apache to make branching and merging easier<br><li>they are 
github lovers with pull requests ending up on their dev list<br><li>they enabled a Erlang beginners question list in 
order to be able to recruit new contributors in a world of lacking Erlang developers. A very specific result of that 
was that people are much more comfortable even asking simple question - and on a more practical note one question for 
the birds eye view of couchdb resulted in Jan spending an hour and a half drawing up that particular picture: Spending 
an hour on docs to get to really new people is time well spend.<br></ul><br><br>In terms of PMC chair lessons learnt: 
The goal should be to get the right people to care about the right thing. Having people finish stuff helps - and is 
infectious.<br><br>In the end as an open source project your biggest asset is your community. Motivating more people to 
join is key. If for your target audience JIRA is one step too much talk to infra to figure out how to make things 
better (and help them with the solutions).<br><br>What is fascinating about CouchDB is the whole ecosystem around the 
project. CouchDB is not just a database project hosted at Apache. It comes with a really well working replication API. 
There are implementations in js running in Browsers, there's BigCouch (dynamo in Erlang on top of CouchDB), there is an 
iOS app, there is PouchDB (the couch for your pocket), TouchDB (iOS and android implementations on top of sqlLight). 
The fun part to watch is that the idea is bigger than the project at Apache. The bigger the ecosystem the better for 
the community - there's no need to fold everything into the original project.<br><br>And of course also CouchDB is 
hiring.
