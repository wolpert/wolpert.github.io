---
author: wolpert
comments: true
date: 2010-03-12 19:41:38+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/03/12/grails-and-cassandra/
slug: grails-and-cassandra
title: Grails and Cassandra
wordpress_id: 203
---

We are going to start using Cassandra at work, and in the process, needed to develop a grails plugin. Nothing was available and we wanted to make something generic; so we could use it in multiple projects. So I have started to write one, and made my [cassandra plugin available at github](http://github.com/wolpert/grails-cassandra). Its not ready for prime-time, but its a start. The goals is to make an easy-to-use method to access a Cassandra installation. I'm wrapping [Hector](http://github.com/rantav/hector) so I have access to his pooling of servers and simplification that he started. I'll be giving the service more options going forward, such as returning empty hash sets rather then throwing 'NotFound' exceptions on queries that turn up empty. (Behaving like the [ruby Cassandra gem)](http://blog.evanweaver.com/articles/2009/07/06/up-and-running-with-cassandra/)
