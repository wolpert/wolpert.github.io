---
author: wolpert
comments: true
date: 2017-09-17 17:04:32+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2017/09/17/easy-bake-data-center/
slug: easy-bake-data-center
title: Easy-Bake Data Center
wordpress_id: 523
---

I cleaned up my office a few weeks ago. Collected the few raspberry pi's that are unused. The odd switch; cheap, unmanaged, but efficient. Sure, I'm still in the process of making a game, but like most humans, I'm easily distracted. This distraction got to me when a saw the switch. And of course, when you see a switch, you think about deployment pipelines.

I work at Amazon, and the way we deploy software is fairly cool. When I write software at home, they way I deploy sucks. Its fine for me, but it 'could be' soooo much more. So a quick search on-line turned up the Netflix deployment pipeline they open-sourced called [spinnaker](https://www.spinnaker.io/). Spinnaker sounded like something I wanted to try. Which, of course, means I have to run it somewhere. And no, I'd rather not run it on my development desktop. Besides, having places to run little apps at home is nice, especially since I'd rather not have to keep my desktop on all the time. Raspberry pi's are great for these types of things.

At $35 a pop, not including SD disk drives, they make perfectly fine compute nodes for a home environment. And there is an active community creating clusters of various sizes. So I looked at my switch and said screw it, lets build a data-center the same way Hasbro said lets build an oven. Here's the initial play-list of goodness:



	
  * [HypriotOS](http://blog.hypriot.com/) for the Linux installs. Raspberry pi meets Docker.

	
  * [Kubernetes](https://kubernetes.io/) to manage the docker installs. Following instructions on this [post](http://blog.kubernetes.io/2015/12/creating-raspberry-pi-cluster-running.html).

	
  * NFS mounted file-system with one host using 1TB [hard drives](https://www.amazon.com/dp/B00CRZ2PRM/ref=psdc_595048_t1_B01LQQHI8I) (For sharing/storing data like [ab initio](https://en.wikipedia.org/wiki/Ab_initio_quantum_chemistry_methods) calcs I want to start [running again](http://www.psicode.org/).)

	
  * [Spinnaker](https://www.spinnaker.io/), which started all this for me.

	
  * And not a lot of money, considering


That last part is the interesting part. This is more of a learning exercise then anything else. For a few bucks, I get to build and play with an easy-bake oven version of a data center using modern techniques. I get a simple place to build my software, or run my old calculations 24x7, and the cluster is easily expandable if I so desire. No monthly costs beyond electricity once it's setup. What's not to love?
