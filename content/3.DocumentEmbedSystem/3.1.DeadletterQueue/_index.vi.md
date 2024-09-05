---
title: "Tạo Dead letter Queue"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

Trong bài viết này, chúng ta sẽ cùng thực hiện các bước tạo **Dead Letter Queue** (DLQ) trên dịch vụ **Amazon Simple Queue Service** (SQS).

### Bước 1: Truy cập SQS trên AWS Console
Đầu tiên, bạn cần đăng nhập vào Bước 2: Tạo Queue Mới
Nhấp vào nút Create Queue để tiến hành tạo một hàng đợi mới. và tìm đến dịch vụ SQS. Giao diện sẽ như hình dưới đây:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled.png)

### Bước 2: Tạo Queue Mới
Nhấp vào nút **Create Queue** để tiến hành tạo một hàng đợi mới.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%201.png)

### Bước 3: Cấu Hình Dead Letter Queue
Trong bước này, chúng ta sẽ tạo **Dead Letter Queue** với các cấu hình cụ thể như sau:

- Tên **Dead Letter Queue**: Đặt tên phù hợp để dễ quản lý.
- **Visibility Timeout**: Đặt giá trị là `300` giây để đảm bảo thời gian hàng đợi không khả kiến đủ lâu cho việc xử lý.
- Các cấu hình khác giữ nguyên mặc định.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%202.png)

### Bước 4: Tạo Queue
Sau khi điền đầy đủ thông tin, nhấp Create Queue để hoàn tất quá trình tạo.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%203.png)

### Kết Quả
Khi hoàn tất, bạn sẽ thấy hàng đợi đã được tạo thành công như hình dưới đây:

![image.png](/images/SQS%204c16c634931e432886dad2df7a7c65af/image.png)

