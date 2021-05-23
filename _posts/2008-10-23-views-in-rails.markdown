---
author: wolpert
comments: true
date: 2008-10-23 17:51:38+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/10/23/views-in-rails/
slug: views-in-rails
title: Views in Rails
wordpress_id: 88
categories:
- Code
---

I had to create a view for a join table of a many-to-many relationship in my model. To do this, I had to have a database migration use the 'execute' command to create the view. Tests failed because the schema.rb dump file does not deal with views. To fix, I had to set the following in my environments.rb file.


ActiveRecord::Base.schema_format= :sql



Then everything worked. At that point, it was just fixing my tests.
