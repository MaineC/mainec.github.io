---
title: "Book: Search Patterns"
date: 2012-07-28T20:41:31+02:00
tags: [search,Science,review,patterns,book,Design,oreilly,]
---

# Book: Search Patterns


I got the book months ago during FOSDEM - the O'Reilly book table always is a pretty dangerous place as a meeting point 
for me: Search Patterns - Design for Discovery is one of those small, deceivingly beautiful books that manages to 
explain effective search engine design by focusing on the end user needs but going into some detail concerning the 
basics of search engine backends as well.<br><br>We use them on a daily basis not only for finding content on the web 
but also for navigating shopping sites, discovering news content and even finding articles on blogs and open source 
project pages. Many discovery tasks can be easily expressed as a search problem and as a result tackled with by now 
standard off the shelve software like Apache Lucene - or event the commercial counterparts from the enterprise search 
market. Still oftentimes search is perceived as being made up of simple a small box that users type (typically one or 
two term) queries into and that as a result show a list of some ten links.<br><br>After setting the stage for search in 
the first chapter the book goes into some more detail in "The anatomy of search". In a very approachable way it 
explains all the components from user constraints, graphical interface, the basics of retrieval and evaluating search 
performance in terms of precision and recall. The third chapter shows some bahavioural patterns that make discovery 
easier for users - from incrementally constructing the answer, progessively disclosing more and more detail up to being 
predictable.<br><br>Finally the design patterns as identified by the authors are introduced. Pretty obvious to those 
working in the field but well explained to those not intimately familiar with the topic:<br><br><ul><br><li>Though 
perceived as a mere convenience to type less by users, autocomplete can actually help guide the user's search in case 
of ambiguities and can help avoid imprecise results.<br><li>Expected as it might be by users, presenting the best 
result first actually goes a long way when building credibility for a search engine. Having more precise queries to 
guide e.g. as a result of autocomplete helps here. So does having strong ranking criteria to build up a compelling 
ranking function that is used by default (even though others might be offered as an alternative for users to explore 
more and different results).<br><li>Federated search has both - advantages (integrating otherwise isolated silos of 
knowledge) but also disadvantages (it's speed being dominated by the slowest connected search engine).<br><li>Facetted 
navigation is pretty much standard for any major search engine - giving the user the option to start with  a broad 
query that returns an overwhelming amount of results but guiding the user when refining the query is one major way of 
driving searches.<br><li>Offering personalisation tends to be one beloved feature though it is particularly hard to 
implement and needs a good deal of user data to work well. Usually there are features that require less work to get 
done that are more promising to start with.<br><li>Pageination is as much standard to be expected by users - though its 
implementation can differ: Though we are used to clicking the next button, this actually may not make much sense and 
just lead to interrupting the user's flow. Much more appealing - but sometimes also confusing - can be interfaces that 
allow for simply extending the result page when scroling to it's end.<br><li>Structured results provide a way to give 
the user more than just an outlink - triggered by specific searches it may be possible to directly answer the user's 
question instead of linking to content that answers it.<br><li>Actionable results are a way for the user to get active 
- either by voting on results, bookmarking them or sharing them with others.<br><li>Unified discovery is about 
accepting that search always plays a role in a bigger context and has to play well with the discovery mode the user is 
in: When searching for "apple" while browsing the category "electronics" it's rather unlikely that I am looking for the 
fruit. Similarly search should take context into account and support me seamlessly when switching from discovery to 
directed search and back to discovery mode.<br></ul><br><br>The book concludes by going into some detail on example 
search engines and presenting some features that are not yet commonplace but might change the world by employing search 
in new and creative ways.<br><br>Easy to read, well written, several nice examples to make the technical points simpler 
to understand. Definitely a good read for domain experts planning to build a search engine, designers trying to 
understand the basics of building effective search engines and engineers struggling for words to explain why a 
seemingly little box can cause a whole lot of pain when done wrong but a whole lot of joy when done right.
