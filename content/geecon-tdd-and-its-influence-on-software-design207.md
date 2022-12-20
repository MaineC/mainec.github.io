---
title: "GeeCon - TDD and it's influence on software design"
date: 2012-05-22T08:04:00+02:00
tags: [Science,Hacking,testing,Free Software,geecon,]
---

# GeeCon - TDD and it's influence on software design


The second talk I went to on the first day was on the influence of TDD on software design. Keith Braithwaite did a 
really great job of first introducing the concept of cyclomatic complexity and than showing at the example of Hudson as 
well as many other open source Java projects that the average and mean cyclomatic complexity of all those projects 
actually is pretty close to one and when plotted for all methods pretty much follows a power law distribution. 
Comparing the properties of their specific distribution of cyclomatic complexities over projects he found out that the 
less steep the curve is, that is the more balance the distribution is, that is the less really complex pieces there are 
in the code the more likely are developers happy with the current state of the code. Not only that, also that 
distribution would be transformed into something more balanced after refactorings.<br><br>Now looking at a selection of 
open source projects he analyzed what the alpha of the distribution of cyclomatic complexity is for projects that have 
no tests at all, have tests and those that were developed according to TDD. Turns out that the latter ones were the 
ones with the most balanced alpha.<br>
