---
author: wolpert
comments: true
date: 2010-04-23 21:51:46+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/04/23/gridgaincassandragrails/
slug: gridgaincassandragrails
title: GridGain and Grails
wordpress_id: 230
---

We've been able to get gridgain and grails running together at work recently. Its works out well, though some of the issues we ran into seem weird.  First, putting closures in gridstasks/jobs works, but using dynamically generated closures, or closures created on the fly without class files on disk being saved ran into problems; so everything had to be compiled before submitting the job. This in itself was not unexpected.

We ran into trouble when we needed to be able to reload tasks and jobs that are submitted by our grails server  without redeploying the grails app in production. This meant we had to create a second project that contained those tasks and jobs. We could use the ﻿﻿GridUriDeploymentSpi to point to a 'gar' directory. However, we were passing in objects to the grid.execute() method that only existed in the grails app and not in the gar. If you ran 'grails run-app' those classes would not be found. But 'grails run-war' they would be. Still not sure what is different in the grails classloader that caused that but at least it works out well enough for development.

I like the idea of 'UserResource' in gridgain, where you can define an injected resource to the tasks and jobs in the grid. But I do not like that you have to define on each grid node how to configure that injected resource and put those classes in a directory on each gridnodes. I'd rather be able to configure them in one place and distribute them as resources to each gridnode automatically, or based on their segment.
