---
title : "Cấp quyền truy cập vào cluster"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.4 </b> "
---

{{% notice info %}}
Tất cả các cluster ElastiCache được thiết kế để có thể truy cập từ phiên bản Amazon EC2. Tình huống phổ biến nhất là truy cập một cluster ElastiCache từ một phiên bản Amazon EC2 trong cùng Amazon Virtual Private Cloud  (Amazon VPC), đây sẽ là trường hợp cho bài lab này.
{{%/notice%}}

Theo mặc định, quyền truy cập mạng vào cluster của bạn bị giới hạn ở tài khoản người dùng đã được sử dụng để tạo nó. Trước khi bạn có thể kết nối với một cluster từ phiên bản EC2, bạn phải cho phép phiên bản EC2 truy cập vào cluster. Các bước bắt buộc phụ thuộc vào việc bạn khởi chạy cluster của mình vào EC2-VPC hay EC2-Classic.

Trường hợp sử dụng phổ biến nhất là khi một ứng dụng được triển khai trên phiên bản EC2 cần kết nối với một cluster trong cùng một VPC. Cách đơn giản nhất để quản lý quyền truy cập giữa các phiên bản và cluster EC2 trong cùng một VPC là thực hiện như sau:

Tạo Security Group VPC cho cluster của bạn. Security Group này có thể được sử dụng để hạn chế quyền truy cập vào các phiên bản cluster. Ví dụ: bạn có thể tạo quy tắc tùy chỉnh cho Security Group này cho phép truy cập TCP bằng cách sử dụng cổng mà bạn đã chỉ định cho cluster khi bạn tạo nó và một địa chỉ IP bạn sẽ sử dụng để truy cập cluster.

Cổng mặc định cho các cluster Redis và replicas group là 6379.


Để tạo quy tắc trong Security Group VPC cho phép kết nối từ một Security Group khác

1. Đăng nhập vào AWS Management Console và mở Amazon VPC console tại https://console.aws.amazon.com/vpc.

2. Trong ngăn dẫn hướng, chọn **Security Groups**.

3. Chọn hoặc tạo một **security group** mà bạn sẽ sử dụng cho các **Cluster instances**. 
4. Trong **Inbound Rules**, chọn **Edit Inbound Rules** 

![Authorize access to the cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.4-Authorizeaccesstothecluster/0001-authorizeaccesstothecluster.png)
5. sau đó chọn **Add Rule**. Security group này sẽ cho phép truy cập vào các thành viên của security group khác.

![Authorize access to the cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.4-Authorizeaccesstothecluster/0002-authorizeaccesstothecluster.png)
6. Đối với **Type**, **chọn Custom TCP Rule**

- Đối với **Port Range**, chỉ định cổng bạn đã sử dụng khi tạo cluster của mình.

- Cổng mặc định cho Redis clusters and replication groups là **6379**.

- Trong hộp **Source**, bắt đầu nhập ID của security group. Từ danh sách, hãy chọn security group bạn sẽ sử dụng cho các Amazon EC2 instances của mình.

7. Chọn **Save rule** khi bạn hoàn thành.

![Authorize access to the cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.4-Authorizeaccesstothecluster/0003-authorizeaccesstothecluster.png)

