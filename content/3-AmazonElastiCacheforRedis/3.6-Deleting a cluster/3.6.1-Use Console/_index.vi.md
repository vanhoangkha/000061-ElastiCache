---
title : "Use Console"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.6.1 </b> "
---

Quy trình sau đây xóa một cluster đơn lẻ khỏi triển khai của bạn. Để xóa nhiều cluster, hãy lặp lại quy trình cho từng cluster mà bạn muốn xóa. Bạn không cần phải đợi một cluster hoàn thành xóa trước khi bắt đầu quy trình xóa một cluster khác.

**Để xóa một cluster**

1. Đăng nhập vào  AWS Management Console và mở Amazon ElastiCache console tại https://console.aws.amazon.com/elasticache/.

2. Trong  ElastiCache console dashboard, chọn **Redis clusters**. Danh sách tất cả các cluster đang chạy Redis xuất hiện.

3. Để chọn cluster để xóa, hãy chọn tên của cluster từ danh sách các cluster. Trong trường hợp này, tên của cluster bạn đã tạo ở [3.2: Tạo cluster](../../3.2-Create%20a%20cluster/3.2.1-Use%20console/_index.md) .

4. Đối với **Actions**, hãy chọn **Delete**.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0001-deletecluster.png)

5. Trong màn hình xác nhận **Delete Cluster**, chọn **Delete** để xóa cluster hoặc chọn **Cancel** để giữ cluster.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0002-deletecluster.png)

Nếu bạn chọn **Delete**, trạng thái của cluster sẽ chuyển thành *deleting*.

*Ngay sau khi cluster của bạn không còn được liệt kê trong danh sách các cluster, bạn sẽ ngừng tính phí cho cluster đó.*

