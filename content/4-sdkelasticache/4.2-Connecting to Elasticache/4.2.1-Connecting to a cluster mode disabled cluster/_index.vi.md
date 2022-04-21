---
title : "Kết nối tới một cluster (mode disabled cluster)"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.2.1 </b> "
---

### Kết nối đến một cluster (cluster mode disable)

1. Tạo một file python có tên ConnectClusterModeDisabled.py.

2. Sao chép chương trình sau và dán vào file có tên ConnectClusterModeDisabled.py.

```
from redis import Redis
import logging

logging.basicConfig(level=logging.INFO)
redis = Redis(host='primary.xxx.yyyyyy.zzz1.cache.amazonaws.com', port=6379, decode_responses=True, ssl=True, username='myuser', password='MyPassword0123456789')

if redis.ping():
    logging.info("Connected to Redis")

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python ConnectClusterModeDisabled.py

```

Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file ConnectClusterModeDisabled.py"

```