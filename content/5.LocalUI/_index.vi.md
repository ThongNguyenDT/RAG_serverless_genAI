---
title: "Thiết lập giao diện trên local"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
### Cài Đặt Node.js

Truy cập trang chủ Node.js và tải phiên bản phù hợp với thiết bị của bạn:

[Node.js — Run JavaScript Everywhere](https://nodejs.org/en)

### Mở Dự Án Trong VS Code

- Mở terminal.
- Chuyển đến thư mục chứa mã nguồn.

Nhập lệnh sau để mở dự án trong VS Code:

```bash
code .
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image.png)

### Cài Đặt Các Package

Chạy lệnh sau để cài đặt các package cần thiết:

```powershell
npm i
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image.png)

### Cấu Hình Local

Chạy lệnh sau để khởi động dự án ở chế độ phát triển:

```powershell
npm run dev
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%201.png)

Mở trình duyệt và truy cập vào đường link ***local***:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%202.png)

Tạo file ***appconfig.json*** trong thư mục ***public***:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%203.png)

Nội dung trong ***appconfig.json***:


```json
{
    "inferenceURL": "<YOUR Interface Lambda URL>>",
      "websocketURL": "<YOUR WebSocket URL>",
      "websocketStateTable": "<YOUR WebSocket DynamoDB StateTable tableName>",
      "stackName": "<StackName>",
      "region": "<YOUR REGION>",
      "bucketName": "<YOUR Document Bucket Name>",
      "auth": {
        "user_pool_id": "<YOUR USER POOL ID>",
        "aws_region": "<YOUR REGION>",
        "user_pool_client_id":"<YOUR USER POOL CLIENT ID>",
        "identity_pool_id": "identityPoolId",
        "standard_required_attributes": ["email"],
        "username_attributes": ["email"],
        "user_verification_types": ["email"],
        "password_policy": {
          "min_length": 8,
          "require_numbers": true,
          "require_lowercase": true,
          "require_uppercase": true,
          "require_symbols": true
        },
        "unauthenticated_identities_enabled": true
      },
      "version": "1",
      "storage": {
        "bucket_name": "<YOUR Document Bucket Name>",
        "aws_region": "<YOUR REGION>"
      }
}
```

Bạn cần cung cấp các thông tin đã biết vào đây:

Riêng phần `<StackName>` là tên dự án của bạn.

### Kiểm Tra Giao Diện UI

Bạn truy cập vào [Localhost:5173](http://Localhost:5173) để xem giao điện web

![image.png](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%204.png)

{{% notice tip %}} Lưu ý sau mỗi lần thay đổi `appconfig.json` bạn cần phải terminate `npm run dev` bằng tổ hợp phí **ctrl+c** → **y** →  **enter** và chạy lại   `npm run dev` để config được thiết lập❗❗❗
{{% /notice %}}