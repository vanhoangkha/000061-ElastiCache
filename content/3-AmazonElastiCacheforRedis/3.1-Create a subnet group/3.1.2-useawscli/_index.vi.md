---
title : "Use AWS CLI"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.1.2 </b> "
---

#### Tạo subnet group sử dụng AWS CLI

1. Tại dấu nhắc lệnh, sử dụng lệnh `**create-cache-subnet-group**` để tạo một subnet group.

- For Linux, macOS, or Unix:

```
aws elasticache create-cache-subnet-group \
    --cache-subnet-group-name mysubnetgroup \
    --cache-subnet-group-description "Testing" \
    --subnet-ids subnet-53df9c3a
```

- For Windows:

```
aws elasticache create-cache-subnet-group ^
    --cache-subnet-group-name mysubnetgroup ^
    --cache-subnet-group-description "Testing" ^
    --subnet-ids subnet-53df9c3a
```

2. Lệnh này sẽ tạo ra kết quả tương tự như sau:

```
{
    "CacheSubnetGroup": {
        "VpcId": "vpc-37c3cd17", 
        "CacheSubnetGroupDescription": "Testing", 
        "Subnets": [
            {
                "SubnetIdentifier": "subnet-53df9c3a", 
                "SubnetAvailabilityZone": {
                    "Name": "us-west-2a"
                }
            }
        ], 
        "CacheSubnetGroupName": "mysubnetgroup"
    }
}

```