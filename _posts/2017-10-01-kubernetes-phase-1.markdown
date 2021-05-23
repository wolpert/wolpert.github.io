---
author: wolpert
comments: true
date: 2017-10-01 22:22:07+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2017/10/01/kubernetes-phase-1/
slug: kubernetes-phase-1
title: Kubernetes Phase 1
wordpress_id: 562
---

I just uploaded to [github](https://github.com/wolpert/kubeOnPi) a set of instructions and scripts that I'm using to install kubernetes on raspberry Pis. I've run into some weird funk due to the [arm OS install](https://www.reddit.com/r/raspberry_pi/comments/49a02s/arm64_images_for_raspberry_pi_3/) on the arm64 processor, and that many containers assume amd64. But this is a start.

The next steps is simplify the install a bit more, and add in instructions to include heapster and kubernetes-dashboard that is compatible. I'm planning on updating to a kernel that is arm64 compatible so I can do more fun stuff.  (Mesos)
