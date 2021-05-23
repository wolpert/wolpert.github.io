---
author: wolpert
comments: true
date: 2013-01-25 04:53:16+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2013/01/24/lenovo-x230-windows-8-and-ubuntu/
slug: lenovo-x230-windows-8-and-ubuntu
title: Lenovo x230, Windows 8 and Ubuntu
wordpress_id: 302
---

Just a quick note for people who bought a laptop with Windows8 (W8) and want to use Ubuntu without destroying W8. And in my case, I have the Lenovo  x230 ThinkPad with secure boot. This is what I did to accomplish this.

You can easily install 12.10 on this ThinkPad. Before you do, make sure you install all the Lenovo windows drivers you can, including firmware updates. Then create a windows recovery disk. (Yeah, searching for the recovery media creation program in W8 sucks on the x230. Google it... maybe a MS geek could find it easier then I did.)

I first re-partitioned the Windows disk via W8 to make a second drive. I booted into the BIOS via the windows 'troubleshoot' restart facility (Yeah, you heard me. You can't get into the BIOS normally anymore until you install Ubuntu. UEFI fail.) (EDIT: Yeah yeah, UEFI replaces BIOS... still annoyed.) After disabling secure boot, I could boot off a Ubuntu installer USB drive and get a real OS on it.

After the Ubuntu install is complete, and you rebooted, you'll notice that Linux works fine, and Windows won't boot anymore. To fix that, I installed the [boot-repair tool](https://help.ubuntu.com/community/Boot-Repair) in Ubuntu and ran it, accepting all the defaults it gave me. When it was done, I got about 3 different windows partitions to boot in grub next time... and the second one is what worked to get back to my game^h^h^h^hwindows OS. (Isn't that why you want W8 in the first place anyways?)

Of course, if all else fails, you can reuse your recover USB disk you made... right? Or forget running w8 native and run it via VirtualBox.

[Disclaimer: YMMV....]
