---
title: "Test API trên giao diện"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 7.4. </b> "
---

Cuối cùng ta tiến hành test API trên giao diện 

Thay thế các mục sau trong ***appconfig.json*** bằng những thông tin đã có từ các bước trước:

- `<YOUR WebSocket URL>`
- `<YOUR WebSocket DynamoDB StateTable TableName>`

#### Tại trang [localhost](http://localhost:5173/)

Tại trang chủ, bạn nhấn phím **F12** để mở giao diện **DevTools**, truy cập vào mục **Console** để tiến hành xem log.

Sau khi bảng **connecting to backend** trên giao diện biến mất, nếu bạn thấy đoạn log của bạn có dạng như sau, tức là bạn đã thành công.

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%207.png)
