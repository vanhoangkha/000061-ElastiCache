---
title : "Cluster Mode Enabled"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.5.2 </b> "
---

Use **Configuration Endpoint** for both read and write operations. Redis determines which node of the cluster to access.

The following procedure demonstrates how to find and clone **Redis (cluster mode enabled) cluster endpoints**.

### Find node endpoints for a Redis (cluster mode enabled) cluster

1. Sign in to the AWS Management Console and open the ElastiCache console at https://console.aws.amazon.com/elasticache/.

2. From the navigation pane, select **Redis clusters**. A list of clusters running any version of Redis will appear.

3. From the list of clusters, select the cluster name of a cluster. The shard page opens.

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.2-Rediscustermodeenabledendpointsconsole/0001-connectenable.png)

4. Select the name of the shard you want the node's endpoint to. The list of shard nodes appears with each node's endpoint.


![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.2-Rediscustermodeenabledendpointsconsole/0002-connectenable.png)

5. Locate the Endpoint column and read the endpoint for each node.

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.2-Rediscustermodeenabledendpointsconsole/0003-connectenable.png)

**In-transit encryption not enabled**
```
clusterName.xxxxxx.regionAndAz.cache.amazonaws.com:port

rce.ameaqx.use1.cache.amazonaws.com:6379
```

**In-transit encryption enabled**
```
clustercfg.clusterName.xxxxxx.regionAndAz.cache.amazonaws.com:port

clustercfg.rce.ameaqx.use1.cache.amazonaws.com:6379
```