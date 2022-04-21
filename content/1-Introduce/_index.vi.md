---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

### Tổng quan

 **Amazon ElastiCache** là một dịch vụ giúp bạn dễ dàng thiết lập, quản lý và mở rộng quy mô lưu trữ dữ liệu trong bộ nhớ phân tán hoặc môi trường bộ nhớ cache. Nó cung cấp giải pháp bộ nhớ đệm hiệu suất cao, có thể mở rộng và tiết kiệm chi phí. Đồng thời giúp loại bỏ sự phức tạp liên quan đến việc triển khai và quản lý môi trường bộ đệm phân tán.

 **ElastiCache for Redis** có nhiều tính năng:
- Tự động phát hiện và phục hồi từ các lỗi node bộ nhớ cache.
- Redis (đã bật chế độ cluster) hỗ trợ phân vùng dữ liệu của bạn lên đến 500 shard.
- Vị trí Availability Zone của các node và cluster linh hoạt giúp tăng khả năng chịu lỗi.
- Tích hợp với các dịch vụ AWS khác như Amazon EC2, Amazon CloudWatch, AWS CloudTrail và Amazon SNS, giúp cung cấp giải pháp lưu vào bộ nhớ đệm trong bộ nhớ được quản lý có hiệu suất cao và bảo mật cao.
- **ElastiCache for Redis** quản lý các bản sao lưu, vá phần mềm, tự động phát hiện lỗi và khôi phục.

### Clusters

- Thành phần cơ bản của ElastiCache cho Redis được gọi là cluster. 

- Một cluster là một tập hợp của một hoặc nhiều node bộ nhớ cache, tất cả đều chạy một instance của phần mềm cache Redis. 

- Khi bạn tạo một cluster, bạn chỉ định engine và instance cho tất cả các node để sử dụng. Các instance ElastiCache dành cho Redis của bạn được thiết kế để có thể truy cập thông qua instance Amazon EC2. Bạn có thể tạo và sửa đổi một cluster bằng cách sử dụng AWS CLI, ElastiCache Redis API hoặc AWS Management console.

- Mỗi cluster ElastiCache for Redis chạy một instance Redis engine. Mỗi instance engine Redis có các tính năng được hỗ trợ riêng. Ngoài ra, mỗi instance engine Redis có một tập hợp các parameter trong một parameter group kiểm soát hành vi của các cluster.

- Khả năng tính toán và dung lượng bộ nhớ của một cluster được xác định bởi instance hoặc node, class của cluster. Bạn có thể chọn loại node ( node type ) đáp ứng tốt nhất nhu cầu của mình. Nếu nhu cầu của bạn thay đổi theo thời gian, bạn có thể thay đổi **node type**. 

- Bạn cũng có thể tận dụng tính năng phân cấp dữ liệu khi xem xét nhu cầu node type của mình. Xếp hạng dữ liệu là một tính năng trong đó một số dữ liệu ít được sử dụng nhất được lưu trữ trên đĩa SSD để giảm thiểu mức sử dụng  bộ nhớ trên các ứng dụng có thể chịu được độ trễ.

Lưu trữ node cluster có hai loại: Standard and memory-optimized. 

- Chúng khác nhau về đặc điểm hiệu suất và giá cả, cho phép bạn điều chỉnh hiệu suất và chi phí lưu trữ theo nhu cầu của mình. 

- Bạn có thể chạy một cluster trên (VPC). Khi bạn sử dụng VPC, bạn có quyền kiểm soát môi trường mạng ảo của mình. Bạn có thể chọn dải địa chỉ IP của riêng mình, tạo  subnet group và định cấu hình danh sách định tuyến và kiểm soát truy cập. ElastiCache quản lý các bản sao lưu, vá phần mềm, tự động phát hiện lỗi và khôi phục.(*Không có thêm chi phí để chạy cluster của bạn trong VPC*).

### ElastiCache nodes

- Node là khối xây dựng nhỏ nhất của việc triển khai ElastiCache. 
- Một node có thể tồn tại ở dạng cô lập hoặc trong mối quan hệ nào đó với các node khác. 
- Node là một đoạn RAM có kích thước cố định, được gắn vào mạng. Mỗi node chạy một instance của engine và instance đã được chọn khi bạn tạo cluster của mình. Nếu cần, bạn có thể scale các node trong một cluster lên hoặc xuống thành một loại instance khác. 
- Mọi node trong một cluster là cùng một kiểu instance và chạy cùng một engine bộ nhớ cache. Mỗi node bộ nhớ cache có tên và cổng Dịch vụ tên miền (DNS) riêng. 

### ElastiCache for Redis shards

- Một Redis shard là một nhóm từ một đến sáu node có liên quan. Một Redis cluster (cluster mode disabled) luôn có một shard.
- Các cluster redis (cluster mode enabled) có thể có tối đa 500 shard, với dữ liệu của bạn được phân vùng trên các shard. 
- Giới hạn node hoặc shard có thể được tăng lên tối đa 500 cho mỗi cluster nếu instance engine Redis là 5.0.6 trở lên.Bạn cần đảm bảo có đủ địa chỉ IP khả dụng để đáp ứng số node gia tăng.
