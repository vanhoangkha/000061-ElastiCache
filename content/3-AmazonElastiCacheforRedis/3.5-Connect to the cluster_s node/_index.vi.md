---
title : "Kết nối với node của cluster"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

#### Tổng quan 

Ứng dụng của bạn kết nối với cluster của bạn bằng cách sử dụng các endpoint. endpoint là địa chỉ duy nhất của node hoặc cluster.

- Redis standalone node, sử dụng endpoint của node cho cả hoạt động đọc và ghi.
- Redis (cluster mode disabled) clusters, sử dụng primary endpoint cho tất cả các hoạt động ghi. Sử dụng reader endpoint để chia đều các kết nối đến endpoint giữa tất cả các read replica. Sử dụng các endpoint node riêng lẻ cho các hoạt động đọc (Trong API / CLI, chúng được gọi là reader endpoint).
- Redis (cluster mode enabled) clusters, sử dụng endpoint cấu hình của cluster cho tất cả các hoạt động hỗ trợ các lệnh (cluster mode enable). Bạn phải sử dụng một ứng dụng khách hỗ trợ Redis Cluster (Redis 3.2). Bạn vẫn có thể đọc từ các endpoint node riêng lẻ (Trong API / CLI, chúng được gọi là reader endpoint).

#### Nội dung

- [Cluster Mode Disable](3.5.1-redis-cluster-mode-disabled-clusters-endpoints-console/)
- [Cluster Mode Enable](3.5.2-redis-cluster-mode-enabled-cluster-console/)
- [Enpoint sử dụng AWS CLI](3.5.3-finding-endpoints-aws-cli/)