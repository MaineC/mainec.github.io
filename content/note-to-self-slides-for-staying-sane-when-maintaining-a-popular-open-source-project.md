---
title: "Note to self - slides for staying sane when maintaining a popular open source project"
date: 2017-05-26T09:00:04+02:00
tags: Opsen Source, project management
categories: Open Source
---

# Note to self - slides for staying sane when maintaining a popular open source project


For further reference - Simon MacDonald has a great collection of good advise on
how to stay sane when running and maintaining a popular open source project.
Link here: http://s.apache.org/sanity

<br><br>
Some things he mentioned:

<br><br>
Include a README. It should tell people what the project is about but also what
the project is not about. It should have some sort of getting started guide.
Potentially link to a CONTRIBUTING doc.

<br><br>
Contribution guidelines should outline social rules like a code of conduct,
technical instructions like how to submit a pull request, a style guide,
information on how to build the project and make changes etc.

<br><br>
Add a LICENSE file - any OSS license really, because by default it won't be open
source in no jurisdiction. Add file headers to each file you publish.

<br><br>
Decide how to handle questions vs. issues: Either both in the issue tracker, or
in separate venues.

<br><br>
Add an issue template that asks the user if they searched for the issue already,
asks for expected behaviour, actual behaviour, logs, reproduction code, version
number used. A note on issues: Having many issues is a good thing - it shows
your project is popular. Having only many stale issues is a bad thing - nobody
is caring for the project anymore.

<br><br>
Close issues that don't follow the template. Close issues that are duplicates.
Close issues that are non active after asking for user input a while ago.
Repeated issues asking for seamingly obvious things: Turn those into additional
documentation. Asks for easy to add functionality: Let it sit for a while to
give others a chance to do it and get involved. Same for bugs that are easy to
fix.

<br><br>
Overall people are more difficult than code. Expect trolls to show up. Remain
empathetic, respectful but firm in your communication. Don't be afraid to say no
to external requests even if they are urgent for the requester.

<br><br>
Add a pull request template that asks for a description, related issue, type
tag. Remember that you don't have to merge every pull request.

<br><br>
Build a community: Make it easy to contribute, identify beginner bugs, document
the hell out of your project, turn contributors into maintainers, thank people
for their effort.

<br><br>
Have tests but keep build times low.

<br><br>
Add documentation, at the very least a README file, a how to contribute file,
break those files into a separate website once they grow too large. 

<br><br>
As for releasing: Automate as much as you can. Three options: time based release
schedule, release on every commit, release "when it's done".


