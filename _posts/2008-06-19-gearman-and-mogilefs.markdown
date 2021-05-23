---
author: wolpert
comments: true
date: 2008-06-19 15:48:32+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/06/19/gearman-and-mogilefs/
slug: gearman-and-mogilefs
title: Gearman and MogileFS?
wordpress_id: 11
categories:
- Code
---

I've been looking at how places like Digg scale up their systems lately...

[Gearman](http://danga.com/gearman/) is a queueing system used by Digg. Unlike JMS or other systems, it has the ability for clients to create a tasklist of parallel tasks. That means that the client defines three things to do, the server finds 3 workers to do the things in parallel, and the results are returned to the client. (Synchronized) Things can be asynch messages too. Its a bit more featureful the JMS or Stompserver, and both of those are totally async processes. Gearman can be both. Having the task list is just a nice way to combine multiple requests. There is a ruby layer and Java layer to get inside it.

The new one on me was [MogileFS](http://danga.com/mogilefs/). That provides a fail-over file caching service that uses many hosts. Forget raid systems, files are copied to multiple hosts and references gain from there. You can do rsync stuff instead, but that (usually) has a parent node for the file system, and the rest are slaves. This is 'headless'.

Memcached is nothing new anymore. There is a claim that everyone uses it, including Java places. I'm not sure I buy that since jTreeCache is native to Java so the translation layer is smaller, but whatever.
