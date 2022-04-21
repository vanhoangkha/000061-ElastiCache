---
title : "Sử dụng Console"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.2.1</b> "
---

#### Tạo một cluster sử dụng Console 

1. Đăng nhập vào AWS Management Console và mở Amazon ElastiCache console tại https://console.aws.amazon.com/elasticache/.

2. Từ danh sách ở góc trên bên phải, chọn AWS Region mà bạn muốn khởi chạy cluster này.

3. Chọn **Redis clusters** từ ngăn điều hướng.

4. Chọn **Create Redis cluster**.
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0001-createcluster.png)

5. Đối với **Choose a cluster creation method**, chọn **Configure and create a new cluster**

6. Đối với **Cluster mode**, chọn **Disabled**

![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0002-createcluster.png)

7. Điền thông tin phần **Cluster info**:
   
- Trong **Name** , hãy nhập tên cho cluster của bạn.

- Trong **Description**, hãy nhập mô tả cho clsuter này.

8. Đối với **Location**, chọn **AWS Cloud**. 

![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0003-createcluster.png)

9. Đối với **Cluster settings**

- **Engine version**: chọn `6.2`
- **Port**: chọn `6379`
- **Parameter groups**: chọn **default.redis6.x**
- **Node type**: chọn `cache.r6g.large`
- **Number of replicas**: chọn `2`
  

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0004-createcluster.png)

10.  Đối với **Subnet group settings**:

- Trong **Subnet groups** chọn **Choose existing subnet group** và chọn subnet group đã tạo ở bước 3.1 Tạo một subnet group

- Trong **Associated subnets**, chọn **Availability Zone** và **Subnet ID**   


   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0005-createcluster.png)

11.   Đối với **Availability Zone placements**, chọn  **Specify Availability Zone** 
12.   Chọn **Next**

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0006-createcluster.png)

13.  Đối với **Advanced settings**:

- **Selected security groups**:  chọn security group 

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0007-createcluster.png)

- Trong **Backup**, chọn **Enable automatic backups**
    - Backup retention period: chọn 1
    - Backup window: No preference
  
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0008-createcluster.png)

- Trong **Maintenance**:
    - Maintenance window: chọn **No preference**
    - Topic for Amazon SNS notification: chọn Amazon Resource Name (ARN) đã có
  
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0009-createcluster.png)

- Trong **Logs**:
  - Slow logs: Chọn **Enable**
  - Log format: chọn **Text**
  - Log destination type: chọn **CloudWatch Logs**
  - Log destination: chọn **Choose existing log group**
  - Log group name: chọn log group name

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00010-createcluster.png)

14.  Xem lại và chọn **Create**

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00011-createcluster.png)

15.  Đợi vài phút khởi tạo và kết quả sau khi tạo cluster
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00012-createcluster.png)