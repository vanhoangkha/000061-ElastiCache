---
title : "Cluster Mode Enabled"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.5.2 </b> "
---

Sử dụng **Configuration Endpoint** cho cả hoạt động đọc và ghi. Redis xác định node nào của cluster để truy cập.

Quy trình sau đây trình bày cách tìm và sao chép **Redis (cluster mode enabled) cluster endpoints**.

### Tìm node endpoints for a Redis (cluster mode enabled) cluster

1. Đăng nhập vào AWS Management Console và mở ElastiCache console tại https://console.aws.amazon.com/elasticache/.

2. Từ ngăn điều hướng, chọn **Redis clusters**. Danh sách các cluster đang chạy bất kỳ phiên bản Redis nào sẽ xuất hiện.

3. Từ danh sách các cluster, hãy chọn tên cluster của một cluster. Trang shard mở ra.

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.2-Rediscustermodeenabledendpointsconsole/0001-connectenable.png)

4. Chọn tên của shard mà bạn muốn endpoint của node. Danh sách các node của shard xuất hiện với endpoint của mỗi node.


![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.2-Rediscustermodeenabledendpointsconsole/0002-connectenable.png)

5. Định vị Endpoint column và đọc endpoint cho mỗi node.

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
