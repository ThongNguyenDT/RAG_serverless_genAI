---
title: "Thiết lập Inference System"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8. </b> "
---

Trong phần này, chúng ta sẽ cùng nhau thiết lập hệ thống xử lý các prompt của người dùng.

Cụ thể, chúng ta sẽ thực hiện cài đặt các dịch vụ **Lambda** + *URL Function* và **Bedrock** cho các tác vụ xử lý chính. Điều này đảm bảo rằng các yêu cầu của người dùng được xử lý nhanh chóng và có khả năng mở rộng khi cần.

### Các bước cài đặt bao gồm:

1. **[Làm việc với ECR](8.1.ECR/)**    
   Trong bước này, chúng ta sẽ cấu hình **Elastic Container Registry (ECR)** để lưu trữ và quản lý các image Docker. Dịch vụ này đóng vai trò quan trọng trong việc giúp các hàm Lambda của chúng ta có thể được container hóa và di chuyển qua các môi trường khác nhau.


2. **[Trích xuất thông tin từ dữ liệu người dùng](8.2.UserDataEmbed/)**    
   Ở bước này, chúng ta sẽ làm việc với việc lấy dữ liệu cần thiết từ đầu vào của người dùng để xử lý qua dịch vụ **Bedrock**. Dữ liệu sẽ được định dạng và cấu trúc để có thể phân tích và xử lý chính xác các prompt của người dùng.


3. **[Cấu hình Interface Lambda](8.3.InterfaceFunc/)**    
   Bước này liên quan đến các thao tác giao diện cho **Lambda** để có thể giao tiếp với các dịch vụ khác như **Bedrock** và xử lý phản hồi cho người dùng. Lambda sẽ được cấu hình để nhận các prompt từ người dùng và cung cấp kết quả một cách hiệu quả.


Để tìm hiểu thêm về cách cài đặt các dịch vụ này, bạn có thể truy cập tài liệu chính thức của [AWS Lambda tại đây](https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html).