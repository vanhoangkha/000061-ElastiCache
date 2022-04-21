---
title : "Tạo cluster (cluster mode disabled)"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

### Tổng quan

- Trước khi tạo một cluster để sử dụng trong môi trường production, bạn cần xem xét cách bạn sẽ định cấu hình cluster để đáp ứng nhu cầu của mình. Đối với bài lab này, bạn sẽ tạo một cluster với **cluster mode disabled** và bạn sẽ áp dụng các giá trị cấu hình mặc định.

- Cluster bạn tạo sẽ hoạt động và không chạy trong sandbox. Bạn sẽ phải chịu phí sử dụng** ElastiCache standard** cho ví dụ cho đến khi bạn xóa nó. Tổng số phí sẽ tối thiểu (thường ít hơn một đô la) nếu bạn hoàn thành bài tập được mô tả ở đây trong một lần và xóa cluster của bạn khi bạn hoàn thành. 

- Cluster của bạn được khởi chạy trong một Virtual Private Cloud (VPC) dựa trên dịch vụ Amazon VPC.

### Nội dung

- [3.2.1 Tạo một cluster sử dụng Console](3.2.1-use-console/)
- [3.2.2 Tạo một cluster sử dụng AWS CLI](3.2.2-use-aws-cli/)