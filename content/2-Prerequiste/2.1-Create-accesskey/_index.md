---
title : "Generate AWS Access Key"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### **Generate access keys for IAM users**

1. Sign in to the AWS Management Console and open the IAM console at [IAM console](https://console.aws.amazon.com/iam/).


![Createaccesskey](/images/2-Prerequiste/2.1-Create-accesskey/0001-createaccesskey.png)

2. In the navigation bar, select **Users**.

3. Select the name of the user whose access key you want to create, and then select the **Security credentials** tab.

![Createaccesskey](/images/2-Prerequiste/2.1-Create-accesskey/0002-createaccesskey.png)

4. In the **Access keys** section, select **Create access key**.

![Createaccesskey](/images/2-Prerequiste/2.1-Create-accesskey/0003-createaccesskey.png)

5. To view the new access key, select **Show**. Your login information should look like this:
   
```
Access key ID: AKIAIOSFODNN7EXAMPLE
Secret access key: wJalrXUtnFEMI / K7MDENG / bPxRfiCYEXAMPLEKEY``
```

6. To download the key pair, select **Download .csv file**.

7. After you download the **.csv** file, select **Close**

![Createaccesskey](/images/2-Prerequiste/2.1-Create-accesskey/0004-createaccesskey.png)