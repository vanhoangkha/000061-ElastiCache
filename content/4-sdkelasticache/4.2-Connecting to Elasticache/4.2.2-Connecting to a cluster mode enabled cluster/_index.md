---
title : "Connecting to a cluster (mode enabled cluster)"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2.2 </b> "
---

### Connect to a cluster (cluster mode enable)

1. Create a python file named ConnectClusterModeEnabled.py.
2. Copy the following program and paste it into the file named ConnectClusterModeEnabled.py.

```
from rediscluster import RedisCluster
import logging

logging.basicConfig(level=logging.INFO)
redis = RedisCluster(startup_nodes=[{"host": "xxx.yyy.clustercfg.zzz1.cache.amazonaws.com","port": "6379"}], decode_responses=True,skip_full_coverage_check=True)

if redis.ping():
     logging.info("Connected to Redis")

```

3. To run the program, enter the following command:

```
python ConnectClusterModeEnabled.py

```

If the program cannot run, use the following command:

```
python "ConnectClusterModeEnabled.py file path"

```