---
title : "Set and Get a hash with multiple items"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

1. Tạo một file python có tên SetAndGetHash.py
2. Sao chép chương trình sau và dán vào file có tên SetAndGetHash.py.

```
import logging
import time

logging.basicConfig(level=logging.INFO,format='%(asctime)s: %(message)s')

keyName='mykey'
keyValues={'datetime': time.ctime(time.time()), 'epochtime': time.time()}

# Set the hash 'mykey' with the current date and time in human readable format (datetime field) and epoch number (epochtime field). 
redis.hset(keyName, mapping=keyValues)

# Set the key to expire and removed from cache in 60 seconds.
redis.expire(keyName, 60)

# Sleep just for better illustration of TTL (expiration) value
time.sleep(5)

# Retrieves all the fields and current TTL
keyValues=redis.hgetall(keyName)
keyTTL=redis.ttl(keyName)

logging.info("Key {} was set at {} and has {} seconds until expired".format(keyName, keyValues, keyTTL))

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python SetAndGetHash.py

```
Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file SetAndGetHash.py"

```
