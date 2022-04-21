---
title : "Tạo một cluster (mode enabled cluster)"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.1.2 </b> "
---

### Tạo một cluster (cluster mode enable)

1. Tạo một file python có tên ClusterModeEnabled.py
2. Sao chép chương trình sau và dán vào tệp có tên ClusterModeEnabled.py.

```
import boto3
import logging

logging.basicConfig(level=logging.INFO)
client = boto3.client('elasticache')

def create_cluster_mode_enabled(CacheNodeType='cache.t3.small',EngineVersion='6.0',NumNodeGroups=1,ReplicasPerNodeGroup=1, ReplicationGroupDescription='Sample cache with cluster mode enabled',ReplicationGroupId=None):
    """Creates an Elasticache Cluster with cluster mode enabled

    Returns a dictionary with the API response

    :param CacheNodeType: Node type used on the cluster. If not specified, cache.t3.small will be used
    Refer to https://docs..amazon.com/AmazonElastiCache/latest/red-ug/CacheNodes.SupportedTypes.html for supported node types
    :param EngineVersion: Engine version to be used. If not specified, latest will be used.
    :param NumNodeGroups: Number of shards in the cluster. Minimum 1 and maximun 90.
    If not specified, cluster will be created with 1 shard.
    :param ReplicasPerNodeGroup: Number of replicas per shard. If not specified 1 replica per shard will be created.
    :param ReplicationGroupDescription: Description for the cluster.
    :param ReplicationGroupId: Name for the cluster
    :return: dictionary with the API results

    """
    if not ReplicationGroupId:
        return 'ReplicationGroupId parameter is required'
    
    response = client.create_replication_group(
        AutomaticFailoverEnabled=True,
        CacheNodeType=CacheNodeType,
        Engine='redis',
        EngineVersion=EngineVersion,
        ReplicationGroupDescription=ReplicationGroupDescription,
        ReplicationGroupId=ReplicationGroupId,
    #   Creates a cluster mode enabled cluster with 1 shard(NumNodeGroups), 1 primary node (implicit) and 2 replicas (replicasPerNodeGroup)
        NumNodeGroups=NumNodeGroups,
        ReplicasPerNodeGroup=ReplicasPerNodeGroup,
        CacheParameterGroupName='default.redis6.0.cluster.on'
    )

    return response


# Creates a cluster mode enabled 
response = create_cluster_mode_enabled(
    CacheNodeType='cache.m6g.large',
    EngineVersion='6.0',
    ReplicationGroupDescription='Redis cluster mode enabled with replicas',
    ReplicationGroupId='redis20210',
#   Creates a cluster mode enabled cluster with 1 shard(NumNodeGroups), 1 primary (implicit) and 2 replicas (replicasPerNodeGroup)
    NumNodeGroups=2,
    ReplicasPerNodeGroup=1,
)

logging.info(response)

```

3. Để chạy chương trình, hãy nhập lệnh sau:
   
```
python ClusterModeEnabled.py
```

Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file ClusterModeEnabled.py"

```


### Tạo một cluster (cluster mode enable) với TLS và RBAC

Để đảm bảo tính bảo mật, bạn có thể sử dụng Transport Layer Security (TLS) và Role-Based Access Control (RBAC) khi tạo một cluster (cluster mode enable). Không giống như Redis AUTH, nơi tất cả các máy khách được xác thực có toàn quyền truy cập replication group nếu mã thông báo của họ được xác thực, RBAC cho phép bạn kiểm soát quyền truy cập cluster thông qua các user group. User groups này được thiết kế như một cách để tổ chức quyền truy cập vào các replication group.


1. Tạo một file python có tên ClusterModeEnabledWithRBAC.py

2. Sao chép chương trình sau và dán vào file có tên ClusterModeEnabledWithRBAC.py.


```
import boto3
import logging

logging.basicConfig(level=logging.INFO)
client = boto3.client('elasticache')

def create_cluster_mode_enabled(CacheNodeType='cache.t3.small',EngineVersion='6.0',NumNodeGroups=1,ReplicasPerNodeGroup=1, ReplicationGroupDescription='Sample cache with cluster mode enabled',ReplicationGroupId=None,UserGroupIds=None, SecurityGroupIds=None,CacheSubnetGroupName=None,CacheParameterGroupName='default.redis6.0.cluster.on'):
    """Creates an Elasticache Cluster with cluster mode enabled and RBAC

    Returns a dictionary with the API response

    :param CacheNodeType: Node type used on the cluster. If not specified, cache.t3.small will be used
    Refer to https://docs..amazon.com/AmazonElastiCache/latest/red-ug/CacheNodes.SupportedTypes.html for supported node types
    :param EngineVersion: Engine version to be used. If not specified, latest will be used.
    :param NumNodeGroups: Number of shards in the cluster. Minimum 1 and maximun 90.
    If not specified, cluster will be created with 1 shard.
    :param ReplicasPerNodeGroup: Number of replicas per shard. If not specified 1 replica per shard will be created.
    :param ReplicationGroupDescription: Description for the cluster.
    :param ReplicationGroupId: Name for the cluster.
    :param CacheParameterGroupName: Parameter group to be used. Must be compatible with the engine version and cluster mode enabled.
    :return: dictionary with the API results

    """
    if not ReplicationGroupId:
        return 'ReplicationGroupId parameter is required'
    elif not isinstance(UserGroupIds,(list)):
        return {'Error': 'UserGroupIds parameter is required and must be a list'}

    params={'AutomaticFailoverEnabled': True, 
            'CacheNodeType': CacheNodeType, 
            'Engine': 'redis', 
            'EngineVersion': EngineVersion, 
            'ReplicationGroupDescription': ReplicationGroupDescription, 
            'ReplicationGroupId': ReplicationGroupId, 
            'SnapshotRetentionLimit': 30, 
            'TransitEncryptionEnabled': True, 
            'UserGroupIds':UserGroupIds,
            'NumNodeGroups': NumNodeGroups,
            'ReplicasPerNodeGroup': ReplicasPerNodeGroup,
            'CacheParameterGroupName': CacheParameterGroupName
        }

    # defaults will be used if CacheSubnetGroupName or SecurityGroups are not explicit.
    if isinstance(SecurityGroupIds,(list)):
        params.update({'SecurityGroupIds':SecurityGroupIds})
    if CacheSubnetGroupName:
        params.update({'CacheSubnetGroupName':CacheSubnetGroupName})

    response = client.create_replication_group(**params)
    return response

if __name__ == '__main__':
    # Creates a cluster mode enabled cluster
    response = create_cluster_mode_enabled(
        CacheNodeType='cache.m6g.large',
        EngineVersion='6.0',
        ReplicationGroupDescription='Redis cluster mode enabled with replicas',
        ReplicationGroupId='redis2021',
    #   Creates a cluster mode enabled cluster with 1 shard(NumNodeGroups), 1 primary (implicit) and 2 replicas (replicasPerNodeGroup)
        NumNodeGroups=2,
        ReplicasPerNodeGroup=1,
        UserGroupIds=[
            'mygroup'
        ],
        SecurityGroupIds=[
            'sg-7cc73803'
        ],
        CacheSubnetGroupName='default'

    )
    
    logging.info(response)

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python ClusterModeEnabledWithRBAC.py

```

Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file ClusterModeEnabledWithRBAC.py"

```

