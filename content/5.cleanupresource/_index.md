---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---


### Delete a cluster using Console

1. Sign in to the AWS Management Console and open the Amazon ElastiCache console at https://console.aws.amazon.com/elasticache/.

2. In the ElastiCache console dashboard, select **Redis clusters**. A list of all clusters running Redis appears.

3. To select the cluster to delete, select the name of the cluster from the list of clusters. In this case, the name of the cluster you created in [3.2: Create cluster](../../3.2-Create%20a%20cluster/3.2.1-Use%20console/_index.md) .

4. For **Actions**, select **Delete**.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0001-deletecluster.png)

5. In the **Delete Cluster** confirmation screen, select **Delete** to delete the cluster or select **Cancel** to keep the cluster.

![Delete cluster](/images/3-GettingstartedwithAmazonElastiCacheforRedis/3.6-Deletecluster/3.6.1-Usesonsole/0002-deletecluster.png)

If you select **Delete**, the cluster's state will change to *deleting*.

*As soon as your cluster is no longer listed in the list of clusters, you will stop charging for that cluster.*


### Delete a cluster using the AWS CLI

The following code will clear the cluster cache **my-cluster**. In this case, replace **my-cluster** with the name of the cluster you created at [3.2: Create cluster](../3.2-Create%20a%20cluster/3.2.2-Use%20AWS%20CLI /_index.md).

```
aws elasticache delete-cache-cluster --cache-cluster-id my-cluster

```
The **`delete-cache-cluster`** CLI action deletes only one cache cluster. To delete multiple cache clusters, call **`delete-cache-cluster`** each cache cluster that you want to delete. You don't have to wait for one cache cluster to finish deleting before deleting another cache cluster.

For Linux, macOS or Unix:

```
aws elasticache delete-cache-cluster \
    --cache-cluster-id my-cluster \
    --region us-east-2

```

For Windows:

```
aws elasticache delete-cache-cluster ^
    --cache-cluster-id my-cluster ^
    --region us-east-2

```