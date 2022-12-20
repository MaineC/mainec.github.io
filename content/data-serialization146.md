---
title: "Data serialization"
date: 2009-06-26T08:39:47+02:00
tags: Avro,Data Serialization,General,Protocol Buffers,Etch,Get Together,Thrift,
---

# Data serialization


XML, JSON and others are currently standard data exchange formats. Being human-readable but still structured enough to 
be easily parsable by programs is their main benefit. Problems are overhead in size and parsing time. In addition at 
least xml is not really as human-readable as it could be.<br><br>An alternative are binary formats. Yet those often are 
not platform independent (either C++ or Java or Python bindings) or are not upgradable (what if your boss comes along 
and wants you to add yet another field? Do you need to process all your data again?).<br><br>There are a few libraries 
that promise to solve at least some of these problems. Usually you specify your data format with an IDL, generate 
(Byte-)code from it and use mechanisms provided by the libraries to upgrade your format.<br><br>Yesterday at the Berlin 
Apache Hadoop Get Together Torsten Curdt gave a short introduction to two of these solutions: Thrift and Protocol 
buffers. He explained why Joost decided to use one of those libraries and highlighted why they went with Thrift instead 
of Protocol Buffers.<br><br>This morning I have gathered a list of data exchange libs that are currently 
available:<br><ul><br><li><a href="http://incubator.apache.org/thrift/">Thrift</a> ... developed at Facebook, now in 
the Apache incubator, active community, Bindings for C++, Java, Python, PHP, Ruby, Erlang, Perl, Haskell, C#, Cocoa, 
Smalltalk, and OCaml.<br><li><a href="http://code.google.com/p/protobuf">ProtoBuf</a> ... developed at Google, mainly 
one developer only, bindings for C++, Java und Python.<br><li><a href="http://wiki.apache.org/hadoop/Avro">Avro</a> ... 
started by Doug Cutting, skips code generation.<br><li><a href="http://cwiki.apache.org/ETCH/index.html">ETCH</a> ... 
developed at Cisco, now in the Apache Incubator, Bindings for Java, C#, JavaScript.<br></ul><br>There are <a 
href="http://blog.oskarsson.nu/2009/04/avro-serialization-follow-up.html">some</a> <a 
href="http://code.google.com/p/thrift-protobuf-compare/">performance</a> <a 
href="http://mail-archives.apache.org/mod_mbox/hadoop-avro-dev/200905.mbox/%3C2C52DBBEC4855C438BB330CB0D3B46590131C93D@S
NV-EXVS01.ds.corp.yahoo.com%3E">benchmarks</a> online. Another <a 
href="http://code.google.com/p/thrift-protobuf-compare/wiki/Benchmarking">recent, extensive</a> comparison of 
serialization performance of various frameworks.
