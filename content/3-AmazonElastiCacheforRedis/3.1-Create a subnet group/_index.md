---
title : "Create subnet group"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

{{% notice info %}}
Before you create a cluster, you must first create a subnet group.
{{%/notice%}}

### Overview

- A cache subnet group is a collection of subnet groups that you may want to specify for your cache clusters in the VPC.
- When launching a cache cluster in VPC, you need to select a cache subnet group. ElastiCache then uses that cache subnet group to assign IP addresses in that subnet group to each cache node in the cluster.
- When you create a new subnet group, note the number of available IP addresses. If the subnet group has very few available IP addresses, you may be limited in the number of nodes you can add to the cluster. To get around this, you can assign multiple subnets to a subnet group so that you have a sufficient number of IP addresses in the Availability Zone of the cluster. Thereby you can add more nodes to your cluster.

### Content

- [3.1.1 Create a subnet group using Console](3.1.1-useconsole/)
- [3.1.2 Create a subnet group using AWS CLI](3.1.2-useawscli/)