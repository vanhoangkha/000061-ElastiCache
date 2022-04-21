---
title : "Sử dụng Console"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1.1 </b> "
---

#### Tạo subnet group sử dụng Console 

1. Đăng nhập vào AWS Management Console và mở ElastiCache console tại https://console.aws.amazon.com/elasticache/.


![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0001-createasubnetgroup.png) 


2. Trong danh sách điều hướng, chọn **Subnet Groups**.

3. Chọn **Create Subnet Group**.


![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0002-createasubnetgroup.png) 


4. Trong trình hướng dẫn **Create Subnet Group**, hãy thực hiện như sau. Khi tất cả các cài đặt như bạn muốn, hãy chọn **Create** .

- Trong hộp **Name** , hãy nhập tên cho nhóm mạng con của bạn.

- Trong hộp **Description** , hãy nhập mô tả cho nhóm mạng con của bạn.

- Trong hộp **VPC ID** , chọn Amazon VPC mà bạn đã tạo.

- Trong danh sách **Availability Zone và Subnet ID**, hãy chọn **Availability Zone và Subnet ID** của private subnet của bạn, sau đó chọn **Add**.

![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0003-createasubnetgroup.png) 

5. Subnet group mới của bạn xuất hiện trong danh sách Subnet Groups của bảng điều khiển ElastiCache. Ở cuối cửa sổ, bạn có thể chọn tên subnet group để xem chi tiết, chẳng hạn như tất cả subnets được liên kết với group này.

![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0004-createasubnetgroup.png) 