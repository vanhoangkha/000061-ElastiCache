---
title : "Use AWS CLI"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.6.2 </b> "
---


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