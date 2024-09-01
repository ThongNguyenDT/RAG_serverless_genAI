---
title: "Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---


Trước khi đi sâu vào phần chính của workshop này, việc chuẩn bị các bước cần thiết là vô cùng quan trọng. Trong buổi học này, chúng ta sẽ làm việc với dự án [RAG Serverless GenAI](https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS.git). Dự án này được thiết kế để tự động hóa việc triển khai ứng dụng AI sinh serverless trên AWS bằng cách sử dụng AWS Cloud Development Kit (CDK). Tuy nhiên, nhằm mục đích của workshop này, chúng ta sẽ hướng dẫn cách thiết lập và triển khai dự án bằng AWS Management Console thay vì CDK.

AWS Management Console cung cấp giao diện đồ họa thân thiện với người dùng để quản lý các tài nguyên AWS. Bằng cách làm theo phương pháp sử dụng console, chúng ta có thể hiểu sâu hơn về hạ tầng cơ sở, các cài đặt cấu hình và quy trình triển khai, từ đó giúp chúng ta kiểm soát tốt hơn từng bước trong quá trình triển khai.

Để bắt đầu, hãy làm theo các bước sau:

#### Bước 1: Clone Repository

Đầu tiên, bạn cần clone repository chứa các tệp tin của dự án. Điều này sẽ cho phép bạn truy cập vào toàn bộ mã nguồn và các tài nguyên cần thiết cho việc triển khai.

```bash
git clone https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS.git
cd RAG_serverless_genAI
```

Sau khi clone repo về máy, hãy mở nó ra, và cùng tìm hiểu xem chúng có những gì nào.

#### Bước 2: Xem xét cấu trúc dự án
Trước khi tiến xa hơn, hãy dành chút thời gian để xem xét cấu trúc của dự án. Việc làm quen với nội dung của repository sẽ giúp bạn hiểu rõ hơn về các thành phần khác nhau và cách chúng kết hợp với nhau.

Trong thư mục gốc của dự án, bạn sẽ tìm thấy một số tệp và thư mục quan trọng:

- **lib/, bin/**: Chứa các định nghĩa của CDK stack, tự động hóa việc tạo các tài nguyên trên AWS. Trong workshop này, chúng ta sẽ tham khảo các định nghĩa này nhưng sẽ tạo tài nguyên thủ công thông qua AWS Management Console.
- **lambda/**: Chứa mã nguồn cho các chức năng AWS Lambda được sử dụng trong ứng dụng.
- **lib/**: Cũng bao gồm cấu hình nguồn cho dịch vụ bedrock - genAI serverless của bạn.
- **README.md**: Cung cấp tổng quan về dự án và hướng dẫn cách triển khai nó bằng CDK.

Tổng quan này giúp bạn có cái nhìn rõ hơn về những gì dự án thực hiện và các thành phần nào sẽ tham gia vào quá trình triển khai. Khi bạn đã cảm thấy thoải mái với cấu trúc, hãy tiếp tục với các bước tiếp theo trong AWS Management Console.