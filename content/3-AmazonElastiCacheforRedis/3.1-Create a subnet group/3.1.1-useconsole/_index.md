---
title : "Use Console"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1.1 </b> "
---

#### Create subnet group using Console

1. Sign in to the AWS Management Console and open the ElastiCache console at https://console.aws.amazon.com/elasticache/.


![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0001-createasubnetgroup.png)


2. In the navigation list, select **Subnet Groups**.

3. Select **Create Subnet Group**.


![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0002-createasubnetgroup.png)


4. In the **Create Subnet Group** wizard, do the following. When all settings are as you want, select **Create** .

- In the **Name** box, enter a name for your subnet group.

- In the **Description** box, enter a description for your subnet group.

- In the **VPC ID** box, select the Amazon VPC you created.

- In the **Availability Zone and Subnet ID** list, select **Availability Zone and Subnet ID** of your private subnet, then select **Add**.

![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0003-createasubnetgroup.png)

5. Your new subnet group appears in the Subnet Groups list of the ElastiCache dashboard. At the bottom of the window, you can select the subnet group name to see details, such as all the subnets associated with this group.

![Createasubnetgroup](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.1-Createasubnetgroup/3.1.1-Useconsole/0004-createasubnetgroup.png)