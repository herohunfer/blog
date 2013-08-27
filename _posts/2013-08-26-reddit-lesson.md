---
layout: post
title: "reddit lesson"
category:
tags:
---
Postgres

Currently it would be very expensive to move out of EC2. This is why EC2 allows you to ingress data for free and charge you to take it out. They want you to put all your data in the cloud.

Most data at reddit is key-value and it is stored in Postgres. Everything that deals with money is kept in a relational database because of transactions and easier analytics.

Cassandra   
* fast negative lookups
* easy incremental scalability
* no single point of failure

Consistent hashing is very important for scaling (cannot rebalance when grow the cache)

Using a proxy was a huge boon to scaling. User could be routed based on the URLs they were hitting. Reddit had a system that would monitor how long every URL took to service. People were put into different lanes. Slow traffic went one place and fast traffic went another.  Splitting traffic based on the median speed of response was a huge boost.
(Why is that?)



