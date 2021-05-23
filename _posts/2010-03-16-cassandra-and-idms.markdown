---
author: wolpert
comments: true
date: 2010-03-16 15:29:22+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2010/03/16/cassandra-and-idms/
slug: cassandra-and-idms
title: Cassandra and IDMS
wordpress_id: 208
categories:
- Code
---

The more I play with [Cassandra](http://cassandra.apache.org/), the more it seems like an [IDMS](http://en.wikipedia.org/wiki/IDMS) implementation for micros. Data keys point to files, which have structured methods to look up the data sets faster then in SQL, but the relationship between data sets are defined in code. I remember a discussion I had back when I worked at Edward Jones with some of the mainframe programmers. This one person couldn't understand why SQL had any benefits. She said something like "All SQL does is make you ignorant on how the data is going to be used." This was about 15 years ago. I'd love to know what she thinks about Cassandra, Big Table, etc. If Cassandra really catches on, then this will be the second major mainframe "framework" to become highly popular on these micros, with Message-oriented-middleware (MOM) being the first.

(And yes, I know Mom was always used on Unix system if you count [Tuxedo](http://en.wikipedia.org/wiki/Tuxedo_%28software%29)... it just wasn't that popular.)
