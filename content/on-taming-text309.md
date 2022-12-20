---
title: "On Taming Text"
date: 2013-01-01T20:21:19+01:00
tags: [Mahout,Lucene,review,book,Science,]
---

# On Taming Text


This time of the year I would usually post pictures of my bicycle standing in the snow somewhere in Tierpark. This year 
however I was tricked into using public transport instead: a) After my husband found a new job, we now share some of 
the route to work - and he isn't crazy going by bike when it's snowing. b) I got myself a Nexus7 earlier this month 
which obsoleted having to take paper books with me when using public transport. c) Early in December Grant Ingersoll 
asked me for feedback on the by now nearly finished  <a href="http://www.manning.com/ingersoll/">"Taming Text</a> 
(currently available as MEAP at Manning). So I even had a really interesting book to read on my way home.<br><br>Up to 
mid-December "Taming Text" was one of those books that always were very high on my to-read list: At least from the TOC 
it looked like the book to read if ever you wanted to write a search application. So I was really curious which topics 
it would cover and how deep explanations would go when I got the offer to read and review the 
book.<br><br><h2>tl&dr</h2><br><br>Short version: If you are building search applications - that is anything that makes 
a search box available on a web site, be it an online store or a new article archive - this is the book to read. It 
covers all the gory details of how to implement features we have come to take for granted when using search: Type 
ahead, spelling correction, facetting, automatic tagging and more. The book motivates what the value of these features 
is from the user side, explains how to implement these features with proven technologies like Apache Lucene, OpenNLP, 
and Mahout and how those projects work internally to provide you with the functionality you need.<br><br><h2>Longer 
summary</h2><br><br>Search can be as easy as providing one box in some corner on your web site that users can type into 
to find relevant pages. However when thinking about the topic just a little more some more handy features that users 
have come to expect come to mind: <br><ul><br><li>Type ahead to avoid superfluous typing - it also comes in handy to 
avoid spelling errors and to know exactly which query actually will return a decent number of 
documents.<br><li>Spelling correction is pretty much standard - and avoids user frustration with hard to spell query 
terms.<br><li>Facetting is a great way to discover and explore more content in particular when there are a few 
structured attributes attached to your items (prices to books, colors to cars etc).<br><li>Named Entity Recognition is 
well known among publishers who use automatic tagging services to support their staff.<br></ul><br><br>The authors of 
Taming Text decided to structure the book around the task of building an automatic <a 
href="http://en.wikipedia.org/wiki/Question_answering">Question Answering</a> system. Throughout the book they present 
technologies that need to be orchestrated to build such an application but are each valuable in it's own 
right.<br><br>In contrast to <a href="http://shop.oreilly.com/product/9780596802288.do">Search Patterns</a> (which is 
focused mainly on the product manager perspective and contains much less technical detail) Taming Text is the book to 
read for any engineer working on search applications. In contrast to books like <a 
href="http://shop.oreilly.com/product/9780596529321.do">Programming Collective Ingelligence</a> Taming Text takes you 
one level further by not only showing the tools to use but also explaining their inner workings so that you can adapt 
them exactly to your use case. To me, Taming Text is the ideal complimentary book to <a 
href="http://manning.com/owen/">Mahout in Action</a> (for the machine learning part) and <a 
href="http://www.manning.com/hatcher2/">Lucene in Action</a> for the search part.<br><br>Back in 1998 <a 
href="http://en.wikipedia.org/wiki/Unstructured_data">it was estimated</a> that 80% of all information is unstructured 
data. In order to make sense of that wealth of data we need technologies that can deal with unstructured data. Search 
is one of the most basic but also most powerful ways to analyse texts. With a good mixture of theoretical background 
and hands-on-examples Taming Text guides you through the process of building a successful search application, no matter 
if you are dealing with a vast product database that you want to make more accessible to your users, with an ever 
growing news archive or with several blog posts and twitter messages that you want to extract data from.
