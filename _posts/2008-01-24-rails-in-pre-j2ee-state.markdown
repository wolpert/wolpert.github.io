---
author: wolpert
comments: true
date: 2008-01-24 20:34:15+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/01/24/rails-in-pre-j2ee-state/
slug: rails-in-pre-j2ee-state
title: Rails in pre-J2EE state...
wordpress_id: 56
categories:
- Code
---

A line was crossed recently. I don't mind this line, its actually a good one. But its one that many in the Rails community don't think to much about.  Thanks to a new <a href="http://opensource.thinkrelevance.com/wiki/simple_services">Simple Service</a>, Rails has transaction demarcation in a service model. You define a 'stateless service' in your rails application where it handles a bit of business logic. It could impact multiple objects and multiple save points. If one of them fails, they all fail and the transaction is rolled back.  Yes, that's right, its the start of a framework needed for a primitive stateless EJB session bean.

Now its missing some key features, such as multi-phase commits and having an external file to define the type of transaction isolation for this one service, but we're not that far off. I'm sure many Rails folks miss out on the meaning behind this little plugin, but for those of us who have escaped the rigors and layers of the enterprise... well, this is a flashback.
