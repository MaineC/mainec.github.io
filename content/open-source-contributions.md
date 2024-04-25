---
title: "How hard can it be: Open Source contributions"
date: 2024-04-25T12:13:12+01:00
tags: [open source, InnerSource, contributions, learning]
---

# How hard can it be: Open Source contributions

"Sharing is caring - if only more downstream users simply contributed to the open source software that they depend upon." - a thought that has crossed my mind more than once in the past decades. Except - for your average software engineer in industry "contributing to open source" is anything but simple. In addition it's anything but obvious why - on top of daily work - one should commit time to open source. Where should that time come from if deadlines already are tight?

## Why should I care?

So unless you've been living under a rock and pretending to be a lone hero coding away in the dark most likely a lot of your daily work relies on open source: That starts with your operating system (at least the one that your production workload is deployed on). It continues with your programming language. Most likely build tooling and package management as well. How about logging - both, the libraries in your code as well as the data analysis stack in your backend? Is there a search box anywhere in your application - chances are it's backed by Apache Lucene. How about data storage? I'm not even trying to dig into stuff that happens in the browser.

"But I can't be involved in all of them." I hear you say. As a first step, trim down the list you created above to components your business relies on - the ones you cannot remove or replace in a matter of days. Those are the ones where you want to learn quickly if there's a security issue, or worse if the project is in the process of shutting down or being superseded by something else. Those are candidates to dig deeper. Dig deeper here means figuring out where the community of the project generally meets to discuss future developments, roadmap, project strategy. These days, a lot happens on GitHub, GitLab and the likes. However there are still projects relying on good old mailing lists, IRC, but also Slack, Discourse or similar systems. Often you will find out where the community meets in their README, on their webpage or on a page dedicated to new contributors. (Caveat: Not all of that may be open for public discussion if the open source project you are looking at is single vendor.)

_So your first reason to be involved:_ Your business vitally depends on an open source project.

"So I just sit down for an hour, checkout the project, make a modification and send it as a pull request, right?" I hear you say. Don't! That will only lead to frustration. Chances are the project uses a language you are not familiar with, a build system you have to get used to and the modification you are making isn't even welcome - leading to you having spent a week for nothing. Instead: Figure out where the project's community meets. Chances are in addition to the source repo you have already found, there is an issue tracker you can follow - more likely on their contributing docs you will find links to mailing lists (did I mention that I have grey hair?), IRC (more grey hair?), Slack, community forums, Discord, Mattermost etc. There you will find all of the unstructured communication that happens outside of issue trackers. People helping users get up and running. People helping contributors getting up and running. People discussin strategy and roadmap. Even job boards if the project is popular enough to get more than the occasional yearly job ad on their communication channels. Dedicate an hour or two each week to just follow along. Very soon you will notice that you are able to answer at least basic questions of people who joined after you. Do that and help the project get time back by responding to these questions on their channels. As a result you will better remember what you learned through having used active recall. In addition over time people will remember your name.

_Your second reason to be involved:_ Learn more about both, project and community and have your name known.

Pro-tip: Larger projects are often very well organised including offering onboarding support, office hour calls, dedicated staff for helping newcomers. On the flip side tiny projects tend to be a lot more relaxed with people both, happy to help you and happy about your help. Which to prefer is up to you.

_Your third reason to be involved:_ Not only will you learn more about the project itself - you will also be exposed to different ways of building, testing, documenting and enforcing coding guidelines. A lot of what teams typically cover in onboarding has to scale in your average open source project to much higher numbers: Out of 100 users, only one will turn in a contributor. Out of 100 contributors, only one will turn into someone who sticks around for long turning into a regular committer - as in someone committed to the project. As a result a lot of what is implicit in company teams tends to be written down explicitly for open source projects to the point where it is automatically enforced, documented to a level where a lot of questions can be answered in a self-service kind-of way or automated to free up precious time. A ton of these practices over time have been carried over to professional software development teams. A ton is still left to carry over.

_Your forth reason to be involved:_ Not only will you learn new technical ways of working. Often open source communities span multiple continents, cultures, timezones, companies. "Let's have a quick call to discuss this." doesn't scale. Neither does any kind of coffee-machine/ desk-bound conversation. Instead methods had to be found to build bridges across these gaps - and find a way to collaborate that builds [a tide that lifts the boats of everyone](https://ospoplusplus.com/blog/all-the-boats-must-rise). As a result not only will you see communication that puts a strong emphasis on async. You will also see very intentional use of in-person communication. You will also see very intentional way of negotiating features rooted in the [economics of vendor neutrality](https://www.sfscon.it/speakers/myrle-krantz/).

## So how exactly do I get started again?

Here's your checklist:

Based on your business interest and risk - but also based on your personal interest - chose an open source project that you want to dedicated an hour or two per week to. Then:

* Figure out where to find your favourite project: Where do they host version control? Where's the issue tracker? Where's the webpage? Is there a "how to contribute" document anywhere in the sourcecode or on the webpage?
* Based on the information gathered above, figure out how to best join the conversation of your project. Most likely only knowing where PRs and issues come in is far from enough.
* Follow the conversations for a couple weeks.
* Notice how you naturally start answering questions of others.
* Notice how after a bit of time potential for modifications is obvious.
* Notice also how friction to send a ping when a PR falls through the cracks reduces substantially because you know the people involved as well as their constraints.

Finally: Watch out for chances to meet in person - or over a virtual cup of tea :)

## Gaining by sharing and building bridges

As a result I tend to emphasize the chance to gain by sharing in open source. In addition through participation you will be able to build bridges - not only to the project itself. By practising to change your perspective that will also become a lot easier when communicating across the limits of your own local team.
