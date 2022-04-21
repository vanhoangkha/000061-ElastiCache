---
title : "Tạo subnet group"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

{{% notice info %}}
Trước khi bạn tạo một cluster, trước tiên bạn phải tạo một subnet group.
{{%/notice%}}

### Tổng quan 

- Một cache subnet group là một tập hợp các subnet group mà bạn có thể muốn chỉ định cho cache clusters của mình trong VPC. 
- Khi khởi chạy một cache cluster trong VPC, bạn cần chọn một cache subnet group. Sau đó, ElastiCache sử dụng cache subnet group  đó để gán địa chỉ IP trong  subnet group đó cho mỗi cache node trong cluster.
- Khi bạn tạo một subnet group mới, hãy lưu ý số lượng địa chỉ IP khả dụng. Nếu subnet group có rất ít địa chỉ IP khả dụng, bạn có thể bị hạn chế về số lượng node khác mà bạn có thể thêm vào cluster. Để giải quyết vấn đề này, bạn có thể chỉ định nhiều subnet cho một subnet group để bạn có đủ số lượng địa chỉ IP trong Availability Zone của cluster. Qua đó bạn có thể thêm nhiều node hơn vào cluster của mình.

### Nội dung

- [3.1.1 Tạo một subnet group sử dụng Console](3.1.1-useconsole/)
- [3.1.2 Tạo một subnet group sử dụng AWS CLI](3.1.2-useawscli/)
