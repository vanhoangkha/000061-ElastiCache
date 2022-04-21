---
title : "Cài đặt AWS CLI"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
{{%notice tip%}}

Để cập nhật cài đặt AWS CLI hiện tại của bạn trên Windows, hãy tải xuống trình cài đặt mới mỗi khi bạn cập nhật để ghi đè lên các phiên bản trước. AWS CLI được cập nhật thường xuyên. Để biết khi nào phiên bản mới nhất được phát hành, hãy xem [bảng thay đổi AWS CLI](https://github.com/aws/aws-cli/blob/v2/CHANGELOG.rst) trên GitHub .

{{%/notice%}}

1. Tải xuống và chạy trình cài đặt AWS CLI MSI dành cho [Windows (64-bit)](https://awscli.amazonaws.com/AWSCLIV2.msi)
   
{{% notice info %}}
Ngoài ra, bạn có thể chạy lệnh `**msiexec**`  trên **Windows Command Promt** để chạy trình cài đặt MSI.
{{%/notice%}}

```
msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

```

![InstallAWSCLI!](/images/2-Prerequiste/2.2-InstallAWSCLI/0001-installawscli.png) 

1. Để xác nhận cài đặt, hãy mở menu **Start** , tìm kiếm **`cmd`** để mở **Windows Command Promt**, hãy sử dụng lệnh `**aws --version**`.

```
aws --version

```

![InstallAWSCLI!](/images/2-Prerequiste/2.2-InstallAWSCLI/0002-installawscli.png) 

{{% notice info %}}
Nếu Windows không thể tìm thấy chương trình, bạn có thể cần phải đóng và mở lại Windows Command Promt để làm mới đường dẫn hoặc thêm AWS CLI vào đường dẫn của bạn .
{{%/notice%}}