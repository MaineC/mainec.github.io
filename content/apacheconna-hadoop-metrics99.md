---
title: "ApacheConNA: Hadoop metrics"
date: 2013-05-14T20:25:25+02:00
tags: sizing,ApacheConNA,ApacheCon,Apache Con,Hadoop,
---

# ApacheConNA: Hadoop metrics


<P><br>Have you ever measured the general behaviour of your Hadoop jobs? Have you<br>sized your cluster accordingly? Do 
you know whether your work load really is IO<br>bound or CPU bound? Legend has it noone expecpt Allen Wittenauer over 
at<br>Linked.In, formerly Y! ever did this analysis for his clusters.<br><br><P><br>Steve Watt gave a pitch for 
actually going out into your datacenter measuring<br>what is going on there and adjusting the deployment accordingly: 
In small<br>clusters it may make sense to rely on raided disks instead of additional<br>storage nodes to guarantee 
``replication levels''. When going out to vendors to<br>buy hardware don't rely on paper calculations only: Standard 
servers in Hadoop<br>clusters are 1 or 2u. This is quite unlike beefy boxes being sold otherwise.<br><br><P><br>Figure 
out what reference architecture is being used by partners, run your<br>standard workloads, adjust the configuration. If 
you want to run the 10TB<br>Terrasort to benchmark your hardware and system configuration. Make sure to<br>capture data 
during all your runs - have Ganglia or SAR, watch out for<br>intersting behaviour in io rates, cpu utilisation, network 
traffic. The goal is<br>to get the cpu busy, not wait for network or disk.<br><br><P><br>After the instrumentation and 
trial run look for over- and underprovisionings,<br>adjust, leather, rinse, repeat.<br><br><P><br>Also make sure to 
talk to the datacenter people: There are floor space, power<br>and cooling constraints to keep in mind. Don't let the 
whole datacenter go down<br>because your cpu intensive job is drawing more power than the DC was designed<br>for. Ther 
are also power constraints per floor tile due to cooling issues -<br>those should dictate the 
design.<br><br><P><br>Take a close look at the disks you deploy: SATA vs. SAS can make a 40%<br>performance difference 
at a 20% cost difference. Also the number of cores per<br>machines dictates the number of disks to spread the 
likelyhood of random read<br>access. As a rule of thumb - in a 2U machine today there should be at least<br>twelve 
large form factor disks.<br><br><P><br>When it comes to controllers he goal should be to get a dedicated lane to 
disc,<br>safe one controller if price is an issue. Trade off compute power against 
power<br>consumption.<br><br><P><br>Designing your network keep in mind that one switch going down means that 
one<br>rack will be gone. This may be a non-issue in a Y! size cluster, in your<br>smaller scale world it might be 
worth the money investing in a second switch<br>though: Having 20 nodes go black isn't a lot of fun if you cannot farm 
out the<br>work and re-replication to other nodes and racks. Also make sure to have enough<br>ports in rack switches 
for the machines you are planning to provision.<br><br><P><br>Avoid playing the ops whake-a-mole game by having one 
large cluster in the<br>organisation than many different ones where possible. Multi-tenancy in Hadoop is<br>still 
pre-mature though.<br><br><P><br>If you want to play with future deployments - watch out for HP currently<br>packing 
270 servers where today are just two via system on a chip designs.<br><br><P><br>
