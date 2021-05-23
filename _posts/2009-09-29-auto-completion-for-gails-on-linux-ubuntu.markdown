---
author: wolpert
comments: true
date: 2009-09-29 19:39:29+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2009/09/29/auto-completion-for-gails-on-linux-ubuntu/
slug: auto-completion-for-gails-on-linux-ubuntu
title: Auto-completion for grails on Linux (Ubuntu)
wordpress_id: 164
categories:
- Code
---

Starting to be full time on grails, I wanted to get bash command line completion to work. I took code from [Fernando Takai](http://www.grails.org/Grails+Bash+Completion) and made very minor changes so it works on Ubuntu. You need to install gawk to get it to work. Just copy it to the /etc/bash_completion.d/ directory and you should be gold. Here is the source for the [grails_bash_completion.sh](http://pastie.org/635551) file.
