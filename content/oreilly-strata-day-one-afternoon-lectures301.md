---
title: "O'Reilly Strata - day one afternoon lectures"
date: 2011-02-13T22:18:04+01:00
tags: [SFO,strataconf,Data Analytics,General,]
---

# O'Reilly Strata - day one afternoon lectures


<h2>Big data at startups - Info Chimps</h2><p>As a startup to get good people there is no other option then to grow 
your own: Offer the option to gain a lot of experience in return for a not so great wage. Start out with really great 
hires:</p><ul><li>People who have the &quot;get shit done gene&quot;: They discover new projects, are proud to 
contribute to team efforts, are confident in making changes to a code base probably not known before hand. To find 
these you should ask open ended questions in interviews.</li><li>People who are passionate learners, that use the tools 
out there, use open code and are willing to be proven wrong.</li><li>People who are generally fun to work 
with.</li></ul><p>Put these people on small, non-mission-critical initial projects - make them fail on parallel tasks 
(and tell them they will fail) to teach them to ask for help. What is really hard for new hires is learning to deal 
with git, ssh keys, command line stuff, what to do and when to ask for help, knowing what to do when something 
breaks.</p><p>Infochimps uses Kanban for organisation: Each developer has a task he has chosen at any given point in 
time. He is responsible for getting that task done - which may well involved getting help from others. Being 
responsible for a complete features is one big performance boost once the feature truely goes online. Code review is 
being used for teachable moments - and in cases where something really goes wrong.</p><p>Development itself is 
organised to optimise for developers' joy - which usually means to take Java out of the loop.</p><h2>Machine learning 
at Orbitz</h2><p>They use Hadoop mostly for log analysis. Also here the problem of fields or whole entries missing in 
the original log format was encountered. To be able to dynamically add new attributes and deal with growing data 
volumns they went from a data warehouse solution to Apache Hadoop. Hadoop is used for data preparation before training, 
for training recommender models, for cross validation setups. Hive has been added for ad-hoc queries usually issued by 
business users.</p><h2>Data scaling patterns at LinkedIn</h2><p>When scaling to growing data LinkedIn developers 
started gathering a few patterns that helped make dealing with data easier:</p><ul><li>When building applications 
constantly monitor your invariants: It can be so frustrating to run an hour long job just to find out at the very end 
that you made a mistake during data import.</li><li>Have a QA cluster, have versioning on your releases to allow for 
easy rollback should anything go bad. Unit tests go without saying.</li><li>Profile your jobs to avoid bottlenecks: Do 
not read from the distributed cache in a combiner - do not reuse code that was intended for a different component 
without thorough review.</li><li>Dealing with real world data means dealing with irregular, dirty data: When generating 
pairs of users for connect recommendation, Obama caused problems as he is friends with seemingly every american. 
</li></ul><p>However the biggest bottleneck: IO during shuffling as every map talks to every reducer. As a rule of 
thumb, do most work on the map side and minimise data sent to reducers. This also applies to many of the machine 
learning M/R formulations. One idea for reducing shuffling load is to pre-filter on the map side with bloom 
filters.</p><p>To serve at scale:</p><ul><li> Run stuff multiple times.</li><li> Iterate quickly to get fast 
feedback.</li><li> Do AB testing to measure performance.</li><li> Push out quickly for feedback.</li><li> Try out what 
you would like to see.</li></ul><p>See also <a href="http://sna-projects.com/blog">sna-projects.com/blog</a> for more 
information.</p>
