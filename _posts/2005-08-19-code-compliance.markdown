---
author: wolpert
comments: true
date: 2005-08-19 20:17:25+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2005/08/19/code-compliance/
slug: code-compliance
title: Code Compliance
wordpress_id: 12
categories:
- Code
---

An interesting couple of days this week at work.  Wed started with me talking to one of the admins at work first thing in the morning.  When I got to his cubical, he was very busy with two guys at his desk.  Instead of me asking him questions about something I had with our servers, he starts talking about how he's building a server and the software he's installing... and that he's almost done.  Then he introduces me to two people in his cube.  We had our main network guy quit, which is also his boss, so I figured these were network people.  No, as I found out, they help making sure our code is 'compliant', and we haven't stolen code from other places like open-source groups.  My next though was wait a minute... are we being audited?

In short, yes.  An internal audit of our code.  This had more to do with us evaluating a product that provides this service and we were evaluating it by auditing our code.  By instinct, I worked with these people and tried to be as helpful as possible.  ISO-9000 days at Philips taught me that well. But my gut reaction was "Who doesn't trust us?" and "What the hell do they think we do all day?  Copy code from open-source products?" and "Do they think their SCO?"  But focus away from me being a developer to someone managing disperse group of people including contractors, outsource folks and new hiers, and I can start to understand why someone would want to use this.

Managers really have no clue how code is really developed.  The assumption is that people will do what they can to get the work done quickly, and that contractors would reuse code between projects as much as possible.  If they can copy code from existing projects, then it will be copied to make their life easier.  In reality, that is harder then it sounds.  Number one, most business-based code is domain specific, and even then, specific to the company the software is for.  Number two, you have to fully understand the code you're working with and 'how' to copy it.  You're more likely to cause a problem using a GPL product as a library for your code then you are copying actual segments of code from that GPL library into your propriatary project.  The only time you'd realy know the code well enough to use in the current project from an open-source one is if you wrote it for the open-source project in the first place.  And even then, only if it was recent.

But here we are, managers need to make sure the people who work for them don't create a problem. I do see a reason that managers need to verify that the code they bought is unique and not infringing on other copyrights that could cause a legal headache.  Problems that 'can' happen easily include contractors reusing frameworks they don't have the right to reuse or developers using GPL libraries for propriatary projects.  But is this a real problem?  I really don't know.  I know that's something I'm careful to avoid.  But how do you check to see if this is happening and you cannot trust your own developers?  As I found out this week and the software product in question that provides this service is expensive.  Very expensive.  Trust and open discussion is much cheaper.  And if you do not (cannot) trust the outsouce folks building your project, then maybe outsourcing work isn't really that cheap after all.
