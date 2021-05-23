---
author: wolpert
comments: true
date: 2009-11-06 15:54:21+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2009/11/06/ubuntu-upgrade-notification-back-by-force/
slug: ubuntu-upgrade-notification-back-by-force
title: Ubuntu upgrade notification back (by force)
wordpress_id: 167
categories:
- Code
---

I'm not found of the notification 'pop-up' in Ubuntu. Rather, I miss the old icon in the notification area. Executing the following line in a terminal can fix this back to the way it was, pre-9.04. (As found on [ubuntumini](http://www.ubuntumini.com/2009/05/remove-pop-up-update-manager.html))

gconftool -s --type bool /apps/update-notifier/auto_launch false
