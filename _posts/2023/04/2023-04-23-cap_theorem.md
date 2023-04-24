---
title: CAP theorem
date: 2023-04-23 18:15
category:
author:
tags: [programming, algorithms]
summary:
---

## Introduction
The CAP theorem, also known as Brewer's theorem, is a fundamental concept in distributed computing that provides insights into the tradeoffs that must be made when designing highly available, distributed systems. In this article, we will discuss the three key components of the CAP theorem and how they apply to distributed systems.

## What is the CAP theorem?
The CAP theorem states that in a distributed system, it is impossible to simultaneously provide more than two of the following three guarantees:

* Consistency: All nodes in the system see the same data at the same time.
* Availability: Every request made to a non-failing node in the system receives a response, without guarantee of whether it contains the most recent data or not.
* Partition Tolerance: The system continues to operate even when network partitions occur, i.e., when the communication between nodes is temporarily interrupted or delayed.

In other words, the CAP theorem involves tradeoffs between Consistency, Availability, and Partition Tolerance.

## Consistency vs. Availability vs. Partition Tolerance
When a network partition occurs, the nodes in the system will be divided into two or more disjoint groups, each group may not be able to communicate with the other groups. If the system chooses to maintain consistency and partition tolerance, then it must sacrifice availability. In other words, a request to a node in a partitioned group will result in an error or timeout, as the system waits for the group to rejoin before processing the request.

On the other hand, if the system chooses to maintain availability and partition tolerance, then it must sacrifice consistency. In other words, the system must accept that different nodes may see different versions of the same data at the same time.

If the system chooses to maintain partition tolerance and consistency, then it must sacrifice availability. In other words, the system must accept that requests to nodes in the partitioned group will result in an error or timeout.

The tradeoffs between Consistency, Availability, and Partition Tolerance are not always straightforward, and the optimal balance will depend on the specific requirements and constraints of each system.

## Conclusion
The CAP theorem highlights the tradeoffs that must be considered when designing distributed systems, and it emphasizes the importance of prioritizing the most critical system requirements. By understanding the tradeoffs between Consistency, Availability, and Partition Tolerance, developers can make informed decisions about how to design their systems to meet their business requirements. Ultimately, the decision of which two guarantees to prioritize is dependent on the specific use case and the business requirements of the system.