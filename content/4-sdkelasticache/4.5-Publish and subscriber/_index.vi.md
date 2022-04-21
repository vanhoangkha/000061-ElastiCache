---
title : "Publish (write) and subscribe (read)"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

1. Tạo một file python có tên PubAndSub.py
2. Sao chép chương trình sau và dán vào file có tên PubAndSub.py.

```
import logging
import time

def handlerFunction(message):
    """Prints message got from PubSub channel to the log output

    Return None
    :param message: message to log
    """
    logging.info(message)

logging.basicConfig(level=logging.INFO)
redis = Redis(host="redis202104053.tihewd.ng.0001.use1.cache.amazonaws.com", port=6379, decode_responses=True)


# Creates the subscriber connection on "mychannel"
subscriber = redis.pubsub()
subscriber.subscribe(**{'mychannel': handlerFunction})

# Creates a new thread to watch for messages while the main process continues with its routines
thread = subscriber.run_in_thread(sleep_time=0.01)

# Creates publisher connection on "mychannel"
redis.publish('mychannel', 'My message')

# Publishes several messages. Subscriber thread will read and print on log.
while True:
    redis.publish('mychannel',time.ctime(time.time()))
    time.sleep(1)

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python PubAndSub.py

```
Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file PubAndSub.py"

```
