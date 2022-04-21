---
title : "Set and Get strings"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---
### Set and Get strings

1. Create a python file named ConnectClusterModeEnabled.py.
2. Copy the following program and paste it into the file named ConnectClusterModeEnabled.py.

```
import time
import logging
logging.basicConfig(level=logging.INFO,format='%(asctime)s: %(message)s')

keyName='mykey'
currTime=time.ctime(time.time())

# Set the key 'mykey' with the current date and time as value.
# The Key will expire and removed from cache in 60 seconds.
redis.set(keyName, currTime, ex=60)

# Sleep just for better illustration of TTL (expiration) value
time.sleep(5)

# Retrieve the key value and current TTL
keyValue=redis.get(keyName)
keyTTL=redis.ttl(keyName)

logging.info("Key {} was set at {} and has {} seconds until expired".format(keyName, keyValue, keyTTL))

```

3. To run the program, enter the following command:

```
python SetAndGetStrings.py

```

If the program cannot run, use the following command:

```
python "SetAndGetStrings.py file path"

```