---
title: "Open Source Summit - Day 3"
date: 2017-10-29T09:35:15+01:00
tags: Open Source, Linux Foundation, Conference
categories: Conference
---

# Open Source Summit - Day 3


Open source summit Wednesday started with a keynote by members of the Banks
family telling a packed room on how they approached raising a tech family. The
first hurdle that Keila (the teenage daughter of the family) talked about was
something I personally had never actually thought about: Communication tools
like Slack that are in widespread use come with an age restriction excluding
minors. So by trying to communicate with open source projects means entering
illegality.
<br><br>
A bit more obivious was their advise to help raise kids' engagement with tech:
Try to find topics that they can relate to. What works fairly often are reverse
engineering projects that explain how things actually work.

<br><br>
The Banks are working with a goal based model where children get ten goals to
pursue during the year with regular quarterly reviews. An intersting twist
though: Eight of these ten goals are choosen by the children themselves, two are
reserved for parents to help with guidance. As obvious as this may seem, having
clear goals and being able to influence them yourselves is something that I
believe is applicable in the wider context of open source contributor and
project mentoring as well as employee engagement.

<br><br>
The speakers also talked about embracing children's fear. Keila told the story
of how she was afraid to talk in front of adult audiences - in particular at the
keynote level. The advise that her father gave that did help her: You can trip
on the stage, you can fall, all of that doesn't matter for as long as you can
laugh at yourself. Also remember that every project is not the perfect project -
there's always something you can improve - and that's ok. This is fairly in line
with the feedback given a day earlier during the Linux Kernel Panel where people
mentioned how today they would never accept the first patch they themselves had
once written: Be persistant, learn from the feedback you get and seek feedback
early.

<br><br>
Last but not least, the speakers advised to not compare your family to anyone,
not even to yourself. Everyone arrives at tech via a different route. It can be
hard to get people from being averse to tech to embrace it - start with a tiny
little bit of motivation, from there on rely on self motivation.

<br><br>
The family's current project turned business is to support L.A. schools to
support children get a handle on tech.

<h2>The TAO of Hashicorp</h2>

In the second keynote Hashimoto gave an overview of the Tao of Hashicorp -
essentially the values and principles the company is built on. What I found
interesting about the talk was the fact that these values were written down very
early in the process of building up Hashicorp when the company didn't have much
more than five employees, comprised vision, roadmap and product design pieces
and has been applied to every day decisions ever since.

<br><br>
The principles themselves cover the following points:
<ul>
<li>Workflows - not technologies. Essentially describing a UX first approach
where tools are being mocked and used first before diving deeper into the
architecture and coding. This goes as far as building a bash script as a mockup
for a command line interface to see if it works well before diving into coding.
<li>Simple, modular and Comosable. Meaning that tools built should have one
clear purpose instead of piling features on top of each other for one product.
<li>Communicating sequential processes. Meaning to have standalone tools with
clear APIs.
<li>Immutability.
<li>Versioning through Codification. When having a question, the answer "just
talk to X" doesn't scale as companies grow. There are several fixes to this
problem. The one that Hashicorp decided to go for was to write knowledge down in
code - instead of having a README.md detailing how startup works, have something
people can execute.
<li>Automate.
<li>Resilient systems. Meaning to strive for systems that know their desired
state and have means to go back to it.
<li>Pragmatism. Meaning that the principles above shouldn't be applied blindly
but adjusted to the problem at hand.
</ul>

<br><br>
While the content itself differs I find it interesting that Hashicorp decided to
communicate in terms of their principles and values. This kind of setup reminds
me quite a bit about the way Amazon Leadership principles are being applied and
used inside of Amazon.

<h2>Integrating OSS in industrial environments - by Siemens</h2>
The third keynote was given by Siemens, a 170 year old, 350k employees rich
German corporation focussed on industrial appliances.

<br><br>
In their current projects they are using OSS in embedded projects related to
power generation, rail automation (Debian), vehicle control, building automation
(Yocto), medical imaging (xenomai on big machines).

<br><br>
Their reason for tapping into OSS more and more is to grow beyond their own
capabilities.

<br><br>
A challenge in their applications relates to long term stability, meaning
supporiting an appliance for 50 years and longer. Running there appliances
unmodified for years today is not feasible anymore due to policies and corporate
standards that requrire updates in the field.

<br><br>
Trouble they are dealing with today is in the cost of software forks - both,
self inflicted and supplier caused forks. The amount of cost attached to these
is one of the reasons for Siemens to think upstream-first, both internally as
well as when choosing suppliers.

<br><br>
Another reason for this approach is to be found in trying to become part of the
community for three reasons: Keeping talent. Learning best practices from
upstream instead of failing one-self. Better communication with suppliers
through official open source channels.

<br><br>
One project Siemens is involved with at the moment is the so-called <a
href="http://cip-project.org">Civil Infrastructure Platform</a> project.

<br><br>
Another huge topic within Siemens is software license compliance. Being a huge
corporation they rely on <a href="https://www.fossology.org/">Fossology</a> for
compliance checking.

<h2>Linus Torvalds Q&A</h2>
The last keynote of the day was an on stage interview with Linus Torvalds. The
introduction to this kind of format was lovely: There's one thing Linus doesn't
like: Being on stage and giving a pre-created talk. Giving his keynote in the
form of an interview with questions not shared prior to the actual event meant
that the interviewer would have to prep the actual content. :)

<br><br>
The first question asked was fairly technical: Are RCs slowing down? The reason
that Linus gave had a lot to do with proper release management. Typically the
kernel is released on a time-based schedule, with one release every 2.5 months.
So if some feature doesn't make it into a release it can easily be integrated
into the following one. What's different with the current release is Greg Kroah
Hartman having announced it would be a long term support release, so suddenly
devs are trying to get more features into it.

<br><br>
The second question related to a lack of new maintainers joining the community.
The reasons Linus sees for this are mainly related to the fact that being a
maintainer today is still fairly painful as a job: You need experience to
quickly judge patches so the flow doesn't get overwhelming. On the other hand
you need to have shown to the community that you are around 24/7, 365 days a
year. What he wanted the audience to know is that despite occasional harsh words
he loves maintainers, the project does want more maintainers. What's important
to him isn't perfection - but having people that will stand up to their
mistakes.

<br><br>
One fix to the heavy load mentioned earlier (which was also discussed during the
kernel maintainers' panel a day earlier) revolved around the idea of having a
group of maintainers responsible for any single sub-system in order to avoid
volunteer burnout, allow for vacations to happen, share the load and ease
hand-over.

<br><br>
Asked about kernel testing Linus admitted to having been sceptical about the
subject years ago. He's a really big fan of random testing/ fuzzing in order to
find bugs in code paths that are rarely if ever tested by developers. 

<br><br>
Asked about what makes a successful project his take was the ability to find
commonalities that many potential contributors share, the ability to find
agreement, which seems easier for systems with less user visibility. An
observation that reminded my of the <a
href="http://bikeshed.com/">bikeshedding</a> discussions.

<br><br>
Also he mentioned that the problem you are trying to solve needs to be big
enough to draw a large enough crowd. When it comes to measuring success though
his insight was very valuable: Instead of focussing too much on outreach or
growth, focus on deciding whether your project solves a problem you yourself
have.

<br><br>
Asked about what makes a good software developer, Linus mentioned that the
community over time has become much less homogenuous compared to when he started
out in his white, male, geeky, beer-loving circles. The things he believes are
important for developers are caring about what they do, being able to invest in
their skills for a long enough period to develop perfection (much like athletes
train a long time to become really sucessful). Also having fun goes a long way
(though in his eyes this is no different when trying to identify a successful
marketing person).

<br><br>
While Linus isn't particularly comfortable interacting with people face-to-face,
e-mail for him is different. He does have side projects beside the kernel.
Mainly for the reason of being able to deal with small problems, actually
provide support to end-users, do bug triage. In Linux kernel land he can no
longer do this - if things bubble up to his inbox, they are bound to be of the
complex type, everything else likely was handled by maintainers already.

<br><br>
His reason for still being part of the Linux Kernel community: He likes the
people, likes the technology, loves working on stuff that is meaningful, that
people actually care about. On vacation he tends to check his mail three times a
day to not loose track and be overwhelmed when he gets back to work. There are
times when he goes offline entirely - however typically after one week he
longing to be back.

<br><br>
Asked about what further plans he has, he mentioned that for the most part he
doesn't plan ahead of time, spending most of his life reacting and being
comfortable with this state of things.

<br><br>
Speaking of plans: It was mentioned that likely Linux 5.0 is to be released some
time in summer 2018 - numbers here don't mean anything anyway.

<h2>Nobody puts Java in a container</h2>
J&ouml;rg Schad from Mesosphere gave an introduction to how container
technolgies like Docker really work and how that applies to software run in the
JVM.

<br><br>
He started off by explaining the advantages of containers: Isolating what's
running inside, supplying standard interfaces to deployed units, sort of the
write once, run anywhere promise.

<br><br>
Compared to real VMs they are more light weight, however with the caveat of
using the host kernel - meaning that crashing the kernel means crashing all
container instances running on that host as well. In turn they are faster to
spin up, need less memory and less storage.

<br><br>
So which properties do we need to look at when talking about having a JVM in a
container? Resource restrictions (CPU, memory, device visibility, blkio etc.)
are being controlled by cgroups. Process spaces for e.g. pid, net, ipc, mnt,
users and hostnames are being controlled through libcontainer namespaces.

<br><br>
Looking at cgroups there are two aspects that are very obviously interesting for
JVM deployments: For memory settings one can set hard and soft limits. However
much in contrast to the JVM there is no such thing as an OOM being thrown when
resources are exhausted. For CPUs available there are two ways to configure
limits: cpushares lets you give processes a relative priority weighting. Cpusets
lets you pin groups to specific cpus.

<br><br>
General advise is to avoid cupsets as it removes one level of freedom from
scheduling, often leads to less efficiency. However it's a good tool to avoid
cup-bouncing, and to maximise cache usage.

<br><br>
When trying to figure out the caveats of running JVMs in containers one needs to
understand what the memory requirements for JVMs are: In addition to the well
known, configurable heap memory, each JVM needs a bit of native JRE memory, perm
get/ meta space, JIT bytecode space, JNO and NIO space as well as additional
native space for threads. With permgen space turned native meta space that means
that class loader leaks are capable of maxing out the memory of the entire
machine - one good reason to lock JVMs in containers.

<br><br>
The caveats of putting JVMs into containers are related to JRE intialisation
defaults being influenced by information like the number of cores available: It
influences the number of JIT compilation threads, hotspot thresholds and limits.

<br><br>
One extreme example: When running ten JVM containers in a 32 core box this means
that:
<ul>
<li>Each JVM believes it's alone on the machine configuring itself to the
maximally availble CPU count.
<li>pre-Java-9 the JVM is not aware of cpusets, meaning it will think that it
can use all 32 cores even if configured to use less than that.
</ul>

<br><br>
Another caveat: JVMs typically need more resources on startup, leading to a need
for overprovisioning just to get it started. J&ouml;rg promised a blog post to
appear on how to deal with this question on the DC/OS blog soon after the
summit.

<br><br>
Also for memory Java9 provides the option to look at memory limits set through
cgroups. The (still experimental) option for that: -XX:+UseCGroupMemLimitForHeap

<br><br>
As a conclusion: Containers don't hide the underlying hardware - which is both,
good and bad.

<h2>Goal - question - metric approach to community measurement</h2>
In his talk on applying goals question metrics to software development
management Jose Manrique Lopez de la Fuente explained how to successfully choose
and use metrics in OSS projects.

<br><br>
He contrasted the OKR based approach to goal setting with the goal question
metric approach. In the latter one first thinks about a goal to achieve (e.g.
"We want a diverse community."), go from there to questions to help understand
the path ot that goal better ("How many people from underrepresented groups do
we have."), to actual metrics to answer that question.

<br><br>
Key to applying this approach is a cycle that integrates planning, making
changes, checking results and acting on them.

<br><br>
Goals, questions and metrics need to be in line with project goals, involve
management and involve contributors. Metrics themselves are only useful for as
long as they are linked to a certain goal.

<br><br>
What it needs to make this approach successful is a mature organisation that
understands the metrics' value, refrains from gaming the system. People will
need training on how to use the metrics, as well as transparency about metrics.

<br><br>
Projects dealing with applying more metrics and analytics to OSS projects
include Grimoire Lab, CHAOSS (Community Health Analytics for OSS).

<br><br>
There's a couple interesting books: Managing inner source projects. Evaluating
OSS projects as well as the Grimoire training which are all available freely
online. 

<h2>Container orchestration - the state of play</h2>
In his talk Michael Bright gave an overview of current container orchestration
systems. In his talk he went into some details for Docker Swarm, Kubernetes,
Apache Mesos. Technologies he left out are things like Nomad, Cattle, Fleet,
ACS, ECS, GKE, AKS, as well as managed cloud.

<br><br>
What became apparent from his talk was that the high level architecture is
fairly similar from tool to tool: Orchestration projects make sense where there
are enough microservices to be unable to treat them like pets with manual
intervention needed in case something goes wrong. Orchestrators take care of
tasks like cluster management, micro service placement, traffic routing,
monitoring, resource management, logging, secret management, rolling updates.

<br><br>
Often these systems build a cluster that apps can talk to, with masters managing
communication (coordinated through some sort of distributed configuration
management system, maybe some RAFT based consensus implementation to avoid split
brain situations) as well as workers that handle requests.

<br><br>
Going into details Michael showed the huge takeup of Kubernetes compared to
Docker Swarm and Apache Mesos, up the point where even AWS joined CNCF.


<br><br>

For Thursday I went to see Rich Bowen's keynote on the Apache Way at MesosCon.
It was great to hear how people were interested in the greater context of what
Apache provides to the Mesos project in terms of infrastructure and mentoring.
Also there were quite a few questions on what that thing called The Apache
Software Foundation actually is at their booth at MesosCon. 

<br><br>
Hopefully the initiative started on the <a
href="https://lists.apache.org/thread.html/91e65143180a0f9de465ed082752fe364320c058dbf735dd989cfcf7@%3Cdev.community.apa
che.org%3E">Apache
Community development</a> mailing list on getting more information out on how
things are managed at Apache will help spread the word even further.


<br><br>
Overall Open Source Summit, together with it's sister events like e.g. KVM
forum, MesosCon as well as co-located events like the OpenWRT summit was a great
chance to meet up with fellow open source developers and project leads, learn
about technologies and processes both familiar was well as new (in my case the
QEMU on UEFI talk clearly was above my personal comfort zone understanding
things - here it's great to be married to a spouse who can help fill the gaps
after the conference is over). There was a fairly broad spectrum of talks from
Linux kernel internals, to container orchestration, to OSS licensing, community
management, diversity topics, compliance, and economics.

