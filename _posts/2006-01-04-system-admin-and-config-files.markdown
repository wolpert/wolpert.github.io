---
author: wolpert
comments: true
date: 2006-01-04 20:21:44+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2006/01/04/system-admin-and-config-files/
slug: system-admin-and-config-files
title: System Admin and Config Files
wordpress_id: 20
categories:
- Business
---

I think I can go on a limb and say that the major part of a system administrator's job is caring for configuration files.  (Warning, what follows is a rant.)

You add a new user?  Modify the /etc/password file.  Adding a new domain name? bind gets its configuration files updated.  Apache?  Yeah, you may compile a new mod, but you're very very careful on how you use mod_proxy in the configuration file.  I bet you spend greater then 10x time on the httpd.conf configuration file when you add in mod_fastcgi then you did in compiling that mod, eh?  Configuration files are the implementation of deployment ideas for admins.  You've got 100 servers in your NOC handling 20 different applications... you better be understanding how those configuration files work line by line when you're adding your 101th server for one of those apps.

This limb seems pretty strong so let me continue a bit...  lets say your a system administrator who keeps assuming you understand the configurations for those 100 servers, but doesn't.  That 101th server that maps so perfectly in your diagrams to help offset the load that occured when sales finally could do their job and sell more stuff; it now needs to be deployed.  Do you start from scratch with that config file or do you find other apps and make sure you know what each piece does in that file before adding that 101th server?  102?  103?  104?  Tell me, what would you do?  And if its a new app, you going to read the manual on the configuration file settings before those 5000 new users start pounding the NOC again after the last time your deployment failed, right?  Maybe making sure you know what the app does this time?

Come on folks, this ain't rocket science. Administrators spend more of their job <i>administrating</i> configuration files then anything else... unless they are hardware suckers testing each component so the owner can save a buck from buying real equipment.  I really feel sorry for those people.  But the rest of you?  If you have to restart processes all the time, it simply means you can't use a mirid of other apps to help manage when apps die, which may not be your fault.  Its a sucky part of the job, but even that isn't the real focus.  Its configuration files.  I was one of you; I know what its like.  And I know there are people who can do this.  How the hell can someone hack a linux system to figure out why IRQ collisions are causing PCI cards to fail to load proper but be complely useless in setting configuration files on the fifth install of the same application after blaming software folks that they wrote it wrong?  Its fucking Tomcat!  Does it LOOK like sendmail.mc to you?  At least pick an m4 configuration to screw up... that's normal.  And stop blaming the developers because you forget how to write an xml file, okay?

Sorry, had to rant.  Its been a bad few days.
