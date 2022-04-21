---
title : "Endpoints using AWS CLI"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.5.3 </b> "
---

You can use the AWS CLI for Amazon ElastiCache to discover endpoints for nodes, clusters, and replication groups.

- Find endpoints for nodes and clusters (AWS CLI)
- Find endpoints for replication groups (AWS CLI)

### Find Endpoints for Nodes and Clusters (AWS CLI)

You can use the AWS CLI to discover endpoints for a cluster and its nodes with the **`describe-cache-clusters`** command. For Redis clusters, the command returns the endpoint of the cluster. If you include the optional parameter **`--show-cache-node-info`**, the command will also return the endpoints of the individual nodes in the cluster.

The following command gets cluster information for *single-node Redis (cluster mode disabled) cluster* mycluster.

- For Linux, macOS or Unix:

```
aws elasticache describe-cache-clusters \
    --cache-cluster-id redis-cluster \
    --show-cache-node-info

```

- For Windows:

```
aws elasticache describe-cache-clusters ^
    --cache-cluster-id redis-cluster ^
    --show-cache-node-info

```

The output from the above should look like this (JSON format).

```
{
    "CacheClusters": [
        {
            "CacheClusterStatus": "available",
            "SecurityGroups": [
                {
                    "SecurityGroupId": "sg-77186e0d",
                    "Status": "active"
                }
            ],
            "CacheNodes": [
                {
                    "CustomerAvailabilityZone": "us-east-1b",
                    "CacheNodeCreateTime": "2018-04-25T18:19:28.241Z",
                    "CacheNodeStatus": "available",
                    "CacheNodeId": "0001",
                    "Endpoint": {
                        "Address": "redis-cluster.ameaqx.0001.use1.cache.amazonaws.com",
                        "Port": 6379
                    },
                    "ParameterGroupStatus": "in-sync"
                }
            ],
            "AtRestEncryptionEnabled": false,
            "CacheClusterId": "redis-cluster",
            "TransitEncryptionEnabled": false,
            "CacheParameterGroup": {
                "ParameterApplyStatus": "in-sync",
                "CacheNodeIdsToReboot": [],
                "CacheParameterGroupName": "default.redis3.2"
            },
            "NumCacheNodes": 1,
            "PreferredAvailabilityZone": "us-east-1b",
            "AutoMinorVersionUpgrade": true,
            "Engine": "redis",
            "AuthTokenEnabled": false,
            "PendingModifiedValues": {},
            "PreferredMaintenanceWindow": "tue:08:30-tue:09:30",
            "CacheSecurityGroups": [],
            "CacheSubnetGroupName": "default",
            "CacheNodeType": "cache.t2.small",
             "DataTiering": "disabled"
            "EngineVersion": "3.2.10",
            "ClientDownloadLandingPage": "https://console.aws.amazon.com/elasticache/home#client-download:",
            "CacheClusterCreateTime": "2018-04-25T18:19:28.241Z"
        }
    ]
}

```

### Finding the Endpoints for Replication Groups (AWS CLI)

You can use the AWS CLI to discover endpoints for a replication group and its clusters with the **describe-replication-groups** command. The command returns the primary endpoint of the replication group and a list of all clusters (nodes) in the replication group with their endpoints, along with the reader endpoint.

The following operation retrieves the primary endpoint and reader endpoint of the replication group `myreplgroup`. Use the primary endpoint for all write operations.

```
aws elasticache describe-replication-groups \
    --replication-group-id myreplgroup

```

*For Windows*:
```
aws elasticache describe-replication-groups ^
    --replication-group-id myreplgroup
```

The output from this operation should look something like this (JSON format).

```
{
   "ReplicationGroups": [
     {
       "Status": "available",
       "Description": "test",
       "NodeGroups": [
         {
            "Status": "available",
               "NodeGroupMembers": [
                  {
                     "CurrentRole": "primary",
                     "PreferredAvailabilityZone": "us-west-2a",
                     "CacheNodeId": "0001",
                     "ReadEndpoint": {
                        "Port": 6379,
                        "Address": "myreplgroup-001.1abc4d.0001.usw2.cache.amazonaws.com"
                     },
                     "CacheClusterId": "myreplgroup-001"
                  },
                  {
                     "CurrentRole": "replica",
                     "PreferredAvailabilityZone": "us-west-2b",
                     "CacheNodeId": "0001",
                     "ReadEndpoint": {
                        "Port": 6379,
                        "Address": "myreplgroup-002.1abc4d.0001.usw2.cache.amazonaws.com"
                     },
                     "CacheClusterId": "myreplgroup-002"
                  },
                  {
                     "CurrentRole":