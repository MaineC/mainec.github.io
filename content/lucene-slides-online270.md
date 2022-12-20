---
title: "Lucene slides online"
date: 2009-06-30T10:04:47+02:00
tags: [Lucene,Get Together,General,]
---

# Lucene slides online


The slides of the Lucene talk at the last Apache Hadoop Get Together Berlin are available online: <a 
href="http://isabel-drost.de/hadoop/slides/Hadoop-meeting-2009-06-25.pdf">Lucene Slides</a>. Especially interesting to 
me are the last few slides which detail both index size and machine setup:<br><br>The installation is running on two 
standard PCs with 2 dual-core processors (usual speed, bought in January 2008 for about 4000 Euro). They have 32GB RAM, 
24 GB are used as ramdisk for the index. Without ramdisk initial queries especially those accessing fields are slower 
but still acceptable. The index contains about 19 million documents, that is 80GB of indexed text + billions of 
annotated tags.<br>
