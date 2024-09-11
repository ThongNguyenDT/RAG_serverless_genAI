---
title: "Xử lý API route vs Lambda"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 7.2. </b> "
---

Trong bài viết này, chúng ta sẽ tìm hiểu cách quản lý các route của **API Gateway** bằng **AWS Lambda**. Chúng ta cũng sẽ học cách chuyển tất cả các yêu cầu từ API Gateway đến một hàm Lambda duy nhất. Hàm Lambda sẽ xử lý các tác vụ bằng cách phân tách route và xử lý chúng dựa trên các đường dẫn cụ thể.

Kỹ thuật này đặc biệt hữu ích trong các tình huống mà bạn muốn đơn giản hóa kiến trúc bằng cách sử dụng một hàm Lambda duy nhất để xử lý nhiều route. Bằng cách định tuyến tất cả các yêu cầu API Gateway đến một Lambda trung tâm, bạn giảm nhu cầu triển khai nhiều hàm và tăng khả năng bảo trì.

Các bước để triển khai giải pháp này bao gồm:

1. **[Khởi tạo Lambda function](7.2.1.LambdaFunction/)**  
   Trong bước này, chúng ta sẽ cấu hình hàm AWS Lambda để xử lý tất cả các yêu cầu đến. AWS Lambda cho phép bạn chạy mã của mình mà không cần phải triển khai hoặc quản lý máy chủ, điều này làm cho nó trở thành lựa chọn tuyệt vời cho các dịch vụ backend có khả năng mở rộng.

2. **[Xử lý API route vs Lambda](7.2.2.APIGatewaySetup)**  
   Sau khi cấu hình hàm Lambda, chúng ta cần thiết lập API Gateway để gửi tất cả các yêu cầu đến Lambda. Hàm Lambda sẽ sử dụng logic để phân tích các yêu cầu đến dựa trên đường dẫn và thực hiện các hành động tương ứng.

Để tìm hiểu thêm về tích hợp API Gateway với Lambda, hãy truy cập vào tài liệu chính thức của [AWS tại đây](https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway.html).