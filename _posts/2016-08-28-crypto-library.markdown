---
author: wolpert
comments: true
date: 2016-08-28 00:19:23+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2016/08/27/crypto-library/
slug: crypto-library
title: Crypto Library
wordpress_id: 496
---

I finally pushed my first version of [paranoia crypto](https://github.com/wolpert/crypto) library. Its basically a wrapper around Bouncy Castle. It 'expires' keys so they don't hang out in memory, forces AES-256, uses Scrypt for hashing, requires SecureRandom, and will include a proguard file to munge BC so it doesn't get into classloader issues on Android. (Google mucked with BC... I'm doing this instead of using spongy castle)

This library avoids the 128 limitations provided by default JCE usage, so you are hereby warned to check your local laws for compliance. I'll have to send out a post detailing why I had to make this library. If you want to use it, start with the SecuredParanoidManager and run from there. I'll work on some better examples of how I intend it to be used.
