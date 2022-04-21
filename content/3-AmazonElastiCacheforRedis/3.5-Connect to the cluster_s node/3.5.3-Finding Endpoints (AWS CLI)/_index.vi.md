---
title : "Endpoints use AWS CLI"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.5.3 </b> "
---

Bạn có thể sử dụng AWS CLI cho Amazon ElastiCache để khám phá các endpoint cho các node, cluster và replication groups.

- Tìm endpoint cho node và cluster (AWS CLI)
- Tìm endpoint cho các nhóm sao chép (AWS CLI)

### Tìm Endpoints for Nodes and Clusters (AWS CLI)

Bạn có thể sử dụng AWS CLI để khám phá các endpoint cho một cluster và các node của nó bằng lệnh  **`describe-cache-clusters`**. Đối với các cluster Redis, lệnh trả về endpoint của cluster. Nếu bạn bao gồm tham số tùy chọn **`--show-cache-node-info`**, lệnh cũng sẽ trả về endpoint của các node riêng lẻ trong cluster.

Lệnh sau lấy thông tin cluster cho *single-node Redis (cluster mode disabled) cluster*  mycluster.

- Đối với Linux, macOS hoặc Unix:

```
aws elasticache describe-cache-clusters \
    --cache-cluster-id redis-cluster \
    --show-cache-node-info  

```

- Đối với Windows:

```
aws elasticache describe-cache-clusters ^
    --cache-cluster-id redis-cluster ^
    --show-cache-node-info  

```

Đầu ra từ thao tác trên sẽ giống như thế này (định dạng JSON).

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

Bạn có thể sử dụng AWS CLI để khám phá các endpoint cho một replication group và các cluster của nó bằng lệnh **describe-replication-groups**. Lệnh trả về primary endpoint của replication group và danh sách tất cả các cluster (node) trong replication group với endpoint của chúng, cùng với reader endpoint.

Thao tác sau đây truy xuất primary endpoint và reader endpoint của replication group `myreplgroup`. Sử dụng primary endpoint cho tất cả các hoạt động ghi.

```
aws elasticache describe-replication-groups \
    --replication-group-id myreplgroup

```

*Đối với Windows*:
```
aws elasticache describe-replication-groups ^
    --replication-group-id myreplgroup
```

Đầu ra từ thao tác này sẽ trông giống như thế này (định dạng JSON).

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
                     "CurrentRole": "replica", 
                     "PreferredAvailabilityZone": "us-west-2c", 
                     "CacheNodeId": "0001", 
                     "ReadEndpoint": {
                        "Port": 6379, 
                        "Address": "myreplgroup-003.1abc4d.0001.usw2.cache.amazonaws.com"
                     }, 
                     "CacheClusterId": "myreplgroup-003"
                  }
               ], 
               "NodeGroupId": "0001", 
               "PrimaryEndpoint": {
                  "Port": 6379, 
                  "Address": "myreplgroup.1abc4d.ng.0001.usw2.cache.amazonaws.com"
               },
               "ReaderEndpoint": {
                  "Port": 6379, 
                  "Address": "myreplgroup-ro.1abc4d.ng.0001.usw2.cache.amazonaws.com"
               }
            }
         ], 
         "ReplicationGroupId": "myreplgroup", 
         "AutomaticFailover": "enabled", 
         "SnapshottingClusterId": "myreplgroup-002", 
         "MemberClusters": [
            "myreplgroup-001", 
            "myreplgroup-002", 
            "myreplgroup-003"
         ], 
         "PendingModifiedValues": {}
      }
   ]
}

```





