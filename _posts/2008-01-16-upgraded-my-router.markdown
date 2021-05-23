---
author: wolpert
comments: true
date: 2008-01-16 20:34:42+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2008/01/16/upgraded-my-router/
slug: upgraded-my-router
title: Upgraded my router...
wordpress_id: 58
categories:
- Code
---

So, I got tired of my laptop bailing out at my kitchen bar, which is about as far away from my wireless router as you can get in my house. I decided that it was time to either upgrade the router to dd-wrt, or brick it. Those that don't know, <a href="http://www.dd-wrt.com/">dd-wrt</a> is an open-source firmware for routers which exposes lots of features that can make your cheap router pretend to be an expensive one. And if you do not upgrade it correctly, you turn your cheap router into an expensive brick.

In my case, all I wanted was assigned MAC addresses for my printer and server, and boost the wifi antenna power. I tried making my own antenna and buying special ones, but nadda. Since I upgraded my laptop to Ubuntu, I noticed the hacked firmware for its internal broadcom wifi card didn't work very well with the low signal at the spot where I like to work, so it kept dropping off the network. Going back to windows was not an option. So I took a shot of vodka and downloaded the latest firmware.

After quickly scanning the instructions, I realized I downloaded the wrong firmware, so I then got the right one. The WRT54GSv7 Linksys router of mine needed the micro, but people didn't trust the v24-rc6.2, so I used v24-rc5. I saw some instructions which included other firmware, in this case, for the WRT54GV8 which the instructions said to use, so I got them all. Save the HTML pages and away I went.

On a lark, I tried the Linksys GUI admin webpage to install the firmware, but no joy. So instead I installed the vxkiller firmware which did the trick. Router rebooted and I tftp'd the v24rc5 for my GSv7. It installed, but other then ping or tftp it did absolutely nothing. Took another shot.

With a slight buzz in head I said to myself, what the hell. I wasn't really following instructions so why start now? If I'm going to brick it, at least do it by being random and potentially drunk. I tftp'd the GSv8 firmware and it actually did work. Well, almost.

Everything came back online. My desktop that was Lan'd into the router could go anywhere, and the wireless was up. But in trying to change the router settings did not work. They just came back with white pages. I couldn't reconfigure dd-wrt... all the configs dropped away. So I finally started to check for the forums. 90% of what people said to do was to clear the router back to default firmware settings. And they said keep trying over and over until it works. So I spent an hour playing that game. I couldn't tell if it worked. Finally I decided to telnet into the router and manually set something like the SSID, which worked. Rebooted the router by removing the power cord, and when it came back, the SSID I set in the telnet session was still there and viewable in the web interface. Then I did my hard-reset and bingo, my SSID was reset. Yet the web interface still didn't work. Damn.

Searching the forum for data, I was worried that the firmware I installed was really crap. Then I decided to pay attention to the other 10% of the comments; clear your browser cache and cookies. So, with a simple click in my firefox to clear all that stuff and it just started to work. I set the SSID, changed my encryption back to what it was, added the MAC filters and upped the power of the wifi to 70mw. It just worked fine. Rebooted it and the settings remained in play.

Not only does my laptop connect, it's now faster. My wifes computer which has a wireless card in it downloaded its Ubuntu updates at super fast speed, and I didn't have to spend a dime to get my upgrade. Just a few shots of vodka.
