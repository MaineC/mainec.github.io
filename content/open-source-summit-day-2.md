---
title: "Open source summit - Day 2"
date: 2017-10-25T12:58:31+02:00
tags: Conference, Open Source, LinuxCon
categories: Conference
---

# Open source summit - Day 2


Day two of Open Source summit for me started a bit slow for lack of sleep. The
first talk I went to was on "Developer tools for Kubernetes" by Michelle Noorali
and Matt Butcher. Essentially the two of them showed two projects (<a
href="https://github.com/azure/draft">Draft</a> and <a
href="https://github.com/azure/brigade">Brigade</a> to help ease development
apps for Kubernetes clusters. Draft here is the tool to use for developing long
running, daemon like apps. Brigade has the goal of making event driven app
development easier - almost like providing shell script like composability to
Kubernetes deployed pipelines.

<br><br>

<h2>Kubernetes in real life</h2>
In his talk on K8s in real life Ian Crosby went over five customer cases. He
started out by highlighting the promise of magic from K8s: Jobs should
automatically be re-scheduled to healthy nodes, traffic re-routed once a machine
goes down. As a project it came out of Google as a re-implementation of their
internal, 15 years old system called Borg. Currently the governance of K8s lies
with the Cloud Native Foundation, part of the Linux Foundation.
<br><br>
So what are some of the use cases that Ian saw talking to customers:
<ul>
<li>"Can you help us setup a K8s cluster?" - asked by a customer with one
monolithic application deployed twice a year. Clearly that is not a good fit for
K8s. You will need a certain level of automation, continuous integration and
continuous delivery for K8s to make any sense at all. 
<li>There were customers trying to get into K8s in order to be able to hire
talent interested in that technology. That pretty much gets the problem the
wrong way around. K8s also won't help with organisational problems where dev and
ops teams aren't talking with each other.
<li>The first question to ask when deploying K8s is whether to go for on-prem,
hosted externally or a mix of both. One factor pulling heavily towards hosted
solution is the level of time and training investment people are willing to make
with K8s. Ian told the audience that he was able to migrate a complete startup
to K8s within a short period of time by relying on a hosted solution resulting
in a setup that requires just one ops person to maintain. In that particular
instance the tech that remained on-prem were Elasticsearch and Kafka as
services.
<li>Another client (government related, huge security requirements) decided to
go for on-prem. They had strict requirements to not connect their internal
network to the public internet resulting in people carrying downloaded software
on USB sticks from one machine to the other. The obvious recommendation to ease
things at least a little bit is to relax security requirements at least a little
bit here.
<li>In a third use case the customer tried to establish a prod cluster, staging
cluster, test cluster, one dev cluster per developer - pretty much turning into
a maintainance nightmare. The solution was to go for a one cluster architecture,
using shared resources, but namespaces to create virtual clusters, role based
access control for security, network policies to restrict which services can
talk to each other, service level TLS to get communications secure. Looking at
CI this can be taken one level furter even - spinning up clusters on the fly
when they are needed for testing.
<li>In another customer case Java apps were dying randomly - apparently because
what was deployed was using the default settings. Lesson learnt: Learn how it
works first, go to production after that.
</ul>

<h2>Rebuilding trust through blockchains and open source</h2>
Having pretty much no background in blockchains - other than knowing that a
thing like bitcoin exists - I decided to go to the introductory "Rebuilding
trust through blockchains and open source" talk next. Marta started of by
explaining how societies are built on top of trust. However today (potentially
accelerated through tech) this trust in NGOs, governments and institutions is
being eroded. Her solution to the problem is called Hyperledger, a trust
protocol to build an enterprise grade distributed database based on a
permissioned block chain with trust built-in.
<br><br>
Marta went on detailing eight use cases:
<ul>
<li>Cross border payments: Currently, using SWIFT, these take days to complete,
cost a lot of money, are complicated to do. The goal with rolling out block
chains for this would be to make reconcillation real-time. Put information on a
shared ledger to make it audible as well. At the moment ANZ, WellsFargo, BNP
Paribas and BNY Mellon are participating in this POC.
<li>Healthcare records: The goal is to put pointers to medical data on a shared
ledger so that procedures like blood testing are being done just once and can be
trusted across institutions.
<li>Interstate medical licensing: Here the goal is to make treatment
re-imbursment easier, probably even allowing for handing out fixed-purpose
budgets.
<li>Ethical seafood movement: Here the goal is to put information on supply
chains for seafood on a shared ledger to make tracking easier, audible and
cheaper. The same applies for other supply chains, think diamonds, coffee etc.
<li>Real estate transactions: The goal is to keep track of land title records on
a shared ledger for easier tracking, auditing and access. Same could be done for
certifications (e.g. of academic titles etc.)
<li>Last but not least there is a POC to how how to use shared ledgers to track
ownership of creative works in a distributed way and take the middleman
distributing money to artists out of the loop.
</ul>

<h2>Kernel developers panel discussion</h2>

For the panel discussion Jonathan Corbet invited five different Linux kernel
hackers in different stages of their career, with different backgrounds to
answer audience questions. The panel featured Vlastimil Babka, Arnd Bergmann,
Thomas Gleixner, Narcisa Vasile, Laura Abbott.
<br><br>
The first question revolved around how people had gotten started with open
source and kernel development and what advise they would have for newbies. The
one advise shared by everyone other than scratch your own itch and find
something that interests you: Be persistant. Don't give up.
<br><br>
Talking about release cycles and moving too fast or too slow there was a comment
on best practice to get patches into the kernel that I found very valuable:
Don't get started coding right away. A lot of waste could have been prevented if
people just shared their needs early on and asked questions instead of diving
right into coding.
<br><br>
There was discussion on the meaning of long time stability. General consensus
seemed to be that long term support really only includes security and stability
fixes. No new features. Imaging adding current devices to a 20 year old kernel
that doesn't even support USB yet.
<br><br>
There was a lovely quote by Narcisa on the dangers and advantages of using C as
a primary coding language: With great power come great bugs.
<br><br>
There was discussion on using "new-fangled" tools like github instead of plain
e-mail. Sure e-mail is harder to get into as a new contributor. However current
maintainer processes heavily rely on that as a tool for communication. There was
a joke about implementing their own tool for that just like was done with git.
One argument for using something less flexible that I found interesting:
Aparently it's hard to switch between subsystems just because workflows differ
so much, so agreeing on a common workflow would make that easier.
<li>Asked for what would happen if Linus was eaten by a shark when scuba diving
the answer was interesting: Likely at first there would be a hiding game because
nobody would want to take up his work load. Next there would likely develop a
team of maintainers collaborating in a consensus based model to keep up with
things.
<li>In terms of testing - that depend heavily on hardware being available to
test on. Think like the kernel CI community help a lot with that.
</ul>

<br><br>

I closed the day going to Zaheda Bhorat's talk on "Love would you do - everyday"
on her journey in the open source world. It's a great motiviation for people to
start contributing to the open source community and become part of it - often
for life changing what you do in ways you would never have imagined before. Lots
of love for The Apache Software Foundation in it.
