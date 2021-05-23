---
author: wolpert
comments: true
date: 2015-09-27 18:31:15+00:00
layout: post
link: https://codeheadsystems.wordpress.com/2015/09/27/final-notes-from-the-2015-cassandra-summit/
slug: final-notes-from-the-2015-cassandra-summit
title: Final Notes from the 2015 Cassandra Summit
wordpress_id: 445
categories:
- Code
tags:
- Cassandra
---

This is my last post about the 2015 Cassandra Summit. This is mostly a list of random details that I wanted to keep track of. Most people may not find this useful.

DataStax 4.8 will have better 'encryption at rest' then previous DataStax versions. There are other providers then DataStax that should be looked at too. Note that you should use eCryptFS to encrypt the commit-log file since its typically not encrypted at rest.

Slide reviews for getting encryption right can be found at [Nate's Slide Share site.](http://www.slideshare.net/zznate/hardening-cassandra-for-compliance-or-paranoia) He goes over a ton including what's wrong with how DataStax documents how to install node-node and client-node encryption, and how to do it right.

Vnodes... 256 could be high. Cassandra 3.0 will start doing 64 vnodes per physical server instead. Do not mix single token nodes and vnodes in the same datacenter. To get a mix in the same cluster, use two datacenters. Solr/Lucene and Spark currently want single-token nodes, but that's changing.

Java drivers should have token-aware policies enabled. No load-balancer between clients and datacenter cluster. Seriously, your load balancer will do all the wrong things.

When developing code, use local consistency levels even if you have just one data center.  Also, you only think you need immediate consistency. When possible, use LOCAL_ONE for both reads and writes. (And don't mistakenly use SimpleStrategy in production.)

Dropping keyspaces does not remove data from disk. (Snapshots) Remember this QA folks and for integration tests.

In general, secondary indexes are useless with the following caveats. If a partition has a ton of values, a secondary index is useful provided you also provide the partition key. Spark Integration can actually benefit from secondary indexes with the DSE install, as each Spark instance will talk to their local Cassandra node.

Low values in commitlog_total_space_in_mb will reduce the number of memtables in memory. So you may need to up that number. 4G may be appropriate. There is a direct correlation between heap size and commit log size.

Compaction can be tuned to start when sstables count is between 4 and 32 sstables per memtable. Less SSTables on disk makes reads faster, but compaction causes high io... so... yeah.

Memtables are HashMaps of array lists (currently)

Remember, if you enable RowCache in your table, the cassandra.yaml file needs to have it enabled too. (Each node)

LevelCompaction strategy should only be used with SSDs. You don't really need the commit log on SSDs, even if your SSTables are.

Do not manually compact. If you do, you will have to forever. Also, if you change the compaction strategy, the next compaction will be huge. So just don't.

Cassandra is CPU bound for writes, and uses memory for reads. 16G-64G ram is recommended even if the heap size is only 8G. Disk caching in linux gets the rest of them memory, which helps you out a ton.

Cassandra sweet spot is 8 cores. More i you have Spark/Solr with Cassandra on the same box.

Sized compaction needs 50% of disk free. Level compaction needs 10% free. SSDs give you 3-5t/node, with rotation drives, 1t/node. Be careful if you go as high as 20T/node... rebuilds will suck, as much as your admins life will.

Expect nodes to be added. Single-token nodes you'll have to double them up. Vnodes you can just add them one at a time.

Use nodetool cleanup after you add nodes to the cluster or decrease replication factor. That will clean up disk space. Its an optimized compaction. If you wait, it'll clean up itself.

Run repair weekly in 2.1. Looks like that will change in 3.0. Run repairs on a few nodes at a time to reduce overhead. Also, use the 'pr' setting so you're not repairing too much. (Should have been the default)  'pr' means only repair data it owns, not data from other nodes. Repairing the data you own will also cause repairs on other nodes... so, yeah.

Always use prepared statements. Always. If you are not, you're doing something wrong. (Reduces load)

async queries are better, but more complicated.

Batch queries should stick in the same partition key for performance gain.

Cassandra/Lucene plugin that is recommended outside of DataStax: [cassandra-lucene-index](https://github.com/Stratio/cassandra-lucene-index) by Stratio.


