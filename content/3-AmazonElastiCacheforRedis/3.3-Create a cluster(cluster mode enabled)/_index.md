---
title : "Create cluster(cluster mode enabled)"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3</b> "
---

#### Create a Redis (cluster mode enabled) cluster using ElastiCache console

1. Sign in to the AWS Management Console and open the Amazon ElastiCache console at https://console.aws.amazon.com/elasticache

2. Select **Redis cluster** from the navigation pane.

3. Select **Create Redis cluster**.

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0001-createclusterenable.png)

4. For **Cluster settings**, complete the following options:

- In **Choose a cluster creation method**, select **Configure and create a new cluster**

5. For **Cluster mode**, select **Enabled**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0002-createclusterenable.png)

6. For **Cluster info**, complete the following information:

- In **Name**, enter the name of the cluster you want to create. (Example: **`my-cluster-enable`**)
- In **Description**, enter a description of your cluster. (Example: **`create cluster enable`**)

7. For **Location**, select **AWS Cloud**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0003-createclusterenable.png)

8. For ***Cluster settings**, complete the following options:

- In **Engine version**, select 6.2
- In **Port**, select 6379
- In **Parameter groups**, select **default.redis6.x.cluster.on**
- In **Node type**, select **cache.r6g.large**
- In **Number of shards**, choose 3
- In **Replicas per shard**, choose 2

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0004-createclusterenable.png)

9. For **Subnet group settings**, complete the following:

- In **Subnet groups**, select **Choose existing subnet group**
- Then select the created subnet group 3.1 Create a subnet group
- In **Associated subnets**, select **Availability Zone** and **Subnet ID**


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0005-createclusterenable.png)

10. For **Availability Zone placements**, complete the following:

- In **Slots and keyspaces**, select **Equal distribution**
- In **Availability Zone placements**, select **Specify Availability Zones**

11. Select **Next**


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0006-createclusterenable.png)

12. For **Advanced settings**, complete the following options:

- In **Selected security groups**, select default security group

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0007-createclusterenable.png)

13. For **Backup**, complete the following options:

- Select **Enable automatic backups**
- In **Backup retention period**, select 1
- In **Backup window**, select **No preference**

14. For **Maintenance**, complete the following options:

- In **Maintenance window**, select **No preference**
- In the **Topic for Amazon SNS notification** section, select Amazon Resource Name (ARN)


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0008-createclusterenable.png)

15. For **Logs**, complete the following options:

- In **Slow logs**, select **Enable**
- In **Log format**, select **Text**
- In **Log destination type**, select **CloudWatch Logs**
- In **Log destination**, select **Choose existing log group**
- In **Log group name**, select the created log name


![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/0009-createclusterenable.png)

16. Select **Next**.
17. Review and select **Create**

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/00010-createclusterenable.png)

18. After a few minutes of initialization and cluster creation results (cluster mode enable)

![Create Cluster (cluster mode enable)](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.3-Createcluster(enable)/00011-createclusterenable.png)