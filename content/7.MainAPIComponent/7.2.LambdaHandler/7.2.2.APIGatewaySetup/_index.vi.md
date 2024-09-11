---
title: "Xử lý API route vs Lambda"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 7.2.2. </b> "
---


Sau khi đã tạo API WebSocket, chúng ta cần cấu hình các route cho API này.

### Cấu hình Route

#### 1. **Truy cập vào Route**:
   - Trong giao diện API Gateway, chọn API mà bạn đã tạo.
   - Vào mục **Routes** để bắt đầu cấu hình các route.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%207.png)

#### 2. **Khởi tạo Route**:
   - Nhấn vào **Create Route** để bắt đầu tạo một route mới.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%207.png)

#### 3. **Cấu hình Route**:
   - Đặt tên cho route. Ví dụ, bạn phải đặt tên là `$connect` cho route `$connect`.
   - Chọn **Target** để chỉ định nơi API sẽ gửi dữ liệu.
   - Bật **Lambda proxy integration**. Điều này cho phép API gửi toàn bộ thông tin yêu cầu (request) đến hàm Lambda mà bạn đã tạo trước đó.
   - Chọn hàm thực thi. Chọn hàm WebSocket handler đã được tạo trong bước trước.
   - Cuối cùng Nhấn vào **Create Route** để bắt đầu tạo một route mới.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%208.png)

#### 4. **Tạo các Route khác**:
   - Thực hiện các bước tương tự cho các route khác với các tên tương ứng như sau:

     - Route **`$default`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%209.png)

     - Route **`$disconnect`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2010.png)

     - Route **`message`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2011.png)

     - Route **`whoami`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2012.png)

#### 5. **Deploy API**:
   - Sau khi cấu hình tất cả các route, bạn cần deploy lại API để các thay đổi có hiệu lực.
   - Vào mục **Route**, chọn **Deploy API** để tiến hành deploy setting của bạn.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2013.png)

   - Chọn tên stage hiện tại và nhấn **Deploy** để triển khai các thay đổi.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2014.png)
