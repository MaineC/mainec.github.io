---
title: "ApacheConEU - part 10"
date: 2012-11-19T20:34:15+01:00
tags: Lucene,tika,ApacheCon,Apache Con,apacheconeu,
---

# ApacheConEU - part 10


In the next session Jukka introduced Tika - a toolkit for parsing content from files including a heuristics based 
component for guessing the file type: Based on file extension, magic and certain patterns in the file the file type can 
be guessed rather reliably. Some anecdotes:<br><ul><br><li>not all mime types are registered with IANA, there are of 
course conflicting file extensions,<br><li>Microsoft Word not only localises their interface but also the magic in the 
file,<br><li>html detection is particularly hard as there is quite some overlap with other file formats (e.g. there are 
such things as html mails...)<br><li>xhtml parsing is quite reliable by using an actual xml parser for the first few 
bytes to identify the namespace of the document<br><li>identifying odf documents is easy - though zipped the magic is 
preserved uncompressed at a pre-defined location in the file<br><li>for ooxml the file has to be unpacked to identify 
it<br><li>plain text content is hardest - there are a few heuristics based on UTF BOMs, ASCII stats, line ending stats, 
byte histograms, still it's not fool proof.<br></ul><br><br>In addition Tika can extract metadata: For text that can be 
as easy as encoding, length, content type and comments. For images that is extended by image size and potentially EXIF 
data. For pdf data it gets even more comprehensive including information on the file creator, save date and more (same 
applies for MS office documents). Most document metadata is based on the doublin core standard, for images there’s EXIF 
and IPCT - soon there’ll also be xmb related data that can be discovered.
