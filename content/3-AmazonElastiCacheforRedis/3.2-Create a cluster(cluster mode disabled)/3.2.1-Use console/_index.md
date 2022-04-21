---
title : "Use Console"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.2.1</b> "
---

#### Create a cluster using Console

1. Sign in to the AWS Management Console and open the Amazon ElastiCache console at https://console.aws.amazon.com/elasticache/.

2. From the list in the upper right corner, select the AWS Region in which you want to launch this cluster.

3. Select **Redis clusters** from the navigation pane.

4. Select **Create Redis cluster**.
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0001-createcluster.png)

5. For **Choose a cluster creation method**, select **Configure and create a new cluster**

6. For **Cluster mode**, select **Disabled**

![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0002-createcluster.png)

7. Fill in **Cluster info** section:
   
- In **Name** , enter a name for your cluster.

- In **Description**, enter a description for this clsuter.

8. For **Location**, select **AWS Cloud**.

![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0003-createcluster.png)

9. For **Cluster settings**

- **Engine version**: select `6.2`
- **Port**: select `6379`
- **Parameter groups**: select **default.redis6.x**
- **Node type**: select `cache.r6g.large`
- **Number of replicas**: select `2`
  

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0004-createcluster.png)

10. For **Subnet group settings**:

- In **Subnet groups** select **Choose existing subnet group** and select the subnet group created in step 3.1 Create a subnet group

- In **Associated subnets**, select **Availability Zone** and **Subnet ID**


   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0005-createcluster.png)

11. For **Availability Zone placements**, select **Specify Availability Zone**
12. Select **Next**

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0006-createcluster.png)

13. For **Advanced settings**:

- **Selected security groups**: select security group

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0007-createcluster.png)

- In **Backup**, select **Enable automatic backups**
    - Backup retention period: choose 1
    - Backup window: No preference
  
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0008-createcluster.png)

- In **Maintenance**:
    - Maintenance window: select **No preference**
    - Topic for Amazon SNS notification: select existing Amazon Resource Name (ARN)
  
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/0009-createcluster.png)

- In **Logs**:
  - Slow logs: Select **Enable**
  - Log format: select **Text**
  - Log destination type: select **CloudWatch Logs**
  - Log destination: select **Choose existing log group**
  - Log group name: select log group name

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00010-createcluster.png)

14. Review and select **Create**

   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00011-createcluster.png)

15. Wait a few minutes for initialization and results after creating the cluster
   
![CreateCluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.2-Createcluster(disable)/3.2.1-Useconsole/00012-createcluster.png)