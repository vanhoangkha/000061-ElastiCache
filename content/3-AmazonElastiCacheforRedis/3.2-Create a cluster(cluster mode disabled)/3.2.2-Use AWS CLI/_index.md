---
title : "Use AWS CLI"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2.2 </b> "
---
#### Create a cluster using the AWS CLI

The following CLI code creates a Redis (cluster mode disabled) cache cluster with no replicas.

For Linux, macOS or Unix:

```
aws elasticache create-cache-cluster \
--cache-cluster-id my-cluster \
--cache-node-type cache.r4.large \
--engine redis \
--engine-version 3.2.4 \
--num-cache-nodes 1 \
--cache-parameters-group default.redis3.2 \
--snapshot-arns arn:aws:s3:::my_bucket/snapshot.rdb
```

For Windows:

```
aws elasticache create-cache-cluster ^
--cache-cluster-id my-cluster ^
--cache-node-type cache.r4.large ^
--engine redis ^
--engine-version 3.2.4 ^
--num-cache-nodes 1 ^
--cache-parameters-group default.redis3.2 ^
--snapshot-arns arn:aws:s3:::my_bucket/snapshot.rdb

```