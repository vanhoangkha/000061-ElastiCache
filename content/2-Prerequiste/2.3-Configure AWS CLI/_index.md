---
title : "Configure AWS CLI"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

The AWS Command Line Interface (AWS CLI) is an open source tool that allows you to interact with AWS services using commands in your command line shell. With minimal configuration, the AWS CLI allows you to start running functional deployment commands equivalent to that provided by the browser-based AWS Management Console from the command prompt in your terminal program :

**Linux shell** - Use popular shell programs such as bash, zsh, and tcsh to run commands in Linux or macOS.

**Windows command line** - On Windows, run the command at the Windows command prompt or in PowerShell.

**Remotely** - Run commands on Amazon Elastic Compute Cloud (Amazon EC2) through a remote terminal program such as PuTTY or SSH, or with AWS Systems Manager.

AWS Command Line Interface (AWS CLI) configuration steps:

1. Type **`aws configure`** at the Windows Command Prompt, then press Enter .

2. AWS CLI outputs lines of text, entering the following information:
   
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: ENTER
```

*Illustrating images:*
![ConfigureAWSCLI!](/images/2-Prerequiste/2.3-ConfigureAWSCLI/0001-configureawscli.png)