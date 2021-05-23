---
author: wolpert
comments: true
date: 2008-05-10 20:35:37+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/05/10/git-versus-mercurial/
slug: git-versus-mercurial
title: Git versus mercurial...
wordpress_id: 62
categories:
- Code
---

I've been playing now with git and mercurial lately. Between rails developers choosing git and all of Sun switching to mercurial, I wanted to see which made more sense. What I liked about CVS was the ability to tag things. Tags were cheap, but branching 'felt' expensive. Subversion was faster then CVS, worked better remotely, directories were in the 'version history', and branching was cheap. But tags really didn't exist. Plus any changes changed the latest revision in any branch or tag, which is dumb. Interacting with the repository also required you to be online, and with a reasonable connection speed, just like CVS. (At least svn was faster then cvs there)

There is no argument against a distributed VCS, especially if they fix the problems with subversion, but which one? The most popular are git and mercurial... so darcs feels alone these days. Git and mercurial are basically feature complete with each other. Both get the job done, but they are built with different core preferences which seems to be evident from their resulting executables. Git was written by Linux kernel hackers using lots of perl scripts with a basic wrapper for most activities. Mercurial is a python script written by application-level coders. Again, 95% of the usage patterns are the same for each of these. Some differences have <a href="http://www.rockstarprogrammer.org/post/2008/apr/06/differences-between-mercurial-and-git/">been documented</a> before, and here are mine which include information from that blog post:

The mercurial script can serve the repository itself. Both git and hg allow for using HTTP/S for accessing a code repository like mod_dav_svn for subversion, and both make use of SSH for pushing/pulling repository information. Git has a separate daemon that you have to run to make use of the 'git' protocol, whereas I can call 'serve' on the hg program to make my code available from my desktop right away. Git requires more configuration to get it working. For this, I prefer mercurial.

Mercurial considers commits immutable by default, whereas git is flexible, and allows for changes against the history in the revision.  I really like the immutable approach... and even subversion's constant updates to tags isn't changing history like git can. So, I really like how mercurial handles this as opposed to git. But this leads to other differences in how branches are dealt with in mercurial and git.

Branching is a very strong point of git, and shows the Linux kernel hackers influence. Branches in Mercurial are permanent, so failed branches live forever. (Immutability) Git branches can be dropped from the repository completely. The head of a branch in mercurial is 'inferred' by having no children, where as they are explicit in git. (Here, git is more like the CVS tagging HEAD technique and mercurial is more like subversion. Note that _both_ are better then subversion, but implicit versus explicit 'head' of a tree is a big difference) Git branching is a stronger system then mercurial for your developers, though mercurial may be better if you want to force history does not change. This is most likely why Linus made/picked git and why Sun picked Mercurial.

Overall, I can easily argue for either solution. Active development in a rails application does not require git, and writing a Java application does not require mercurial. You can use CVS with either if you wanted. Do not let the communities force you in a direction. On my desktop, I have RCS commands, svn, git, hg and darcs. They don't collide with each other, both are fast for committing code changes and pulling/pushing repository changes, so choose the one for your project you like and makes more sense for your business.
