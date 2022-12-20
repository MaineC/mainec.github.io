---
title: "Strata EU - part 4"
date: 2012-10-28T20:17:36+01:00
tags: strataeu,General,
---

# Strata EU - part 4


The rest of the day was mainly reserved for more technical talks: Tom Wight introducing the merits of MR2, also known 
as YARN. Steve Loughran gave a very insightful talk on the various failure modes of Hadoop – though the Namenode is 
like the most obvious single point of failure there are a few more traps waiting for those depending on their Hadoop 
clusters: Hadoop does just find with single harddisks failing. Failing single machines usually also does not create a 
huge issue. However what if the switch one of your racks is connected with fails? Suddenly not just one machine has to 
be re-replicated but a whole rack of machines. Even if you have enough space in your cluster left, can your network 
deal with the replication traffic? What if your cluster is split in half as a result? Steve gave an introduction to the 
various HA configurations available for Hadoop. There's one insight I really liked though: If you are looking for SPOFs 
in your system – just carry a pager … and wait.<br><br>In the afternoon I joined Ted Dunning's talk on fast kNN soon to 
be available in Mahout – the speedups gained really do look impressive – just like the fact that the algorithm is all 
online and single pass.<br><br>It was good to meet with so many big data people in two days – including Sean Owen who 
joined the Data Science Meetup in the evening.<br><br>Thanks to the O'Reilly Strata team – you really did an awesome 
job making Strata EU an interesting and very well organised event. If you yourself are still wondering what this big 
data thing is and in what respect it might be relevant to your company Strata is the place to be to find out: Though 
being a tad to high-level for people with a technical interest the selection of talks is really great when it comes to 
showing the wide impact of big data applications from IT, the medical sector right up to data journalism.<br><br>If you 
are interested in anything big data, in particular who to turn the technology into value make sure you check out the 
conferences in New York and Santa Clara. Also all keynotes of London were video taped and are available on YouTube by 
now.
