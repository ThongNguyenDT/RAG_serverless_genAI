---
title: "Cấu Hình Document Registry Table"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### Bước 3: Cấu Hình Document Registry Table

- **Đặt tên cho table:** Chọn một tên phù hợp cho bảng.
- **Partition key:** Chọn `md5`.
- **Sort key:** Chọn `s3_path`.
- **Custom Index:** Chọn tùy chọn custom để thêm index.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%201.png)

- **Thiết lập Global Index:** Cấu hình index toàn cục cho cột **s3_path**.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%202.png)

- Nhấn **Create Table** để hoàn tất.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%203.png)

Sau khi tạo xong, bạn sẽ thấy bảng được thiết lập như sau:

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%204.png)


