---
title : "Connecting to a cluster (mode disabled cluster)"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.2.1 </b> "
---

### Connect to a cluster (cluster mode disable)

1. Create a python file named ConnectClusterModeDisabled.py.

2. Copy the following program and paste it into the file named ConnectClusterModeDisabled.py.

```
from redis import Redis
import logging

logging.basicConfig(level=logging.INFO)
redis = Redis(host='primary.xxx.yyyyyy.zzz1.cache.amazonaws.com', port=6379, decode_responses=True, ssl=True, username='myuser', password='MyPassword0123456789')

if redis.ping():
     logging.info("Connected to Redis")

```

3. To run the program, enter the following command:

```
python ConnectClusterModeDisabled.py

```

If the program cannot run, use the following command:

```
python "ConnectClusterModeDisabled.py file path"

```