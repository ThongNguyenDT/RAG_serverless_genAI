---
title: "Test User Pool đã setup"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 6.2. </b> "
---

Thay thế các mục sau trong ***appconfig.json*** bằng những thông tin đã có từ các bước trước:

- `<YOUR REGION>`
- `<YOUR USER POOL ID>`
- `<YOUR USER POOL CLIENT ID>`

Bạn sẽ thử tạo tài khoản và đăng nhập trên localhost của mình. Nếu các bước cấu hình Cognito đã chính xác, bạn sẽ đăng nhập thành công và thấy giao diện như sau:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%205.png)

Đến đây mọi thứ đã tạm ổn, bạn nên thử chức năng **đăng xuất** để đảm bảo hệ thống hoạt động đúng cách:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%206.png)

Trong phần này của ***appconfig.json*** , hãy cấu hình tương tự với cấu hình trong **user pool** của bạn.

```json
"password_policy": {
          "min_length": 8,
          "require_numbers": true,
          "require_lowercase": true,
          "require_uppercase": true,
          "require_symbols": true
        },
        ...
```