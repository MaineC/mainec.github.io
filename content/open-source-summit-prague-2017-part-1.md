---
title: "Open Source Summit Prague 2017 - part 1"
date: 2017-10-23T13:18:47+02:00
tags: Open Source, Linux Foundation, Conference
categories: Conference
---

# Open Source Summit Prague 2017 - part 1



Open Source Summit, formerly known as LinuxCon, this year took place in Prague.
Drawing some 2000 attendees to the lovely Czech city, the conference focussed on
all things Linux kernel, containers, community and governance.
The first day started with three crowded keynotes: First one by Neha Narkhede on
<br><br>
<h2>Keynotes</h2>
Apache Kafka and the Rise of the Streaming Platform. Second one by Reuben Paul
(11 years old) on how hacking today really is just childs play: The hack
itself might seem like toying around (getting into the protocol of children's toys
in order to make them do things without using the app that was intended to
control them). Taken into the bigger context of a world that is getting more and
more interconnected - starting with regular laptops, over mobile devices to cars
and little sensors running your home the lack of thought that goes into security
when building systems today is both startling and worrying at the same time.

<br><br>
The third keynote of the morning was given by Jono Bacon on what it takes to
incentivise communities - be it open source communities, volunteer run
organisations or corporations. According to his perspective there are four major
factors that drive human actions:

<br><br>
<ul>
<li>People thrive for acceptance. This can be exploited when building
communities: Acceptance is often displayed by some form of status. People are
more likely to do what makes them proceed in their career, gain the next level
in a leadership board, gain some form of real or artificial title.
<li>Humans are a reciprocal species. Ever heart of the phrase "a favour given -
a favour taken"? People who once received a favour from you are more likely to
help in the long run.
<li>People form habits through repetition - but it takes time to get into a
habit: You need to make sure people repeat the behaviour you want them to show
for at least two months until it becomes a habit that they themselves continue
to drive without your help. If you are trying to roll out peer review based,
pull request based working as a new model - it will take roughly two months for
people to adapt this as a habit.
<li>Humans have a fairly good bullshit radar. Try to remain authentic, instead
of automated thank yous, extend authentic (I would add qualified) thank you
messages.
</ul>

<br><br>
When it comes to the process of incentivising people Jono proposed a three step
model: From hook to reason to reward.

<br><br>
Hook here means a trigger. What triggers the incentivising process? You can look
at how people participate - number of pull requests, amount of documentation
contributed, time spent giving talks at conferences. Those are all action based
triggers. What's often more valuable is to look out for validation based
triggers: Pull requests submitted, reviewed and merged. He showed an example of
a public hacker leaderboard that had their evaluation system published. While
that's lovely in terms of transparency IMHO it has two drawbacks: It makes it
much easier to evaluate known wanted contributions than what people might not
have thought about being a valuable contribution when setting up the leadership
board. With that it also heavily influences which contribtions will come in and
might invite a "hack the leadership board" kind of behaviour.

<br><br>
When thinking about reason there are two types of incentives: The reason could
be invisible up-front, Jono called this submarine rewards. Without clear prior
warning people get their reward for something that was wanted. The reason could
be stated up front: "If you do that, then you'll get reward x". Which type to
choose heavily depends on your organisation, the individual giving out the
reward as well as the individual receiving the reward. The deciding factor often
is to be found in which is more likely authentic to your organisation.

<br><br>
In terms of reward itself: There are extrinsic motivators - swag like stickers,
t-shirts, give-aways. Those tend to be expensive, in particular if shipping them
is needed. Something that in professional open source projects is often
overlooked are intrinsic rewards: A Thank You goes a long way. So does a blog
post. Or some social media mention. Invitations help. So do referrals to ones
own network. Direct lines to key people help. Testimonials help.

<br><br>
Overall measurement is key. So is concentrating on focusing on incentivising
shared value.
<h2>Limux - the loss of a lighthouse</h2>

<br><br>
In his talk, Matthias Kirschner gave an overview of Limux - the Linux rolled out
for the Munich administration project. How it started, what went wrong during
evaluation, which way political forces were drawing.

<br><br>
What I found very interesting about the talk were the questions that Matthias
raised at the very end:

<br><br>
<ul>
<li>Do we suck at desktop? Are there too many depending apps?
<li>Did we focus too much on the cost aspect?
<li>Is the community supportive enough to people trying to monetise open source?
<li>Do we harm migrations by volunteering - as in single people supporting a
project without a budget, burning out in the process instead of setting up
sustainable projects with a real budget? Instead of teaching the pros and cons
of going for free software so people are in a good position to argue for a
sustainable project budget?
<li>Within administrations: Did we focus too much on the operating system
instead of freeing the apps people are using on a day to day basis?
<li>Did we focus too much on one star project instead of collecting and
publicising many different free software based approaches?
</ul>

<br><br>
As a lesson from these events, the FSFE launched <a
href="http://publiccode.eu">an initiative to drive developing code funded by
public money under free licenses</a>.
<h2>Dude, Where's My Microservice</h2>
In his talk Dude, Where's My Microservice? - Tomasz Janiszewski from Allegro
gave an introduction to what projects like Marathon on Apache Mesos, Docker Swarm,
Kubernetes or Nomad can do for your Microservices architecture. While the
examples given in the talk refer to specific technologies, they are intented to
be general purpose.

<br><br>
Coming from a virtual machine based world where apps are tied to virtual
machines who themselves are tied to physical machines, what projects like Apache
Mesos try to do is to abstract that exact machine mapping away. Is a first
result from this decision, how to communicate between micro services becomes a
lot less obvious. This is where service discovery enters the stage.

<br><br>
When running in a microservice environment one goal when assigning tasks to
services is to avoid unhealthy targets. In terms of resource utilization instead
of overprovisioning the goal is to use just the right amount of your resources
in order to avoid wasting money on idle resources. Individual service overload
is to be avoided.

<br><br>
Looking at an example of three physical hosts running three services in a
redundant matter, how can assigning tasks to these instances be achieved?

<br><br>
<ul>
<li>One very simple solution is to go for a proxy based architecture. There will
be a single point of change, there aren't any in-app dependencies to make this
model work. You can implement fine-grained load balancing in your proxy. However
this comes at the cost of having a single point of failure, one additional hop
in the middle, and usually requires using a common protocol that the proxy
understands.
<li>Another approach would be to go for a DNS based architecture: Have one
registry that holds information on where services are located, but talking to
these happens directly instead of through a proxy. The advantages here: No
additional hop once the name is resolved, no single point of failure - services
can work with stale data, it's protocol independent. However it does come with
in-app dependencies. Load balancing has to happen local to the app. You will
want to cache name resolution results, but every cache needs some cache
invalidation strategy.
</ul>

<br><br>
In both solutions you will also still have logic e.g. for de-registrating
services. You will have to make sure to register your service only once is
successfully booted up. 

<br><br>
Enter the Service Mesh architecture, e.g. based on <a
href="https://linkerd.io/">Linker.d</a>, or <a
href="https://www.envoyproxy.io/">Envoy</a>. The idea here is to have what Tomek
called a sidecar added to each service that talks to the service mesh controller to take
care of service discovery, health checking, routing, load balancing, authn/z,
metrics and tracing. The service mesh controller will hold information on which
services are available, available load balancing algorithms and heuristics,
repeating, timeouts and circuit breaking, as well as deployments. As a result
the service itself no longer has to take care of load balancing, ciruict
breaking, repeating policies, or even tracing. 

<br><br>
After that high level overview of where microservice orchestration can take you,
I took a break, following a good friend to the Introduction to SoC+FPGA talk.
It's great to see Linux support for these systems - even if not quite as stable
as would be an ideal world case.

<br><br>
<h2>Trolling != Enforcement</h2>
The afternoon for me started with a very valuable talk by Shane Coughlan on how
Trolling doesn't equal enforcement. This talk was related to what was published
on LWN <a href="https://lwn.net/Articles/721458/">earlier this year</a>.

Shane started off by explaining some of the history of open source licensing,
from times when it was unclear if documents like the GPL would hold in front of
courts, how projects like gplviolations.org proofed that indeed those are valid
legal contracts that can be enforced in court.

What he made clear was that those licenses are the basis for equal
collaboration: They are a common set of rules that parties not knowing each
other agree to adhere to. As a result following the rules set forth in those
licenses does create trust in the wider community and thus leads to more
collaboration overall.

On the flipside breaking the rules does erode this very trust. It leads to less
trust in those companies breaking the rules. It also leads to less trust in open
source if projects don't follow the rules as expected.

However when it comes to copyright enforcement, the case of Patrick McHardy does
imply the question if all copyright enforcement is good for the wider community.
In order to understand that question we need to look at the method that Patrick
McHardy employs: He will get in touch with companies for seemingly minor
copyright infringements, ask for a cease and desist to be signed and get a small
sum of money out of his target. In a second step the process above repeats,
except the sum extracted increases.

Unfortunately with this approach what was shown is that there is a viable
business model that hasn't been tapped into yet. So while the activities by
Patrick McHardy probably aren't so bad in and off itself, they do set a
precedent that others might follow causing way more harm.

Clearly there is no easy way out. Suggestions include establishing common norms
for enforcement, ensuring that hostile actors are clearly unwelcome. For
companies steps that can be taken include understanding the basics of legal
requirements, understanding community norms, and having processes and tooling to
address both. As one step there is a project called <a
href="http://www.openchainproject.org">Open Chain</a> publishing material on the
topic of open source copyright, compliance and compliance self certification.
<br><br>
<h2>Kernel live patching</h2>
Following Tomas Tomecek's talk on how to get from <a
href="https://schd.ws/hosted_files/osseu17/3d/From%20Dockerfiles%20to%20Ansible%20Container.pdf">
Dockerfiles to Ansible Containers</a> I went to a talk that was given by Miroslav Benes from SuSE on Linux
kernel live patching.

<br><br>

The topic is interesting for a number of reasons: As early as back in 2008 MIT
developed something called Ksplice which uses jumps patched into functions for
call redirection. The project was aquired by Oracle - and discontinued.

<br><br>
In 2014 SuSE came up with something called kGraft for Linux live patching based
on immediate patching but lazy migration. At the same time RedHat developed
kpatch based on an activeness check.

<br><br>
In the case of kGraft the goal was to be able to apply limited scope fixes to the Linux
kernel (e.g. for security, stability or corruption fixes), require only minimal
changes to the source code, have no runtime cost impact, no interruption to
applications while patching, and allow for full review of patch source code.
<br><br>

The way it is implemented is fairly obvious - in hindsight: It's based on
re-useing the ftrace framework. kGraft uses the tracer for inception but then
asks ftrace to return back to a different address, namely the start of the
patched function. So far the feature is available for x86 only.

<br><br>
Now while patching a single function is easy, making changes that affect
multiple funtions get trickier. This means a need for lazy migration that
ensures function type safety based on a consistency model. In kGraft this is
based on a per-thread flag that marks all tasks in the beginning and makes
waiting for them to be migrated possible.

<br><br>
From 2014 onwards it took a year to get the ideas merged into mainline. What is
available there is a mixture of both kGraft and kpatch.
<br><br>

What are the limitations of the merged approach? There is no way right now to
deal with data structure changes, in particular when thinking about spinlocks
and mutexes. Consistency reasoning right now is done manually. Architectures
other than X86 are still an open issue. Documentation and better testing are
open tasks.  





