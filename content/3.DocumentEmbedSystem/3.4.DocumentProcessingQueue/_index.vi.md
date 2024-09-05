---
title: "Tạo Document Processing Queue"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

# Tạo Queue và Cấu Hình Quyền Cho S3 Trên AWS SQS

Tương tự như cách tạo **Dead Letter Queue** trước đó, chúng ta cần thực hiện các bước sau:

- **Đặt tên cho Queue**.
- Thiết lập **Visibility Timeout** là `120` giây.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%204.png)

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%205.png)

### Cấu Hình Quyền Cho S3

Để dịch vụ S3 có thể cấp quyền truy cập cho queue, chúng ta cần cấu hình quyền cụ thể như sau:

- Chọn như hình dưới đây:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%206.png)

- Sao chép và thay thế đoạn sau `"Resource": "<YOUR CURRENT SQS ARN>"` trong đoạn mã dưới đây:


```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": [
        "sqs:GetQueueAttributes",
        "sqs:GetQueueUrl",
        "sqs:SendMessage"
      ],
        "Resource": "<YOUR CURRENT SQS ARN>",
        "Condition": {
        "ArnLike": {
          "aws:SourceArn": "<YOUR DOCUMENT BUCKKET ARN>"
        }
      }
    }
  ]
}
```

- Để lấy giá trị "`<YOUR DOCUMENT BUCKKET ARN>`": bạn cần lấy ARN từ bucket như hình dưới:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%207.png)

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%208.png)

### Thiết Lập Dead Letter Queue
Sau khi đã thay thế xong, tiến hành thiết lập Dead Letter Queue:

- Mở **Dead-letter queue**
- Chon **Dead-letter queue** đã tạo
- Set Maximum receives
- Cuối cùng, nhấn **Create Queue** để hoàn tất.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%209.png)
