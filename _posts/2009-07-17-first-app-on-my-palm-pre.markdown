---
author: wolpert
comments: true
date: 2009-07-17 01:10:34+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2009/07/16/first-app-on-my-palm-pre/
slug: first-app-on-my-palm-pre
title: First app on my palm pre...
wordpress_id: 147
categories:
- Code
---

Finally got the Palm Pre SDK today. Palm released it like 10 months sooner then Apple did for their smartphone, and 15 months later then Google did for their smartphone. VirtualBox is used for the emulator, and Eclipse makes the SDK developer-friendly. Note that the recommended versions of both apps is not the latest... I used what they said to use on my Ubuntu install. One change from their install instructions, I used the following repo for the VirtualBox for my Ubuntu 9.04

    
    deb http://download.virtualbox.org/virtualbox/debian jaunty non-free


Anyways... a few side comments. First, read the instructions in their 'Hello World' app. It works great. Use the emulator. It works great. The command line tools also work great. Except for one part. You cannot, after following their instructions, put the Hello World app on a real palm. On the forums, someone mention about having to use the 'secret password' to get the developer tools available. Information can be found [here](http://developer.palm.com/distribution/viewtopic.php?f=6&t=89&p=282). After the installation, all the instructions are fine.

Side note: in Eclipse, once you are using the 'Emulator' to run the app, if you want to switch to have Eclipse use your palm, right click on the project and select properties. In 'Run/Debug Settings', select your application, hit edit and change the target. You can futz with Eclipse to get multiple run targets off the menu, but I'll leave that as an exercise to the reader.

First impression? Its fun and easy. Second impression will take a few days.

EDIT: As mentioned in [this link](http://developer.palm.com/distribution/viewtopic.php?f=6&t=93), you can use Eclipse 3.5, Aptana 1.5 and Virtual Box 3.0.2 instead of the older versions mentioned by Palm in their SDK. (Aptana version should use this url: http://update.aptana.com/install/studio instead of the listed one.)[](http://update.aptana.com/install/studio)
