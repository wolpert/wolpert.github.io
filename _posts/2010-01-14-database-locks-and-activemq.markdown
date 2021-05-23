---
author: wolpert
comments: true
date: 2010-01-14 21:53:52+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/01/14/database-locks-and-activemq/
slug: database-locks-and-activemq
title: Database locks and ActiveMQ
wordpress_id: 179
categories:
- Code
---

If you are using a database with your ActiveMQ installation, you may want to set useDatabaseLock to "false" in the journaledJDBC element of your configuration. This is there so that you can have a master/slave configuration and the instance that can lock a specific table gets to be the master. If you only have one server, this doesn't do you any good. Also, databases like PostgreSQL which use vacuum can have issues with these long-running transactions.
