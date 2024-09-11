---
title: "Thiết lập Lambda Function"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.3.1. </b> "
---

Trong dịch vụ AWS Lambda, chúng ta sẽ tiến hành tạo một function mới để xác thực ứng dụng.
1. **Truy cập dịch vụ Lambda**:
   - Đầu tiên, truy cập vào dịch vụ **Lambda** trên AWS và chọn tùy chọn để tạo một function mới.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2011.png)

2. **Tạo Lambda Function**:
   - Tại giao diện tạo function, bạn cần nhập tên cho Lambda function của mình.
   - Chọn **Runtime** là Node.js 20, đây là phiên bản JavaScript hỗ trợ thực thi các thao tác xử lý WebSocket và các yêu cầu liên quan.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2012.png)

   - Sau khi đặt tên và chọn runtime, nhấn **Create Function** để tiến hành tạo mới.

3. **Tải Source Code**:
   -Bạn có thể lấy Source code của Lambda function từ repository đã được cung cấp trước đó.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2013.png)

4. **Nén và Tải lên Code**:
   - Để đẩy code lên Lambda, bạn cần nén toàn bộ thư mục code thành một file `.zip`. Sau đó, bạn có thể upload file này lên Lambda qua giao diện **Upload from**.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2014.png)

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2015.png)

### Cấu hình Biến Môi Trường

Tiếp theo, chúng ta sẽ tiến hành cấu hình các biến môi trường cho Lambda function để đảm bảo rằng nó hoạt động chính xác.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Tạo các biến môi trường cần thiết như trong file `appconfig.json`. Các giá trị trong biến môi trường sẽ tương ứng với thông tin kết nối, chẳng hạn như API endpoint và các thông số bảo mật khác.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2016.png)