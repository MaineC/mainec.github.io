---
title: "What makes ASF projects successful"
date: 2026-09-03T08:29:28+02:00
tags: [ASF, OSS, public sector]
---

Yesterday I was invited to give a keynote at [CiviCon](https://www.civitasconnect.digital/civicon). After a brief call on the background and scope of the conference I decided to focus on the three pillars of a successful open source strategy: informed usage, upstream first and intentional publishing as a last step. Both, during hallway conversations but also in the panel moderated by Markus Beckedahl one topic came up frequently: What makes the ASF so successful, how does that differ from projects discussed at the conference which originate from the public sector. I'll be sharing some thoughts below. Feel free to add yours through a PR extending the text.

## Organisational setup

The ASF itself is a charitable foundation. As such it does not develop any code itself and does not accept donations intended to flow directly into the development of its projects. Instead it provides a thin layer of administration for the infrastructure (technical but also including marketing, security etc.) for its projects. Development costs themselves are covered by organisations paying individuals contributing to and committing to projects. That implies a strong "those who do the work decide on direction" operating model. It also implies that it's easy to state that projects that don't receive any contributions anymore can safely be moved to the attic: If apparently nobody is interested in further development, there's no need to keep the project alive and go look for funding for it.

This model works particularly well if either the target users of the project are themselves technologically savvy and interested as well as capable to fix issues - or if there is an existing ecosystem of service providers and hosting companies willing to support the project who have customers willing to pay for that support. Building this ecosystem gets trickier the further one moves towards software that is primarily used by end users, who are unable to pay for support.

## Definition of a "user"

One important clarification that seems needed: Within the ASF, no matter if we talk about users, contributors or members - we always talk about individuals. Those individuals may be contributing on their free time, more often than not they are paid for by their employers investing strategically in the projects that they have built their business on. Committership and membership is not tied to corporations, it is tied to the individual - so changing jobs keeps roles within the ASF. As a result a signal of expertise is attached to the individual doing the work - not the entity paying membership fees. Cases of "our employees contributed x% to project" types of communication did happen in the past - I would strongly advise staying away from such simplistic metrics especially in marketing used widely: Metrics like this are notoriously hard to measure. Did your employees work for you when they made these contributions? Does that even count? Did they do the work on or off work schedule? Counting is bound to get messy leading to muddied messaging.

## Decision making

Decision making at least in the German public sector seems to be highly hierarchical and top down. This is in contrast to ASF projects where hierarchies are by design very flat: Everyone working on a project is expected to leave their affiliation at the door and act in the best interest of the project - on equal footing with every other committer. And still this doesn't result in chaos. How so?

There are projects following standards defined externally, so the general direction is very clear. There are other OSS projects outside of the ASF, where a lot of committers are paid for by commercial entities, so likely coordination, alignment and direction setting happens outside of the project itself. Finally there are those where direction setting happens within the project, in public and in writing. For larger communities often supported by processes around feature proposals that follow set guidelines.


## Self Serve onboarding

Common wisdom has it that out of 100 users, only one ends up making a contribution. Out of those 100 contributors only one sticks around to become a regular committer. Even when talking about individuals instead of organisations, these numbers are staggering. As a result, the projects that I'm familiar with rely on very heavy self service onboarding processes: Initially there's no need for 1:1 mentoring. Finding places where the project communicates is straight forward - there is contributing documentation detailing where discussions happen, which contribution is welcome, where to find source code, how to build it and how to submit patches.

Documentation for successful OSS projects often is awesome for the same reason: Even if not everyone reads the docs right away, being able to point to existing docs instead of having to write down things over and over again is a huge time saver - and this includes standard disclaimers added to certain types of questions.

The architecture itself often allows for extensions and plugins. That way downstream users can add their own functionality without having to make modifications to the core architecture. This saves maintenance overhead on the side of the project which now only has to keep extension points and plugin APIs as stable as possible.

## Communication

One final aspect: Important decision making communication always happens in writing - on a medium that is archived, searchable with individually linkable messages. This archive of messages serves as a baseline documentation pool - a pool that more structured documentation can be drawn from, in particular from those messages that are referenced more often than others. It also serves as the memory of projects as people move in and out.

This principle means that users can follow the project and organically become more proficient turning into contributors and committers over time. It also means that people can participate independent of their time zone - and independent of their schedule. It makes coordination of communication a lot cheaper - however it needs a high trust culture where making mistakes and communicating in the open is not only OK but welcome.

## On Free riders

One final word on people using projects without contributing back: There is no open source license forcing any contributions back. All there is are licenses that force vendors to give their users the same rights they themselves received. This often means that publishing modifications and extensions to the general public is a lot cheaper than giving each downstream users some USB stick, in particular as those downstream users in turn can make these modifications public in turn.

When choosing a vendor to role out a solution for me though, I would be careful to not only look for the cheapest option - but also make sure that vendor has the expertise needed to guarantee long term support. What better indicator of expertise than having committers in house who are sitting at the table where decisions about a project are being made, who themselves are active committers in a project and define it's future direction?

