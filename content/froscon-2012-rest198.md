---
title: "FrOSCon 2012 - REST"
date: 2012-08-29T19:33:34+02:00
tags: Hacking,FrOSCon,rest,
---

# FrOSCon 2012 - REST


Together with <a href="http://thilo-fromm.de">Thilo</a> I went to FrOSCon last weekend. Despite a few minor glitches 
and the "traditional" long BBQ line the conference was very well organised and again brought together a very diverse 
crowd of people including but not limited to Debian developers, OpenOffice people, FSFE representatives, KDE and Gnome 
developers, people with background in Lisp, Clojure, PHP, Java, C and HTML5.<br><br>The first talk we went to was given 
by <a href="http://www.adayinthelifeof.nl/">JThijssen</a> on <a 
href="http://programm.froscon.de/2012/events/906.html">REST in practice</a>. After briefly introducing REST and going a 
bit into Myths and false believes about REST he explained how REST principles can be applied in your average software 
development project.<br><br>To set a common understanding of the topic he first introduced the four steps <a 
href="http://martinfowler.com/articles/richardsonMaturityModel.html">REST Maturity Model</a>: Step zero means using 
plain old xml over http for rpc or SOAP. Nothing particularly fancy here - even to some extend breaking common 
standards related to http. Going one level up means modeling your entities as resources. Level two is as simple as 
using the http verbs for what they are intended - don't delete anything on the other side just by using a GET request. 
Level three finally means using hypermedia controls, HATEOS and providing navigational means to decide on what to do 
next.<br><br><b>Myths and legends</b><br><br>Rest is always http - well, it is transport agnostic. However mostly it 
using http for transport.<br><br>Rest equals CRUD - though not designed for that it is often used for that task in 
practice.<br><br>Rest scales - as a protocol yes, however of course that does not mean that the backend you are talking 
to does. All Rest does for you is to give you a means to horizontally scale without having to worry too much about 
server state.<br><br><b>Common mistakes</b><br><br>Using Http verbs - if you've ever dealt with web crawling you 
probably know those stories of some server's content being deleted just be crawling a public facing web site just 
because there was a "delete" button somewhere that would trigger a delete action through an innocent looking GET 
request. The lesson learnt of those: Use the verbs for what they are intended to be used. One commonly confused thing 
is the usage of PUT vs. POST. Common rule of thumb that also applies to the CouchDB REST API: Use PUT if you know what 
the resulting URL should be (e.g. when storing an entry to he database and you know the key that you want to use). Use 
POST if you do not care about which URL should result from the operation (e.g. if the database should automatically 
generate a unique key for you). Also make sure to use the error codes as intended - never return error code 2?? only to 
add an xml snippet to the payload that explains to the surprised user that an error occurred including an error code. 
If you really need an explanation of why this is considered bad practice if not plain evil, think about caching 
policies and related issues.<br><br>When dealing with resources a common mistake is to stuff as much information as 
possible into one single resource for one particular use case. This means transferring a lot of additional information 
that may not be needed for other use cases. A better approach could be to allow clients to request custom views and 
joins of the data instead of pre-generating them.<br><br> When it comes to logging in to your API - don't design around 
HTTP - use it. Sure you can give a session id into a cookie to the user. However than you are left with the problem of 
handling client state on the server - which was supposed to be stateless so clients can talk to any server. You could 
store the logged in information in the client cookie - signing and encrypting that might even make it slightly less 
weird. However the cleaner approach would be to authenticate individual requests and avoid state 
altogether.<br><br>When it comes to URL design keep in mind to keep them in a format that is easy to handle for caches. 
An easy check would be to try and bookmark the page you are looking at. Also think about ways to increase the number of 
cache hits if results are even slightly expensive to generate. Think about an interface to retrieve the distance from 
Amsterdam to Brussels. The URL could be /distance/to/from - however given no major road issues the distance from 
Amsterdam to Brussels should be the same as from Brussels to Amsterdam. One easy way to deal with that would be to 
allow for both requests but to send a redirect to the first version in case a user requests the second. The semantics 
would be slightly different when asking for driving directions - there the returned answers would indeed 
differ.<br><br>The speaker also introduced a concept for handling asynchronous updates that I found interesting: When 
creating a resource hand out a 202 accepted response including a queue ticket that can be used to query for progress. 
For as long as the ticket is not yet being actively dealt with it may even contain cancellation methods. As soon as the 
resource is created requesting the ticket URL will return a redirect to the newly created resource.<br><br>The gist of 
the talk for me was to not break the Rest constraints unless you really have to - stay realistic and pragmatic about 
the whole topic. After all, most likely you are not going to build the next Twitter API ;)<br><br><br>
