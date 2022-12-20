---
title: "On making Libre Office suck less – a major refactoring effort - FOSDEM 08"
date: 2013-02-19T20:47:10+01:00
tags: libre office,Fosdem,Event,
---

# On making Libre Office suck less – a major refactoring effort - FOSDEM 08


Libre Office is currently in a phase of code cleanup and refactoring that turns the whole code base upside down. What 
that means is that people need tooling to avoid quality from going down and allow for new features going in without too 
much risk. The project made good experiences with using gerrit for code review of patches, tinderbox for fast 
integration testing, strict whitespace checks to avoid unintended mistakes, use clang compiler plugins. They have less 
process that allows for change anywhere in any part of the code base.<br><br>There is an easy hacks page for people to 
get started quickly. I know that kind of thing from the Hadoop issue tracker and really appreciate having this to get 
new developers comfortable with the code base and all the tooling around. They apply reply-header mangling to allow for 
responses to go back to posters on their mailing list w/o prior subscription. They moved from their own dmake that 
wasn't industry standard to standard make tooling to build the project. They are in the process of translating all the 
German comments – shout-out to all German speaking readers of this blog: Help the Libre Office developers understand 
the code better by providing your German speaking skills for translation.<br><br>Some anecdotes: They found 4+ String 
classes in the code base and managed to get rid of one of them only recently. They are busy killing dead code, kicking 
out string macros, fixing cpplint warnings, refactoring code that was writing pre-STL into clean STL code, getting rid 
of obsolete libraries, fixing the windows installer, killing proprietary translation services and replacing that with 
an open one, getting rid of cargo-cult componentisation, getting rid of code duplication e.g. in the import filter 
implementation. They are reducing structure sizes for calc, switching to a layout based frontend, optimising the red 
lining for writer. The goal is to really have no no-go areas.<br><br>In order to retain quality in this fluid setup 
they opted for a drastic increase in unit- and integration test coverage, using bug documents as source for tests. 
Though the Bugzilla assistant they made it way easier even for non-experts and end-users to submit bug 
reports.<br><br>They are going for time-based, 6-monthly releases. Due to a long build time they are keeping track of 
all past binary builds for bi-section purposes – currently in git which most likely isn't the most ideal 
choice.<br><br>What works is putting graphs of bugs created vs. fixed over time in front of developers to keep the 
number of bugs low.<br><br>Within version 4.0 Libre Office is shipping:<br><ul><br><li>better interop features for word 
documents with comments<br><li>RTF drawing imports<br><li>RTF improved formulae import<br><li>Docx annotation 
support<br><li>CMIS support for better interaction with Sharepoint, Alfresco and Nuxeo<br><li>More import filters e.g. 
for Microsoft publisher<br><li>Visio is now completely supported<br><li>Support for arbitrary XML to spreadsheet 
mappings<br><li>Conditional formulae<br><li>Stock option pricing support<br><li>Android remote control support for 
slides<br><li>Libre Logo integration for schools<br><li>Image rendering, smoothing, re-sizing and scaling was 
improved<br><li>Better support for right-to-left writing arabic languages<br><li>Style previews for fonts<br><li>Better 
unity integration<br></ul><br><br>There even is an Android port in the works!
