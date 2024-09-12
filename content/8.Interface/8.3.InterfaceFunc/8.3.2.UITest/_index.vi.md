---
title: "kiểm tra Lambda Function URL"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 8.3.2 </b> "
---
Sau khi thiết lập URL của Lambda, bạn sẽ có một **inferenceURL** như hình dưới đây:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%208.png)

### Cập Nhật `appconfig.json`

Bạn cần thay đổi giá trị của **inferenceURL** trong file ***appconfig.json*** để đảm bảo nó khớp với URL mà bạn đã thiết lập. Đây là bước quan trọng để cấu hình hệ thống hoạt động chính xác.

Hãy mở file ***appconfig.json*** và thay thế giá trị của **inferenceURL** bằng URL mới mà bạn đã nhận được từ bước thiết lập Lambda.