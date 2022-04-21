---
title : "Cluster Mode Disabled"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.5.1 </b> "
---

Nếu một Redis cluster (cluster mode disabled) chỉ có một node, thì endpoint của node được sử dụng cho cả việc đọc và ghi. Nếu một Redis cluster có nhiều node, thì có ba loại endpoint: *primary endpoint, the reader endpoint and the node endpoints.*

Primary endpoint là tên DNS luôn phân giải đến node chính trong cluster. Primary endpoint miễn nhiễm với các thay đổi đối với cluster của bạn, chẳng hạn như promoting a read replica cho vai trò chính. Đối với hoạt động ghi, bạn nên kết nối các ứng dụng của mình với endpoint.

Reader endpoint sẽ chia đều các kết nối đến endpoint giữa tất cả các read replicas trong ElastiCache for Redis cluster. Các yếu tố bổ sung như thời điểm ứng dụng tạo kết nối hoặc cách ứng dụng (tái sử dụng) các kết nối sẽ xác định phân phối lưu lượng. Reader endpoints theo kịp các thay đổi của cluster trong thời gian thực khi các replicas được thêm vào hoặc loại bỏ. Bạn có thể *ElastiCache for Redis cluster’s multiple read replicas* ở các AWS Availability Zones (AZ) khác nhau để đảm bảo tính khả dụng cao của các reader endpoints.

Đối với hoạt động đọc, các ứng dụng cũng có thể kết nối với bất kỳ node nào trong cluster. Không giống như primary endpoint, node endpoints phân giải thành các endpoint cụ thể. Nếu bạn thực hiện thay đổi trong cluster của mình, chẳng hạn như thêm hoặc xóa bản sao, bạn phải cập nhật các node endpoints trong ứng dụng của mình.

### Để tìm  Redis (cluster mode disabled) cluster's endpoints

1. Đăng nhập vào AWS Management Console và mở  ElastiCache console tại https://console.aws.amazon.com/elasticache/.

2. Từ ngăn điều hướng, chọn **Redis clusters**. Màn hình Redis clusters sẽ xuất hiện với danh sách các Redis (cluster mode disabled) và Redis (cluster mode enabled) clusters.

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.1-Rediscustermodedisabledendpointsconsole/0001-connectdisable.png)

3. Để tìm **Primary** và/hoặc **Reader endpoints** của cluster, hãy chọn tên của cluster.

4. Nếu  **Redis (cluster mode disabled) cluster có các replica nodes**, bạn có thể tìm thấy **replica node endpoints** của cluster bằng cách chọn tên của cluster. Màn hình các node xuất hiện với mỗi node trong cluster, primary và replicas, được liệt kê với endpoint của nó.

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.1-Rediscustermodedisabledendpointsconsole/0002-connectdisable.png)

5. Để sao chép một endpoint vào khay nhớ tạm của bạn:

- Mỗi lần một endpoint, tìm rồi đánh dấu endpoint bạn muốn sao chép.

- Bấm chuột phải vào endpoint được đánh dấu, sau đó chọn **Copy** từ trình đơn ngữ cảnh. Endpoint được đánh dấu hiện được sao chép vào khay nhớ tạm của bạn. 

![Connect to the cluster's node](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.5-Connecttotheclusternode/3.5.1-Rediscustermodedisabledendpointsconsole/0003-connectdisable.png)

**In-transit encryption not enabled**

```
clusterName.xxxxxx.nodeId.regionAndAz.cache.amazonaws.com:port
			
redis-01.7abc2d.0001.usw2.cache.amazonaws.com:6379

```

**In-transit encryption enabled**

```
master.clusterName.xxxxxx.regionAndAz.cache.amazonaws.com:port

master.ncit.ameaqx.use1.cache.amazonaws.com:6379

```
