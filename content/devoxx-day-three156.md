---
title: "Devoxx – Day three "
date: 2010-12-10T21:28:26+01:00
tags: [lombok,Java,Devoxx,General,]
---

# Devoxx – Day three 


The panel discussion on the future of Java was driven by visitor submitted and voted questions on the current state and 
future of Java. The general take-aways for me included the clear statement that the TCK will never be made available to 
the ASF. The promise of Oracle to continue supporting the Java community and remaining active in the JCP.<br><br>There 
was some discussion on whether coming Java versions should be backwards-incompatible. One advantage would be the 
removal of several Java puzzlers thus making it easier for Joe Java to write code in Java without knowing too much 
about potential inconsistencies. According to Joshua Bloch the language is no longer well suited to the average 
programmer who just simply wants to get his tasks done in a consistent and easy to use language: It has become too 
complicated over the course of the years and is in bitter need for simplification.<br><br>Having seen his presentation 
in Berlin at Buzzwords and silently following the project's progress online I skipped parts of the elastic search 
presentation. Instead went to the presentation on the Ghost-^wBoilerplate Busters from project Lombok. It always stroke 
me as odd that in a typical Java project there is so much code that can be generated automatically by Eclipse – such as 
getters/setters, equals/hashcode, delecation of methods and more. I never really understood why it is possible to 
generate all that code from Eclipse but not during compile time. Project Lombok however comes to the rescue here. As a 
compile time dependency it provides several annotations that are automatically converted to the correct code on the 
fly. It includes support for getter/setter generation, handling of closable resources (even with the current stable 
version of java), generation of thread safe lazy initialisation of member variables, automatic implementation of the 
composition over inheritance pattern and much more.<br><br>The library can be used from within Eclipse, in maven, ant, 
ivy, on Google App Engine. One of the developers in charge for IntelliJ who was in the audience announced that the 
library will be supported by the next version of IntelliJ as well.<br>
