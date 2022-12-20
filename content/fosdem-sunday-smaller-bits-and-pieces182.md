---
title: "FOSDEM - Sunday - smaller bits and pieces"
date: 2011-02-18T20:17:57+01:00
tags: Brussels,Fosdem,General,
---

# FOSDEM - Sunday - smaller bits and pieces


<p>With WebODF the Office track featured a very interesting project that focusses on providing a means to open ODF 
documents in your favourite browser: Content and formatting are converted to a form that can easily be dealt with by 
using a combination of HTML and CSS. Advanced editing is then supported by using JavaScript.</p><p>With Open Stack the 
following talk focussed on an open cloud stack project that was started by NASA and Rackspace as both simultanously 
needed support for an open source, openly designed, developed cloud stack that strives for community inclusion. 
According to the speaker the goal is to be as ubiquitous a cloud project as Apache is for web servers - he probably was 
not quite aware of how close to even the foundation side of Apache that development model is.</p><p>The closing keynote 
dealt with the way kernel development takes place. There were a few very interesting pieces of information for 
contributors that are valid for any open source project really:</p><ul><li>Out of tree code is invisible to the kernel 
developers and users. As such the longer it remains out of tree code the harder it becomes to actually go out there and 
feel the wind.</li><li>In contrast open code means giving up control: Maintainership means responsibility but it does 
not come with any power or control over the source code. Similarly opening code up as patch or separate project at 
Apache means giving up control - means working towards turning the project into a community that can live on its 
own.</li><li>For kernel patches the general rule is to not break things and not go backward in quality: What is working 
for users today must be working with the next release as well. To be able to spot any compat issues it is necessary to 
take part on the wider disucssion lists - not only in your limited development community. Developers should focus on 
coming up with a problem solution instead of getting their original code into the project.</li></ul><p>Or in short: The 
kernel is no research project, as such it must not break existing applications. Visionary brilliance really is no 
excuse for poor implementation. Conspiracy theories such as &quot;hey, developer x declined my patch only because it is 
out of scope for his employer's goals&quot; are not going to get you anywhere. Such things do happen, but in general 
kernel developers first think of themselves as kernel developers - being employee somewhere only comes after 
that.</p><p>Keep in mind that the community remembers past actions. In the end you need not convince business people or 
users but the developers themselves who might end up with the maintanance burden for your patch. To get your patch 
accepted it greatly helps to not express it in terms of the implementation needs only but to clearly formulate your 
requirements - independent of implementation. And as in any open source project, helping with cleanup (that is not only 
white space fixes, but real cleanup as in refactoring) does help build a positive attitude.</p><p>Why you should go for 
kernel development never the less? It's a whole lot of fun. It's a way to influence the kernel to support the features 
that you need. It's sort of like becoming part of an elite club - and which developer does not like the feeling of 
belonging to the elite changing the way the world looks tomorrow? In addition as with an substantial open source 
involvement being visible in the kernel community also most likely means being visible to your future 
employer.</p><p></p>
