---
author: wolpert
comments: true
date: 2010-06-15 23:05:58+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/06/15/gridgain-grails-gorm-and-cassandra/
slug: gridgain-grails-gorm-and-cassandra
title: Gridgain, Grails, GORM and Cassandra
wordpress_id: 257
---

I have grails working to submit jobs to gridgain nodes. The grid tasks execute and send out jobs that run on the grid nodes just fine. The grid jobs are able to make use of a cassandra service (provided by the cassandra plugin I wrote) just fine, thanks to Hector reconnecting blindly on the grid job. Interesting tidbit is that GridTasks (which execute on the node that submits the task) are able to make use of standard GORM methods like list(). But GridJobs cannot make use of these methods. Odds are this is due to how the method list() is added to the GORM object... the method simply isn't added on the grid node when it loads up the class.

I should also note that this is using the GAR deployment.
