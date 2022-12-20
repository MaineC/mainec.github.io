---
title: "GeeCon - Testing hell and how to fix it"
date: 2012-05-26T08:08:20+02:00
tags: [jira,geecon,Hacking,testing,atlassian,]
---

# GeeCon - Testing hell and how to fix it


The last regular talk I went to was on testing hell at Atlassian – in particular the JIRA project. What happened to 
JIRA might actually be known to developers who have to deal with huge legacy projects that predate the junit and 
dependency injection era: Over time their test base grew into a monster that was hard to maintain and didn't help at 
all with making developers confident on checkin time that they would not break anything.<br><br>On top of 13k unit 
tests they head accumulated 4k functional tests, several hundreds of selenium user interface tests in 65 maven modules 
depending on 554 dependencies that represented quite some technology mix from old to new, ranging across different 
libraries for solving the same task. They used 60+ remote agents for testing, including AWS instances that were 
orchestrated by a Bamboo installation, had different plants for every supported version branch, tested in 
parallel.<br><br>Most expensive were platform tests that were executed every two to four weeks before each release – 
those tested JIRA with differing CPU configurations, JVMs, Browsers, databases, deployment containers. Other builds 
were triggered on commit, by dependencies or nightly.<br><br>Problem was that builds would take for 15 min for unit 
tests, one hour for functional tests, several hours for all the rest – that means developers get feedback only after 
they are home essentially blocking other developers' work. For unit tests that resulted in fix turnaround times of 
several hours, for integration tests several days. Development would slow down, developers became afraid of commits, it 
became difficult to release – in summary morale went down.<br><br>Their problems: Even tiny changes caused test 
avalanches. As tests were usually red, noone would really care. Developers would not run tests for effort reasons and 
got feedback only after leaving work.<br>Some obvious mistakes: <br><br>Tests were separate from the code they tested – 
in their case in a separate maven module. So on every commit the whole suite has to run. Also back when the code was 
developed dependency injection only just started to catch up which meant the code was entangled, closely coupled and 
hard to test in isolation. There were opaque fixtures hard coded in xml configuration files that captured application 
scope but had to be maintained in the tests.<br><br>Their strategy to better testing:<br><ul><br><li>Introduce less 
fragile UI tests based on the page objects pattern to depend less on the actual layout and more on the functionality 
behind.<br><li>They put test fixtures into the test code by introducing REST APIs for modification and an introduction 
of backdoors, only open in the test environment.<br><li>Flickering tests were put to quarantine and either fixed 
quickly or deleted – if noone fixes them, they are probably useless anyway.<br></ul><br><br>After those simple measures 
they started splitting the software into multiple real modules to limit scope of development and raise responsibility 
of development teams. That comes with the advantage of having tests close to the real code. But it comes with the cost 
of a more complex CI hierarchy. However in well organised software in such a project hierarchy commits turned out to 
tend to go into leaves only – which did lessen the number of builds quite a bit.<br><br>There is  a tradeoff between 
speed vs. control: Modularizing means you no longer have all in one workspace, in turn it means faster development for 
most of your tasks. For large refactorings noone will stop you to put all code in one idea workspace.<br><br>The goal 
for Atlassian was to turn the pyramid of tests upside down: Have most but fast unit tests, have less REST/html tests 
and even less Selenium tests. Philosophy was to only provide REST tests if there is no way at all to cover the same 
function in a unit test.<br><br>In terms of speeding up execution they started batching tests against one instance to 
avoid installation time, merged tests, used in-process databases, mocked IO and webservers where possible. Also putting 
more hardware in does help, so does avoiding sleeping in tests.<br><br>In terms of splitting code – in addition to 
responsibility that can also be done by maturity to keep what is evolving quickly close together until it is 
stable.<br><br>The day finished with a really inspiring keynote by Kevlin Henney on Cool Code – showing several both 
either miserably failing or incredibly cool pieces of software. His intention when reading code is to extend a coders 
vocabulary when it comes to programming. That's why even the obfuscated c code competition does make for an interesting 
read as it tells you things about language features you otherwise might never have learned about before. One very 
important conclusion from his talk: “If you don't have the time to read, you have neither time nor tools to write.” - 
though being made by Stephen King on literature this statement might as well apply to software, after all to some 
extend what we produce is some kind of art, is some kind of literature in it's own right.<br>
