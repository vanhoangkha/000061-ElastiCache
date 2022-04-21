---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---


### Xóa một cluster sử dụng Console

1. Đăng nhập vào  AWS Management Console và mở Amazon ElastiCache console tại https://console.aws.amazon.com/elasticache/.

2. Trong  ElastiCache console dashboard, chọn **Redis clusters**. Danh sách tất cả các cluster đang chạy Redis xuất hiện.

3. Để chọn cluster để xóa, hãy chọn tên của cluster từ danh sách các cluster. Trong trường hợp này, tên của cluster bạn đã tạo ở [3.2: Tạo cluster](../../3.2-Create%20a%20cluster/3.2.1-Use%20console/_index.md) .

4. Đối với **Actions**, hãy chọn **Delete**.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0001-deletecluster.png)

5. Trong màn hình xác nhận **Delete Cluster**, chọn **Delete** để xóa cluster hoặc chọn **Cancel** để giữ cluster.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0002-deletecluster.png)

Nếu bạn chọn **Delete**, trạng thái của cluster sẽ chuyển thành *deleting*.

*Ngay sau khi cluster của bạn không còn được liệt kê trong danh sách các cluster, bạn sẽ ngừng tính phí cho cluster đó.*


### Xóa một cluster sử dụng AWS CLI

Đoạn mã sau sẽ xóa cache cluster **my-cluster**. Trong trường hợp này, hãy thay thế **my-cluster** bằng tên của cụm bạn đã tạo ở [3.2: Tạo cluster](../3.2-Create%20a%20cluster/3.2.2-Use%20AWS%20CLI/_index.md).

```
aws elasticache delete-cache-cluster --cache-cluster-id my-cluster

```
Hành động **`delete-cache-cluster`** CLI chỉ xóa một cache cluster. Để xóa nhiều cache cluster, hãy gọi **`delete-cache-cluster`** từng cache cluster mà bạn muốn xóa. Bạn không cần phải đợi một cache cluster hoàn tất việc xóa trước khi xóa một cache cluster khác.

Đối với Linux, macOS hoặc Unix:

```
aws elasticache delete-cache-cluster \
    --cache-cluster-id my-cluster \
    --region us-east-2

```

Đối với Windows:

```
aws elasticache delete-cache-cluster ^
    --cache-cluster-id my-cluster ^
    --region us-east-2

```