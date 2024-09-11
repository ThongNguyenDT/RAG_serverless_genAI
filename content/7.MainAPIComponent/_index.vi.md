---
title: "Xây dưng API xử lý dữ liệu người dùng"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

Trong phần này, chúng ta sẽ cùng nhau thiết lập hệ thống backend serverless để xử lý các công việc dưới nền.

Cụ thể, chúng ta sẽ thực hiện cài đặt 2 dịch vụ: **API Gateway** và **Lambda** cho các tác vụ xử lý chính.

#### Các bước cài đặt bao gồm:

1. [Thiết lập WebSocket với API Gateway](7.1.WebsocketAPI/)
2. [Xử lý API route vs Lambda](7.2.LambdaHandler/)
3. [Xác thực API bằng Lambda](7.3.lambdaAuth/)
4. [Test API trên giao diện](7.4.APIonUITest/)