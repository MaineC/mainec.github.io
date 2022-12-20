---
title: "Async decision making"
date: 2017-05-16T08:45:35+02:00
tags: [Open Source, async, inner source ]
categories: [Open Source]
---

# Async decision making


This is the second in a series of posts on inner source/open source. Bertrand
Delacretaz gave an interesting talk on how to avoid meetings by introducing an
async way of making decisions.

<br><br>
He started off with a little anecdote related to Paul Graham's <a href="https://s.apache.org/ms">maker's
vs. manager's schedule</a>: Bertrand's father was a carpenter. He was working in
the same house that his family was living in, so joining the family for lunch
was common for him. However there was one valid excuse for him to skip lunch:
"I'm glueing." How's that? Glueing together a chair is a process that cannot be
interrupted once started without ruining the entire chair - it's a classical
maker task that can either be completed in one go, or not at all.

<br><br>
Software development is pretty similar to that: People typically need several
hours of focus to get anything meaningful done, in my personal experience at
least two (for smaller bugs) or four (for larger changes). That's the motivation
to keep forced interruptions low for development teams.

<br><br>
Managers tend to be on a completely different schedule: Context switching all
day, communicating all day adding another one hour meeting to the schedule
doesn't make much of a difference.

<br><br>
The implication of this observation: Adding one hour of meeting time to an
engineer's schedule comes with an enourmous cost if we factor the interruption
into the equation. Adding to the equation that lots of meetings actually fail
for various reasons (lack of preparation, lack of participants getting prepared,
bad audio or video quality, missing participants, delayed start time, bad
summarisation) it seems valid to ask if there is a way to reduce the number of
face to face meetings while still remaining operational.

<br><br>
As communication still remains key to a functional organisation, one approach
taken by open development at Adobe (as well as at the Apache Software Foundation
really) is to differentiate between things that can only be discussed in person
and decisions that can be taken in an asynchronous fashion. While this doesn't
reduce the amount of time communicating (usually quite the contrary happens) it
does allow for participants to participate pretty much on their own schedule
thus reducing the number of forced interruptions.

<br><br>
How does that work in practice? In Bertrand's experience decision making tends
to be a four step process: Coming from an open brainstorming sessions, options
need to be condensed, consensus established and finally a decision needs to be made.

<br><br>
In terms of tooling in his experience what works best is to have one and only
one shared communication medium for brainstorming. At Apache those are good old
mailing lists. In addition there is a need for a structured issue tracker/ case
management tool to make options and choices obvious, decisions visible and
archived.

<br><br>
When looking at tooling we are missing one important ingredient though: Each
meeting needs extensive preparation and thourough post processing. As an example
lets take the monthly Apache board of directors' meeting: It's scheduled to last
no longer than two hours. Given each of hundreds of projects are required to
report on a quarterly basis, given that executive officers need to provide
reports on a monthly basis, given that each month at least one major decision
item comes up and given that there is still day to day decisions about personel,
budget and the like to be taken: How does reducing that to two hours work? The
secret sauce is a text file in svn + a web frontend called whimsy to it. 

<br><br>
Directors will read through those reports ahead of the meeting. They will add
comments to them (which will be mailed automatically to projects), often those
comments are used by directors to communicate with each other as well. They will
pre-approve reports, they will mark them for discussion if there is something
fishy. Some people will check projects' lists to match that up with what's being
discussed in the report, some will focus on community stuff, some will focus on
seeing releases being mentioned. If a report gets enough pre-approvals an no
mark "to be discussed" they are not being shown or touched in the real meeting.

<br><br>
That way most of the discussion happens before the actual meeting leaving time
for those issues that are truely contentious. As the meeting is open for anyone in
te foundation to attend questions raised beforehand that could not be resolved
in writing can be answered in the voice call fairly quickly.

<br><br>
Speaking of call: How does the actual meeting proceed? All participants dial in
via good old telephone. Everyone is on a telephone so the issue of "discussions
among people in the same room are hard to understand for remote participants"
doesn't occur. In addition to telephone there's an IRC backchannel for
background discussion, chatter, jokes and less relevant discussion. All
discussion that has to be archived and that relates to discussions is kept on
the voice channel though. During the meeting the board's chair is moderating
through the agenda. In addition the secretary will make notes of who attended,
which discussions were made and which arguments exchanged. Those notes are being
shared after the meeting, approved at the following month's meeting and
published thereafter. If you want to dig deeper into any project's history,
there's tooling to drill down into meeting minutes per project until the very
beginning of the foundation.

<br><br>
Does the above make decision making faster? Probably not. However it enables an
asynchronous work mode that fits best with a group of volunteers working
together in a global, distributed community where participants do not only live
in different geographies and timezones but are on different schedules and
priorities as well.

