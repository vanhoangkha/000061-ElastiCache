---
title : "Tạo cluster(cluster mode enabled)"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3</b> "
---

#### Tạo một Redis (cluster mode enabled) cluster sử dụng ElastiCache console

1. Đăng nhập vào AWS Management Console và mở Amazon ElastiCache console tại https://console.aws.amazon.com/elasticache

2. Chọn **Redis cluster** từ ngăn điều hướng.

3. Chọn **Create Redis cluster**.

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0001-createclusterenable.png)

4. Đối với **Cluster settings**, hoàn thành các lựa chọn sau:

- Trong **Choose a cluster creation method**, chọn **Configure and create a new cluster**

5. Đối với **Cluster mode**, chọn **Enabled**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0002-createclusterenable.png)

6. Đối với **Cluster info**, hoàn thành nhập các thông tin sau:

- Trong **Name**, nhập tên cluster bạn muốn tạo.( Ví dụ: **`my-cluster-enable`**)
- Trong **Description**, nhập nội dung mô tả cluster của bạn.(Ví dụ: **`create cluster enable`**)

7. Đối với **Location**, chọn **AWS Cloud**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0003-createclusterenable.png)

8. Đối với ***Cluster settings**, hoàn thành các lựa chọn sau:

- Trong **Engine version**, chọn 6.2
- Trong **Port**, chọn 6379
- Trong **Parameter groups**, chọn **default.redis6.x.cluster.on**
- Trong **Node type**, chọn **cache.r6g.large**
- Trong **Number of shards**, chọn 3
- Trong **Replicas per shard**, chọn 2

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0004-createclusterenable.png)

9. Đối với **Subnet group settings**, hoàn thành nhập nội dung sau:

- Trong **Subnet groups**, chọn **Choose existing subnet group**
- Sau đó chọn subnet group đã tạo 3.1 Tạo một subnet group
- Trong **Associated subnets**, chọn **Availability Zone** và **Subnet ID** 


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0005-createclusterenable.png)

10. Đối với **Availability Zone placements**, hoàn thành các thông tin sau:

- Trong **Slots and keyspaces**, chọn **Equal distribution**
- Trong **Availability Zone placements**, chọn **Specify Availability Zones**

11. Chọn **Next**


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0006-createclusterenable.png)

12. Đối với **Advanced settings**, hoàn thành các lựa chọn sau:

- Trong **Selected security groups**, chọn security group mặc định

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0007-createclusterenable.png)

13. Đối với **Backup**, hoàn thành các lựa chọn sau:

- Chọn **Enable automatic backups**
- Trong **Backup retention period**, chọn 1
- Trong **Backup window**, chọn **No preference**

14. Đối với **Maintenance**, hoàn thành các lựa chọn sau:

- Trong **Maintenance window**, chọn **No preference**
- Phần **Topic for Amazon SNS notification**, chọn Amazon Resource Name (ARN) 


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0008-createclusterenable.png)

15. Đối với **Logs**, hoàn thành các lựa chọn sau:

- Trong **Slow logs**, chọn **Enable**
- Trong **Log format**, chọn **Text**
- Trong **Log destination type**, chọn **CloudWatch Logs**
- Trong **Log destination**, chọn **Choose existing log group**
- Trong **Log group name**, chọn tên log đã tạo


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0009-createclusterenable.png)

16. Chọn **Next**.
17. Xem lại và chọn **Create**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/00010-createclusterenable.png)

18. Sau vài phút khởi tạo và kết qủa tạo cluster(cluster mode enable)

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/00011-createclusterenable.png)