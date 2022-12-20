---
title: "AMQP Erlang user group talk"
date: 2009-07-10T15:56:38+02:00
tags: [Messaging,Hacking,Erlang,Free Software,General,]
---

# AMQP Erlang user group talk


Last Wednesday at the Erlang user group Berlin Matthias Radestock from the <a 
href="http://www.rabbitmq.com/">RabbitMQ</a> project gave a talk on RabbitMQ, AMQP and messaging in general. Slides are 
available <a 
href="http://www.rabbitmq.com/resources/google-tech-talk-final/alexis-google-rabbitmq-talk.pdf">online</a>.<br><br>First
 Matthias motivated the need for an open standard for messaging: So far, their are a few provides of middleware systems 
like Tibco and IBM. But those solutions are usually closed, expensive, cumbersome to handle. In short they do not fit 
into a world where people rely on open standards for communication, free software for development and lightweight 
implementations.<br><br>AMQP aims to povide an open standard for messaging - that is decoupled communication between 
processes that may reside on separate boxes or in different datacenters. There are a few providers of AMQP 
implementations. Some examples are iMatix focussed on low latency communication, Apache Qpid and the corresponding 
project inside of RedHat and RabbitMQ.<br><br>RabbitMQ is implemented in Erlang (after all, the talk was hosted by the 
Erlang User Group Berlin ;) ). With about 7000 lines of code the code base is rather compact. The goal was not to built 
a super-fast implementation, but one that is scalable and highly available.<br><br>So far there is no facility for 
building reliable cross datacenter communication built into RabbitMQ. Yet, there are several projects available that 
aim at providing just that.
