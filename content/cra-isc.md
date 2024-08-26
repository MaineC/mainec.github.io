---
title: "Open Source, InnerSource, CRA?"
date: 2024-08-26T17:17:00+02:00
tags: [innersource, open source, cra, isc, oss, upstream]
---


# Open Source, InnerSource, CRA?

A couple days ago on Mastodon I read a post from by Robert Sander (here translated from German): "At FrOSCon I got the impression the FLOSS community is aging together. Where are people in their mid-twenties, new people entering the community?" 

"Entering the open source community" - what does that even mean? Does it mean creating a public GitHub repo and publishing source code there? For years when employers wanted to show how active employees are in Open Source they would point to projects on GitHub under their own org. Often employer branding was the most important motivation for a lot of these companies - and the weakest reason when faced with economic challenges.

In addition taking that path implies that developers do not benefit from being part of and learning from a community that spans multiple corporations, cultures and timezones. It also does not add more hands to the group of people supporting existing and wide spread existing open source projects.

"But telling my colleagues to participate upstream didn't work" - for what reason does upstream participation fail? Developers and management both lack a deep understanding of the benefits of investing working hours into a project they believed they could use for free. Developers are afraid to participate due to the public nature of open source: All mistakes, every little question will be made in public, where it's archived, where it will surface in web searches. There are open source projects - in particular those operating according to an open core model - where outside collaboration is limited to submitting issues. For patches often only those are accepted that are in line with the business strategy of the backing entity. In addition participation there tends to end where strategy and roadmaps are decided, inherently limiting the level of impact an outsider can have - and limiting the motivation to invest time and energy.

Looking at each of these three reasons in turn:

## Better understanding

Outside of core open source circles - how well does your average software engineer understand the business reasons for investing precious time in open source? I would argue that very few people using open source would be able to tell even for their core dependencies who is backing these projects. How sustainable financing of the people backing these projects is setup. What the difference is between single vendor, VC backed open source vs. single vendor, bootstrapped vs. vendor neutral, foundation backed - and what that means in terms of risk assessment for anyone downstream using projects in any of these models.

So far other than the occasional high impact security issue being blissfully unaware of these details didn't pose more than minor annoyances at least for your average downstream user. At the very worst case it meant having to switch to another dependency in case of a license change or end of life of a project.

With the CRA this changes to some extend: With a higher level of liability for sold software products there is a higher motivation to have security issues in downstream projects fixed. However maintaining those fixes independently is a very costly matter: Instead getting them integrated in the upstream project does prove a lot cheaper in the long run. As a result there's now one more reason to be able to participate in upstream open source projects.

## Gaining experience and learning

More than a decade ago I learnt that learning needs an environment where students feel safe, where they understand that mistakes will not be held against them. What a contrast to how work in open source is organised - with all communication happening in public, on channels that are archived, searchable and linkable - preferably for a very long time.

What if instead developers could practise open source ways of working internally - after all even withing corporations there are lots of teams, working on components that are not all fully independent. InnerSource translates collaboration patterns often found in open source and translates those into patterns that help solve challenges commonly found in cross team collaboration within corporations.

Interestingly people that have been practising InnerSource for several years over time were able to dig ever deeper - and noticed how a lot of the discussion points in open source around governance, communication, expectation management and the like are exactly the same as they already know from their InnerSource experience. As a result, becoming active upstream turns out to be a whole lot easier.

## Gaining agency

Bringing the two aspects together: With growing discussion around re-licensing I do believe teams are starting to be aware of how open source projects are different from each other - not only in terms of license but also in terms of governance.

InnerSource - in particular the pattern about governance levels - helps teams get more hands on experience what different levels of openess and neutrality mean for daily project decisions. In addition InnerSource teaches that the walls between teams are fairly small and can easily be overcome - giving agency back to engineers, teaching them just how easy and helpful it is to get involved in all of the things they depend on - both, internally (using InnerSource) as well as externally (participating naturally in Open Source projects).

## Summarizing

 

