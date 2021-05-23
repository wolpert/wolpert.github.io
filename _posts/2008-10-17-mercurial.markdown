---
author: wolpert
comments: true
date: 2008-10-17 17:30:00+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/10/17/mercurial/
slug: mercurial
title: Mercurial...
wordpress_id: 85
categories:
- Code
---

At this point, we've switched over to mercurial from subversion for a few months which impacted two separate projects directly, one of which is in production. I wanted to post about the impact of the switch.

Using mercurial has been so easy. Cloning repositories is quicker then it is to download a subversion project. So much faster that now when I have to use subversion on other projects its painful. But in a small team, the daily life of the developer has not really changed much. We still have the concept of a central repository that we push and pull our changes from. With five people actively committing changes, we do not need anything more complicated. Though I have cloned my own personal repository for doing some experiments on the code, which of course is nice.

For releases, mercurial has really shined compared to subversion. The tagging and the cloning of repositories makes all the difference. I've hated subversion's tagging and branching system... actually preferred CVS's techniques. And we took to heart that instead of branching a repository we clone it. I could see using repository branching within a master repository if I needed a full time configuration manager... but that would be for the master repository only; should not expect developers to use it that way. Rather I would expect the developer repositories to work like they do in our project now.

As far as git versus mercurial goes... there was no problem there. Rails projects don't really care which source code control you use, and capistrano works fine with both. Cruisecontrol.rb also works fine with both of them too. The advantage of mercurial is more subtle in reality. The lack of tons of 'git' programs all over the place, and the less confusing commands. Not to mention that git kinda requires 'compacting' the repository after a while, kind of like how subversion used to due to inefficiencies in BDB. But in reality, everyday usage of either git or mercurial becomes just 'the standard'. Once you're using it, you don't think about it.
