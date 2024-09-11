---
title: "Xác thực API bằng Lambda"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 7.3. </b> "
---

Trong phần này ta sẽ cùng nhau cấu hình **API Gateway Authorizer** cho WebSocket API đã tạo trước đó. Việc thiết lập Authorizer giúp bảo mật và kiểm soát quyền truy cập vào hệ thống API, cho phép xác thực người dùng thông qua các cơ chế an toàn như **Lambda Authorizer**. 

#### Để setup **API Gateway Authorizer** ta cần thuự hiện các bước sau:
1. [Thiết lập Lambda Function](7.3.1.LambdaFunction/)
2. [Thiết lập WebSocket Authorizer trong API Gateway](7.3.2.APIGatewaySetup/)

Cấu hình Authorizer là bước quan trọng để nâng cao tính bảo mật cho hệ thống của bạn. Bạn có thể tham khảo tài liệu chi tiết về API Gateway và Lambda Authorizer để hiểu rõ hơn cách thiết lập các thành phần này một cách tối ưu.