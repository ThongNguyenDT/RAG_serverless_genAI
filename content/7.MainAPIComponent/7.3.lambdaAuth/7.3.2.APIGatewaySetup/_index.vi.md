---
title: "Thiết lập WebSocket Authorizer trong API Gateway"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 7.3.2. </b> "
---
Trong phần này, chúng ta sẽ thiết lập **WebSocket Authorizer** để bảo mật việc kết nối và xác thực người dùng qua API Gateway.

1. **Truy cập WebSocket API**:
   - Sau khi tạo xong **WebSocket API**, truy cập vào phần **Authorizers** để bắt đầu cài đặt Authorizer cho WebSocket.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2015.png)
   

2. **Tạo Authorizer Mới**:
   - Click vào nút **Create Authorizer** để bắt đầu tạo một **Authorizer** mới cho WebSocket.
   - Khi hộp thoại hiện ra, điền các thông tin cần thiết như sau:
   
     - **Đặt tên Authorizer**: Bạn có thể đặt tên tùy ý, ví dụ:
     
     ```text
     WebsocketAuthorizer
     ```

     - **Chọn vùng (Region)** và **Hàm Lambda Authorizer** đã tạo trước đó để làm công cụ xác thực.
   
   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2016.png)

3. **Cấu hình Source Type**:
   - Sau khi thiết lập Authorizer, bạn cần cài đặt **Identity Source Type** như trong hình để chỉ định nguồn xác thực (ví dụ: header hoặc request).

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2017.png)

4. **Hoàn tất thiết lập**:
   - Nhấn nút **Tạo** để hoàn tất quy trình. Sau khi tạo thành công, bạn có thể sử dụng **Authorizer** này để bảo vệ và kiểm tra kết nối cho WebSocket API của mình.

Như vậy, ta đã hoàn tất các bước thiết lập **WebSocket Authorizer**.