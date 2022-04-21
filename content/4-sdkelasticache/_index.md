---
title : "Using AWS SDK to write and read data on ElastiCache"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### Overview
In this tutorial, you use the AWS SDK for Python (Boto3) to write simple programs that perform the following ElastiCache operations:

- Create ElastiCache cluster (cluster mode disable and cluster mode enable)

- Check if user or user group exists, if not create the user (Redis 6.0 onwards only)

- Connect with ElastiCache

- Perform operations such as set up and get strings, read and write to steam, and publish and subscribe from a Pub/Sub channel.

**Prepare**
- Set up AWS Access Key to use AWS SDK.

- Install Python 3.0 or later. For more information see https://www.python.org/downloads.

### Content

- [Create Cluster](4.1-creating-elasticache-clusters-and-users/)
- [Connect node](4.2-connecting-to-elasticache/)
- [Set and get string](4.3-set-and-get-strings/)
- [Publish and subscriber](4.5-publish-and-subscriber/)
- [Write and read from a stream](4.6-write-and-read-from-a-stream/)