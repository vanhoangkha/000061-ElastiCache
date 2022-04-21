---
title : "Connect to cluster node"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

#### Overview

Your application connects to your cluster using endpoints. endpoint is the unique address of the node or cluster.

- Redis standalone node, which uses the node's endpoint for both read and write operations.
- Redis (cluster mode disabled) clusters, which use the primary endpoint for all write operations. Use the reader endpoint to equally split connections to the endpoint between all read replicas. Use individual endpoint nodes for read operations (In the API/CLI these are called reader endpoints).
Redis (cluster mode enabled) clusters, which use the cluster's configuration endpoint for all operations that support commands (cluster mode enable). You must use a client that supports Redis Cluster (Redis 3.2). You can still read from individual endpoint nodes (In the API/CLI these are called reader endpoints).

#### Content

- [Cluster Mode Disable](3.5.1-redis-cluster-mode-disabled-clusters-endpoints-console/)
- [Cluster Mode Enable](3.5.2-redis-cluster-mode-enabled-cluster-console/)
- [Enpoint using AWS CLI](3.5.3-finding-endpoints-aws-cli/)