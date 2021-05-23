---
author: wolpert
comments: true
date: 2015-09-27 17:40:50+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2015/09/27/cassandra-summit-conference-sessions/
slug: cassandra-summit-conference-sessions
title: 'Cassandra Summit: Conference Sessions'
wordpress_id: 443
categories:
- Code
tags:
- Cassandra
---

The Cassandra summit that DataStax hosted this year had just shy of 140 sessions over two days. Each session was grouped into tracks such as operations, development and architecture. They had a half-way decent app built by [Double Dutch](https://play.google.com/store/apps/details?id=me.doubledutch.cassandrasummit) that provided a way to schedule which sessions you wanted to see.  The app worked well, and provided a few 'games' mostly designed to get you to visit the vendors.

The sessions were divided into 3 groups. The first group was geared towards managers on what people did or how to integrate Cassandra into your company. Typically these were fairly useless. The ones I accidently attended were fairly useless. There was a session defined as 'hands on' that was a overview of technologies installed.

The second group of sessions were technical deep-dives. A fairly crowded one consisted of folks from [The Last Pickle](http://thelastpickle.com/) going over the source code for how data is deleted in Cassandra. Extremely useful as it shows why certain behaviors within Cassandra exist, and guided you into programming with those behaviors in mind. There could have been more of these types of sessions and in bigger rooms. I had to sit on the floor for one of them even with my priority pass.

The third group was a best practices or "Hey, this is what worked for us."  The tech head from the Weather Group did a great presentation about their attempts to scale up their ability to process incoming datasets... showing what they tried first that failed, and what actually worked.

A few notes from the summit: [Spark](http://spark.apache.org/) is everywhere. People seem to be using Spark with Cassandra for any type of analytics or reporting. Also, [Zeppelin](https://zeppelin.incubator.apache.org/) has been getting a lot of mention too. Its a electronic notebook to create and share Spark 'recipes' in the same way you can a RStudio project... perfect for folks in data analytics or just looking for a quick way to visualize data in Cassandra. I need to install both Spark and Zeppelin and see what I can do there.
