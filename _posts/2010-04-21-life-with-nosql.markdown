---
author: wolpert
comments: true
date: 2010-04-21 15:32:17+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/04/21/life-with-nosql/
slug: life-with-nosql
title: Life with 'NoSQL'...
wordpress_id: 227
categories:
- Business
- Code
---

I  have to say that after playing with Cassandra, a NoSQL datastore, I'm completely impressed with what it gives. Fast read and writes, scale unlike I've ever seen, and (fairly) easy to manage. Its not without compromises; transaction management, two-phased commits, atomicity, etc. But I'm having to view the datastores in a whole new light. Here is a list of interesting links of talks and presentations:



	
  * ﻿﻿[http://www.slideshare.net/jbellis/cassandra-nosql-eu-2010](http://www.slideshare.net/jbellis/cassandra-nosql-eu-2010)

	
  * [http://www.slideshare.net/matwall/nosql-presentation](http://www.slideshare.net/matwall/nosql-presentation)

	
  * [http://www.youtube.com/v/2ElGO1P8v0c&hl=en_US&fs=1&](http://www.youtube.com/v/2ElGO1P8v0c&hl=en_US&fs=1&)

	
  * [http://blog.oskarsson.nu/2009/06/nosql-debrief.html](http://blog.oskarsson.nu/2009/06/nosql-debrief.html)


The last one contains a bunch of links to videos with various NoSQL solutions. I highly recommend to go though them.

At this point, I can see these NoSQL datastores to be used along-side SQL ones. There is no question that many websites can only use NoSQL datastores, but it gets tricky when dealing with things that SQL databases solve well, such as financial transaction management. Considering that many large banks still use datastores like IDMS, that could eventually change.
