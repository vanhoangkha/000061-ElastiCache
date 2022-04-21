---
title : "Kết nối tới một cluster (mode enabled cluster)"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2.2 </b> "
---

### Kết nối đến một cluster (cluster mode enable)

1. Tạo một file python có tên ConnectClusterModeEnabled.py.
2. Sao chép chương trình sau và dán vào file có tên ConnectClusterModeEnabled.py.

```
from rediscluster import RedisCluster
import logging

logging.basicConfig(level=logging.INFO)
redis = RedisCluster(startup_nodes=[{"host": "xxx.yyy.clustercfg.zzz1.cache.amazonaws.com","port": "6379"}], decode_responses=True,skip_full_coverage_check=True)

if redis.ping():
    logging.info("Connected to Redis")

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python ConnectClusterModeEnabled.py

```

Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file ConnectClusterModeEnabled.py"

```
