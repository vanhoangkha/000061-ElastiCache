---
title : "Use AWS CLI"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2.2 </b> "
---
#### Tạo một cluster bằng AWS CLI

Mã CLI sau đây tạo một Redis (cluster mode disabled) cache cluster không có bản sao.

Đối với Linux, macOS hoặc Unix:

```
aws elasticache create-cache-cluster \
--cache-cluster-id my-cluster \
--cache-node-type cache.r4.large \
--engine redis \
--engine-version 3.2.4 \
--num-cache-nodes 1 \
--cache-parameter-group default.redis3.2 \
--snapshot-arns arn:aws:s3:::my_bucket/snapshot.rdb
```

Đối với Windows:

```
aws elasticache create-cache-cluster ^
--cache-cluster-id my-cluster ^
--cache-node-type cache.r4.large ^
--engine redis ^
--engine-version 3.2.4 ^
--num-cache-nodes 1 ^
--cache-parameter-group default.redis3.2 ^
--snapshot-arns arn:aws:s3:::my_bucket/snapshot.rdb

```