---
title: "Thiết lập CORS"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 3.6. </b> "
---

### Bước 1: Chọn bucket chứa tài liệu người dùng ma bạn đã tạo trước đó

### Bước 2: Bật CORS

Truy cập vào tab **Permissions** trong bucket tài liệu.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/image.png)

Cuộn xuống cuối, tìm mục **Cross-origin resource sharing (CORS)** và chọn **Edit**.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/image%201.png)

### Bước 3: Cấu hình CORS

Dán đoạn cấu hình sau vào và lưu lại:

```json
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET",
            "HEAD",
            "PUT",
            "POST",
            "DELETE"
        ],
        "AllowedOrigins": [
            "https://dtxxmgtpzjun0.cloudfront.net",
            "http://localhost:5173",
            "https://localhost:5173"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 0
    }
]
```