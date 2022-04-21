---
title : "Sử dụng AWS SDK để ghi và đọc dữ liệu trên ElastiCache"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Tổng quan
Trong hướng dẫn này, bạn sử dụng AWS SDK cho Python (Boto3) để viết các chương trình đơn giản nhằm thực hiện các hoạt động ElastiCache sau:

- Tạo cluster ElastiCache (cluster mode disable và cluster mode enable)

- Kiểm tra xem người dùng hoặc nhóm người dùng có tồn tại hay không, nếu không thì tạo  (chỉ Redis 6.0 trở đi)

- Kết nối với ElastiCache

- Thực hiện các thao tác như thiết lập và lấy chuỗi, đọc và ghi vào hơi nước cũng như xuất bản và đăng ký từ kênh Pub / Sub.

**Chuẩn bị**
- Thiết lập AWS Access Key để sử dụng AWS SDK.

- Cài đặt Python 3.0 trở lên. Để biết thêm thông tin, hãy xem https://www.python.org/downloads. 

### Nội dung 

- [Tạo cluster](4.1-creating-elasticache-clusters-and-users/)
- [Kết nối node](4.2-connecting-to-elasticache/)
- [Set and get string](4.3-set-and-get-strings/)
- [Publish and subscriber](4.5-publish-and-subscriber/)
- [Write and read from a stream](4.6-write-and-read-from-a-stream/)
