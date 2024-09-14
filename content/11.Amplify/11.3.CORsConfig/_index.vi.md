---
title: "Cấu hình CORs"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 11.3. </b> "
---

Trong phần này, bạn cần cấu hình CORs ở hai nơi:

- API Gateway, đây là nơi mà lỗi đã xuất hiện như bạn thấy trước đó.
- Document bucket, đây là lỗi ngăn người dùng tải tài liệu lên.

## Cấu hình CORs cho API Gateway

Nếu bạn nhớ lại, khi cấu hình API Gateway với websocket, chúng ta chưa cấu hình CORs. Vậy CORs sẽ được cấu hình ở đâu?

Chúng ta sẽ tiến hành cấu hình CORs trong **Lambda Authorizer**.

Để làm điều này, hãy truy cập vào Lambda Authorizer theo cách tương tự như khi chúng ta đã cấu hình biến môi trường trước đó.

Sau khi truy cập, chúng ta sẽ thấy màn hình như sau:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2016.png)

Trong phần **COMMA_SEPARATED_ORIGINS**, có thể bạn đã để trống hoặc điền vào một chuỗi ký tự bất kỳ. Nhiệm vụ của chúng ta bây giờ là chỉnh sửa và dán tên miền của dự án mà bạn đã deploy vào đây.

❗ Lưu ý: Đường dẫn của bạn không được có dấu “/” ở cuối.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2019.png)

Sau đó, lưu lại thay đổi.

Chờ một vài phút và thử tải lại trang web của bạn.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2020.png)

Sau khi chờ đợi một lúc, bạn sẽ thấy mình đã kết nối thành công.

## Cấu hình CORs cho User Document Bucket

Khi truy cập vào tab **documents**, bạn có thể thấy lỗi hiển thị như sau:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2021.png)

Tương tự như trước, chúng ta cần cấu hình CORs cho Document Bucket. Đây là cấu hình CORs mà bạn có thể sử dụng:

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

Thay thế đường dẫn CloudFront trong đoạn code trên bằng đường dẫn Amplify của bạn. Ví dụ trong dự án của mình là:

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
            "https://main.d24pacxd5z3be6.amplifyapp.com",
            "http://localhost:5173",
            "https://localhost:5173"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 0
    }
]
```

## Kiểm tra lại

Hãy kiểm tra lại tất cả các chức năng của ứng dụng sau khi bạn đã deploy, để đảm bảo rằng mọi thứ đều hoạt động trơn tru trước khi chính thức công bố dự án.

Như vậy, bài hướng dẫn đã kết thúc tại đây. Trong bước cuối cùng, chúng ta cần dọn dẹp và xóa các tài nguyên không còn cần thiết sau khi hoàn thành bài lab.

