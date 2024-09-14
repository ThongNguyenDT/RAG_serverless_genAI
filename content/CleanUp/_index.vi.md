---
title: "Clean Up Resources"
date :  "`r Sys.Date()`" 
weight : 99
chapter : false
---
### Tại sao ta cần xóa tài nguyên sau bài lab?
Dọn dẹp tài nguyên AWS là rất quan trọng vì một số lý do sau:

**1. Quản lý chi phí:** Các tài nguyên không sử dụng hoặc không cần thiết có thể tích tụ và làm tăng chi phí. Bằng cách dọn dẹp thường xuyên, bạn tránh phải trả tiền cho những tài nguyên không được sử dụng.

**2. Bảo mật:** Các tài nguyên không sử dụng có thể trở nên dễ bị tổn thương theo thời gian nếu không được bảo trì đúng cách. Dọn dẹp giúp giảm thiểu bề mặt tấn công và giảm nguy cơ bảo mật tiềm ẩn.

**3. Giới hạn tài nguyên:** AWS có các hạn ngạch về số lượng tài nguyên có thể được cung cấp. Việc loại bỏ tài nguyên không sử dụng đảm bảo bạn không gặp phải giới hạn này, có thể ảnh hưởng đến việc triển khai tài nguyên mới.

**4. Hiệu quả tổ chức:** Môi trường không có sự lộn xộn giúp các nhóm quản lý và giám sát tài nguyên đang hoạt động hiệu quả hơn, cải thiện hiệu quả tổng thể và giảm gánh nặng quản trị.

**5. Tuân thủ:** Dọn dẹp thường xuyên có thể giúp đảm bảo tuân thủ các chính sách tổ chức và yêu cầu quy định, thường yêu cầu giảm thiểu tài nguyên không sử dụng hoặc dư thừa.

#### Trong bài này ta cần thực hiện các bước xóa tại nguyên sau:
- [SQS](SQS/)
- [S3](S3/)
- [DynamoDB](DynamoDB/)
- [ECR](ECR/)
- [Lambda](Lambda/)
- [API Gateway](API_Gateway/)
- [Amplify](Amplify/)
- [System Manager](SystemManager/)