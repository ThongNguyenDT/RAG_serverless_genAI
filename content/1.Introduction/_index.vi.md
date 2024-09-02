---
title: "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

Trong bối cảnh trí tuệ nhân tạo hiện đại, việc tích hợp thông tin động và được cập nhật liên tục vào các mô hình ngôn ngữ lớn (LLMs) là điều cần thiết để phát triển các ứng dụng thông minh và phản hồi nhanh chóng. Các LLM truyền thống chủ yếu dựa vào cơ sở kiến thức tĩnh có sẵn, điều này có thể dẫn đến việc thông tin trở nên lỗi thời theo thời gian. Retrieval-Augmented Generation (RAG) giải quyết hạn chế này bằng cách cho phép LLM truy cập dữ liệu theo thời gian thực, đảm bảo rằng các phản hồi luôn chính xác, phù hợp với ngữ cảnh và được cập nhật theo thông tin mới nhất.

Trong hướng dẫn này, chúng ta sẽ khám phá cách xây dựng giải pháp RAG không máy chủ (serverless) bằng cách sử dụng Amazon Web Services (AWS). Bằng cách áp dụng kiến trúc không máy chủ, chúng ta tận dụng được các lợi ích của khả năng mở rộng theo nhu cầu, hiệu quả về chi phí và dễ dàng quản lý, cho phép giải pháp RAG của chúng ta xử lý các tải công việc khác nhau mà không phát sinh chi phí không cần thiết. Buổi hướng dẫn này sẽ dẫn bạn qua quá trình xây dựng một hệ thống RAG mạnh mẽ, có khả năng mở rộng, sử dụng công nghệ tiên tiến và các phương pháp tốt nhất để tối đa hóa tiềm năng của các ứng dụng AI sinh.

### Bạn sẽ học được gì

Trong buổi hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tạo ra một giải pháp RAG không máy chủ trên AWS, cho thấy cách tích hợp liền mạch các dịch vụ của AWS để đạt được một kiến trúc chức năng cao và hiệu quả. Trọng tâm sẽ là xây dựng một ứng dụng có thể truy xuất thông tin động, xử lý thông tin đó với một mô hình AI sinh, và cung cấp cho người dùng các phản hồi theo thời gian thực và phù hợp với ngữ cảnh. Cuối buổi hướng dẫn này, bạn sẽ có hiểu biết toàn diện về cách triển khai và quản lý một giải pháp RAG không máy chủ trên AWS, cho phép bạn xây dựng các ứng dụng mạnh mẽ dựa trên AI có khả năng thích ứng với các thông tin thay đổi liên tục.

### Các mục tiêu học tập chính

- **Hiểu về khái niệm RAG**: Tìm hiểu về Retrieval-Augmented Generation và tầm quan trọng của nó trong việc nâng cao khả năng của các mô hình ngôn ngữ lớn.
- **Tận dụng công nghệ không máy chủ**: Khám phá cách các dịch vụ không máy chủ của AWS, như Lambda, API Gateway, và Bedrock, có thể được sử dụng để xây dựng các ứng dụng AI có khả năng mở rộng và hiệu quả về chi phí.
- **Triển khai truy xuất dữ liệu theo thời gian thực**: Học cách tích hợp truy xuất dữ liệu theo thời gian thực vào ứng dụng AI của bạn bằng cách sử dụng cơ sở dữ liệu vector và các dịch vụ khác của AWS.
- **Phát triển kiến trúc có khả năng mở rộng**: Khám phá các phương pháp tốt nhất để thiết kế các kiến trúc có khả năng mở rộng có thể xử lý tải công việc tăng lên mà không làm giảm hiệu suất hoặc tăng chi phí.
- **Bảo mật và quản lý quyền truy cập người dùng**: Hiểu cách bảo mật ứng dụng của bạn bằng cách sử dụng AWS Cognito và quản lý xác thực và ủy quyền người dùng một cách hiệu quả.

## Mục lục

1. [Giới thiệu](1.introduction/) 
2. [Các bước chuẩn bị](2.preparation/)
3. [Thiết Lập Hệ Thống Xử Lý Document Từ Người Dùng](3.documentembedsystem/) 
4. [Hướng Dẫn Tạo Các Bảng Trong DynamoDB](4.DynamoDB/) 
5. [Thiết lập giao diện trên local](5.LocalUI/) 
6. [Quản lý user với Cognito](6.Cognito/) 
7. [Xây dưng API xử lý dữ liệu người dùng](7.MainAPIComponent/) 
8. [Thiết lập Inference System](8.Interface/) 
9. [Cấu hình System Manager Parameter Store](9.SystemManager/)  
10. [Kiểm tra các thiết lập trên giao diện](10.UITesting/) 
11. [Deploy giao diện dự án lên AWS Amplify](11.Amplify/) 
12. [Clean Up Resources](CleanUp/) 