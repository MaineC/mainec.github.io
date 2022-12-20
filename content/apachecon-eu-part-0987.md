---
title: "ApacheCon EU - part 09"
date: 2012-11-18T20:54:29+01:00
tags: [tfidf,Apache Con,ApacheCon,Lucene,ap,apacheconeu,Solr,]
---

# ApacheCon EU - part 09


In the Solr track <a 
href=”http://www.slideshare.net/kucrafal/battle-of-the-giants-apache-solr-vs-elasticsearch”>Elastic Search and Solr 
Cloud went into competition</a>. The comparison itself was slightly apples-and-oranges like as the speaker compared the 
current ES version based on Lucene 3.x and Solr Cloud based on Lucene 4.0. During the comparison it still turned out 
that both solutions are more or less comparable - so choice again depends on your application. However I did like the 
conclusion: The speaker did not pick a clear winner in terms of projects. However he did have another clear winner: The 
user community will benefit from there being two projects as this kind of felt competition did speed up development 
already considerably.<br><br>The day finished with hoss' Stump the Chump session: The audience was asked to submit 
questions before the session, the jury was than asked to pick the winning question that stumped Hoss the 
most.<br><br>Some interesting bits from that question: One guy had the problem of having to provide somewhat diverse 
results in terms e.g. manufacturers in his online shop. There are a few tricks to deal with this problem: a) clean your 
data - don't have items that use keyword spamming side by side with regular entries. Assuming this is done you could b) 
use grouping to collapse items from the same manufacturer and let the user drill deeper from there. Also using c) a 
secondary sorting value can help - one hint: Solr ships with a random value out of the box for such cases. <br><br>For 
me the last day started with <a href="http://people.apache.org/~hossman/ac2012eu/">hossman's session on boosting and 
scoring tricks with Solr</a> - including a cute reference for explaining TF-IDF ranking to people (see also <a 
href="http://twitter.com/MaineC/status/256361114923851776">a message tweeted earlier for an explanation</a> of what a 
picture taken during my wedding has to do with ranking documents):<br><br><center><br><a 
href="http://twitpic.com/bbb9lg" title="Share photos on twitter with Twitpic"><img 
src="http://twitpic.com/show/large/bbb9lg.jpg" width="400" alt="Share photos on twitter with 
Twitpic"></a><br></center><br><br>Though TF-IDF is standard IR scoring it probably is not enough for your application. 
There's a lot of domain knowledge that you can encode in your ranking:<br><ul><br><li>novelty factors - number of 
ratings/ standard deviation of ratings - ranks controversial items on top that might be more interesting than just 
having the stuff that everyone loves<br><li>scarcity - people like buying what is nearly sold out<br><li>profit 
margin<br><li>create your score manually by an external factor - e.g. popularity by association like categories that 
are more popular than others or items that are more popular depending on the time of day or year<br></ul><br><br>There 
are a few sledge hammers people usually think of that can turn against you really badly: Say you rank by novelty only - 
that is you sort by date. The counter example given was the case of the AOL-Time Warner merger - being a big story news 
papers would post essays on it, do evaluations etc. However also articles only remotely related to it would mention the 
case. So be the end of the week when searching for it you would find all those little only remotely relevant articles 
and have to search through all of them to find the really big and important essay.<br><br>There are cases where it 
seems like only recency is all that matters: Filter only for the most recent items and re-try only in case of no 
results. The counter example is the case where products are released just on a yearly basis but you set the filter to 
say a month. This way up until May 31 your users will run into the retry branch and get a whole lot of results. However 
when a new product comes out on June first from that day onward the old results won't be reachable anymore - leading to 
a very weird experience for those of your users who saw yesterday's results.<br><br>There were times when scoring was 
influenced by keyword stuffing to emulate higher scores - don't do that anymore, Solr does support sophisticated per 
field and document boosting that make such hacks superfluous.<br><br>Instead rather use edismax for weighting fields. 
Some hints on that one: configure omitNorms in order to avoid having keyword stuffing influence your ranking. Configure 
omitTermFrequencyAndPosition if the term frequency in any document does not really tell you much e.g. in case of small 
documents only.<br><br>With current versions of Solr you can use your custom scoring per field. In addition a few ones 
are shipped that come with options for tweaking - like for instance the sweetSpotSimilarity wher you can tell the 
scorer that up to a certain length no length penalisation should happen.<br><br>Create your own boost functions that in 
addition to TF-IDF rely on rating values, click rates, prices or category influences. There's even an external file 
field option to allow you to load your scoring value per document or category from an external file that can be updated 
on a much more frequent basis than you would otherwise want to re-index all documents in your solr. For those suffering 
from the "For business reasons this document must come first no matter what the algorithm says" syndrom - there's a 
query elevation component for very fine grained tuning of rankings per query. Keep in mind so that this can easily turn 
into a maintanance nightmare. However it can be handy when quickly fixing a highly valuable business based use case: 
With that component it is possible to explicitly exclude documents from matching and precisely setting where to rank 
individual documents.<br><br>When it comes to user analytics and personalisation many people think of highly 
sophisticated algorithms that need lots of data to be trained. Yes Mahout can help you with personalisation and 
recommendation - but there are a few low hanging fruits to grab before:<br><ul><br><li>Use the history of registered 
users or those you can identify through cookies - track the keywords they are looking for, the sort and filter 
functions commonly used.<br><li>Bucket people by explicit or implicit demographics.<br><li>Even just grouping people by 
the os and browser they use can help to identify preferences.<br></ul><br><br>All of this information is relatively 
cheap to get by and can be used in many creative ways:<br><ul><br><li>Provide default sort and filter functions for 
returning users.<br><li>Filter on the current query but when scoring take the older query into account.<br><li>Based on 
category facet used before do boosting in the next search assuming that the two queries are 
related.<br></ul><br><br>Essentially the goal is to identify three factors for your users: What is their preference, 
what is the differentiator and what is your confidence in your estimation.<br><br>Another option could be to use the 
SweetSpotPlateau: If someone clicked on a price range facet on the next related query do not hide other prices but 
boost those that are in the previous facet.<br><br>One side effect to keep in mind: Your cache hit rate will go down 
now you are tailoring your results to individual users or user groups.<br><br>Biggest news for Lucene and Solr was the 
release of Lucene 4 - <a href=”http://www.h-online.com/open/news/item/Lucene-and-Solr-4-0-released-1728616.html”>find 
more details online</a> in an article published recently.
