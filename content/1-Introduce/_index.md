---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Overview

 **Amazon ElastiCache** is a service that makes it easy to set up, manage, and scale data storage in a distributed memory or cache environment. It provides a high-performance, scalable and cost-effective caching solution. It also eliminates the complexity involved in deploying and managing distributed cache environments.

 **ElastiCache for Redis** has many features:
- Automatically detect and recover from node failures.
- Redis (cluster mode enabled) supports partitioning your data up to 500 shards.
- Availability Zone locations of nodes and clusters are flexible for increased fault tolerance.
- Integrates with other AWS services such as Amazon EC2, Amazon CloudWatch, AWS CloudTrail, and Amazon SNS, providing a high-performance and highly secure managed in-memory caching solution.
- **ElastiCache for Redis** manages backups, patching, automatic error detection and recovery.

### Clusters

The basic component of ElastiCache for Redis is called a cluster.

A cluster is a collection of one or more cache nodes, all running one instance of the Redis cache engine software.

When you create a cluster, you specify the engine and version for all nodes to use. Your ElastiCache for Redis instances are designed to be accessible through Amazon EC2 instances. You can create and modify a cluster using the AWS CLI, ElastiCache for Redis API, or the AWS Management Console.

- Each ElastiCache for Redis cluster runs an instance of the Redis engine. Each Redis engine version has its own supported features. In addition, each Redis engine instance has a set of parameters in a parameter group that control the behavior of the clusters it manages.

- The compute capacity and memory capacity of a cluster is determined by its instance or node or class. You can choose the type of node that best meets your needs. If your needs change over time, you can change the **node type**.

- You can also take advantage of data hierarchy considering your node type needs. Data rating is a feature where some of the least-used data is stored on disk to minimize memory limitations on applications that can tolerate additional latency.

There are two types of node cluster storage: Standard and memory-optimized.

- They vary in performance and price characteristics, allowing you to tailor performance and storage costs to your needs.

- You can run a cluster on a virtual private cloud (VPC) using the Amazon Virtual Private Cloud (Amazon VPC) service. When you use a VPC, you have control over your virtual network environment. You can choose your own IP address range, create subnet groups, and configure routing lists and access control. ElastiCache manages backups, software patching, automatic failure detection and recovery.(*No extra cost to run your cluster in VPC*).

### ElastiCache nodes

- Node is the smallest building block of the ElastiCache implementation.
- A node can exist in isolation or in some relationship with other nodes.
- Node is a fixed-size piece of RAM that is attached to the network. Each node runs an instance of the engine, and the version was selected when you created your cluster. If needed, you can scale the nodes in a cluster up or down to a different instance type.
- Every node in a cluster is the same instance type and runs the same cache engine. Each cache node has its own Domain Name Service (DNS) port and name.

### ElastiCache for Redis shards

- A Redis shard (called a node group in the API and CLI) is a group of one to six related nodes. A Redis cluster (cluster mode disabled) always has a shard.
- Redis clusters (cluster mode enabled) can have up to 500 shards, with your data partitioned across shards.
- The node or shard limit can be increased to a maximum of 500 per cluster if the Redis engine version is 5.0.6 or higher. Make sure there are enough available IP addresses to accommodate the increase.