---
title : "Install AWS CLI"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

{{%notice tip%}}

To update your existing AWS CLI installation on Windows, download a new installer each time you update to overwrite previous versions. AWS CLI is updated regularly. To see when the latest version is released, see the AWS CLI changelog on GitHub.
{{%/notice%}}

1. Download and run the AWS CLI MSI installer for [Windows (64-bit)](https://awscli.amazonaws.com/AWSCLIV2.msi)
   
{{% notice info %}}
Alternatively, you can run the command `**msiexec**` on **Windows Command Promt** to run the MSI installer.
{{%/notice%}}

```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

```

![InstallAWSCLI!](/images/2-Prerequiste/2.2-InstallAWSCLI/0001-installawscli.png)

1. To confirm the installation, open the **Start** menu, search for **`cmd`** to open **Windows Command Promt**, use the command `**aws --version**` .

```
aws --version

```

![InstallAWSCLI!](/images/2-Prerequiste/2.2-InstallAWSCLI/0002-installawscli.png)

{{% notice info %}}
If Windows cannot find the program, you may need to close and reopen the Windows Command Prompt to refresh the path or add the AWS CLI to your path.
{{%/notice%}}