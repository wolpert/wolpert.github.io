---
author: wolpert
comments: true
date: 2009-07-08 23:18:29+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2009/07/08/ruby-activemessaging-and-activemq/
slug: ruby-activemessaging-and-activemq
title: Ruby, ActiveMessaging and ActiveMQ
wordpress_id: 141
categories:
- Code
---

Just wanted to have a quick post on how we switched to ActiveMQ for our ruby app. We ran into problems that were easy to fix though hard to see where the error was. The first was a problem with idle connections and firewalls, and the second was how slow consumers 'ate' off the ActiveMQ queue.

In our situation, the pollers/consumers of the messages exist in the DMZ, and the ActiveMQ server is behind an internal firewall. This firewall drops connections that are idle for >1 hr. ActiveMessaging, for some reason I still do not understand, does not re-connect in this situation, though ActiveMQ sees the consumers as not connected. And you can't have ActiveMessaging clients 'ping' the server... no such API request possible. Suggestion on the web to fix this: Create a 'keep-alive' topic that you ping once in a while. Since its a topic and not a queue, all listeners get the ping. No idle connections now. (In our firewall, you cannot turn of it behavior on a single port, so we opted to go for the keep-alive topic.) Is this optimal? Not really, but it does work.

The second issue was 'greedy' consumers. If we pushed 10 messages into a queue, and the queue had 3 consumers, one consumer would get all ten. If the client died after the first message, the other nine would be lost. Solution was to add the ":ack=>'client'" header, so the client acknowledges only after its done processing the current message. Second issue, if you started up one consumer and 10 messages were in the queue, then started up two more consumers, the first client again would only process those 10 messages. Though if it died after the first message, then ActiveMQ would give the other messages (redeliver) to the other consumers. Solution was to set the activemq.prefetchSize to one. Both of these are done on the processor's definition, not in the configuration file for ActiveMQ. The magical incantation is this:

`
subscribes_to :mail_event, :ack=>'client', 'activemq.prefetchSize'.to_sym=>1`

The hard part was that in ActiveMQ, you have several different prefetchSize options, but the correct location was in the stomp section as its protocal dependent, and then 'where' to set it in ActiveMessaging got confusing. But it now works like a champ.
