---
title: " Thiết lập WebSocket với API Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.1. </b> "
---

Để bắt đầu, ta cần truy cập vào dịch vụ API Gateway trên AWS. Đây là nơi bạn có thể quản lý và cấu hình các API của mình một cách dễ dàng.

Bạn có thể truy cập dịch vụ API Gateway tại địa chỉ sau:

[API Gateway Console](https://us-west-2.console.aws.amazon.com/apigateway/home?region=us-west-2)

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image.png)

### WebSocket API

Sau khi đăng nhập vào API Gateway Console, chúng ta sẽ tiến hành tạo một WebSocket API mới. WebSocket API cho phép giao tiếp hai chiều giữa client và server, điều này rất hữu ích cho các ứng dụng cần cập nhật thời gian thực.

Trong giao diện của API Gateway, bạn cần thực hiện các bước sau để tạo WebSocket API:

1. **Tạo WebSocket API**:
   - Nhấn vào nút để bắt đầu quá trình tạo API mới và chọn **WebSocket API**.
   
   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%201.png)

2. **Đặt tên cho WebSocket API**:
   - Bạn sẽ cần đặt một tên cho WebSocket API của mình. Đây là tên mà bạn sẽ sử dụng để nhận diện API này trong hệ thống.
   - Trong mục Route selection expression, bạn điền giá trị `request.body.action`. Điều này cho phép API xác định các hành động từ yêu cầu gửi đến.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%202.png)

3. **Bỏ qua các bước không cần thiết**:
   - Nhấn **Next** để tiếp tục. Bạn có thể bỏ qua các bước thiết lập chi tiết khác nếu không cần thiết cho trường hợp của bạn.

4. **Đặt tên**:
   - Trong bước này, bạn cần đặt tên cho **state** deploy của bạn và nhấn **Next** để tiếp tục.

  ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%203.png)

5. **Hoàn tất việc tạo API**:
   - Cuối cùng, nhấn **Create API** để hoàn tất quá trình tạo WebSocket API của bạn.
   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%204.png)



Sau khi tạo xong, bạn sẽ thấy giao diện quản lý WebSocket API mới được tạo. Giao diện này sẽ cho phép bạn cấu hình và quản lý các route cũng như các phần khác của API.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%205.png)


**Tiếp theo**, bạn cần truy cập vào mục Stage để chuẩn bị cho các bước tiếp theo trong quá trình cấu hình và triển khai WebSocket API.

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%206.png)

