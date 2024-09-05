---
title: "Thiết lập Document bucket đẩy thông báo sang SQS"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

### Bước 1: Chọn bucket chứa tài liệu người dùng

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%206.png)

### Bước 2: Truy cập tab **Properties**

Cuộn xuống và tìm mục **Event notifications**.

Chọn **Create Event notifications**.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%207.png)

### Bước 3: Cấu hình Event Notification

- Đặt tên cho event.
- Chọn **Suffix** (định dạng file).
- Chọn các hành động tác động lên event:
    - Ở đây, chúng ta chọn tất cả các mục tạo và xóa.
- Chọn nơi nhận thông báo tác động, trong trường hợp này là document SQS.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%208.png)

### Bước 4: Kiểm tra Event Notification

Sau khi khởi tạo event, bạn có thể thử tạo một file PDF, upload vào bucket và kiểm tra thông báo xuất hiện trong SQS.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%209.png)

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%2010.png)

Chúng ta có thể thấy rằng có 2 tin nhắn (messages) trong document queue. Sau một thời gian, chúng sẽ xuất hiện trong dead-letter queue và biến mất khỏi document queue.
