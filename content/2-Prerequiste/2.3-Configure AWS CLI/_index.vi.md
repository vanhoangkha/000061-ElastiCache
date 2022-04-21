---
title : "Cấu hình AWS CLI"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

Giao diện dòng lệnh AWS (AWS CLI) là một công cụ mã nguồn mở cho phép bạn tương tác với các dịch vụ AWS bằng cách sử dụng các lệnh trong trình bao dòng lệnh của bạn. Với cấu hình tối thiểu, AWS CLI cho phép bạn bắt đầu chạy các lệnh triển khai chức năng tương đương với chức năng được cung cấp bởi Bảng điều khiển quản lý AWS dựa trên trình duyệt từ dấu nhắc lệnh trong chương trình đầu cuối của bạn:

**Linux shell** - Sử dụng các chương trình shell phổ biến như bash, zsh, và tcsh để chạy các lệnh trong Linux hoặc macOS.

**Windows command line** - Trên Windows, chạy lệnh tại dấu nhắc lệnh Windows hoặc trong PowerShell.

**Remotely** - Chạy lệnh trên Amazon Elastic Compute Cloud (Amazon EC2) thông qua chương trình đầu cuối từ xa như PuTTY hoặc SSH hoặc với AWS Systems Manager.

Các bước cấu hình Giao diện dòng lệnh AWS (AWS CLI):

1. Nhập dòng lệnh **`aws configure`** tại Windows Command Promt, sau đó nhấn Enter .

2. AWS CLI xuất ra các dòng văn bản, nhập các thông tin sau:
   
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: ENTER
```

*Hình ảnh minh họa:*
![ConfigureAWSCLI!](/images/2-Prerequiste/2.3-ConfigureAWSCLI/0001-configureawscli.png) 
