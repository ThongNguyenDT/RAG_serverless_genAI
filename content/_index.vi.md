---
title: "Serverless Retrieval-Augmented Generation (RAG) trên AWS"
date :  "`r Sys.Date()`" 
# weight : 1
chapter : false
---

# Xây dựng giải pháp Serverless Retrieval-Augmented Generation (RAG) trên AWS

## Tổng quan

Trong bối cảnh trí tuệ nhân tạo sinh (Generative AI) ngày càng phát triển, việc tích hợp thông tin từ bên ngoài và được cập nhật liên tục vào các mô hình ngôn ngữ lớn (LLMs) là một bước tiến quan trọng. Bài viết này sẽ hướng dẫn bạn xây dựng một giải pháp Retrieval-Augmented Generation (RAG) thực sự không máy chủ (serverless) trên AWS. RAG giúp ứng dụng tạo ra các phản hồi chính xác hơn và phù hợp với ngữ cảnh bằng cách truy xuất động thông tin từ các nguồn bên ngoài. Mục tiêu của chúng tôi là giúp bạn tạo ra ứng dụng GenAI nhanh chóng, đồng thời giữ chi phí thấp và chỉ phải trả tiền cho tài nguyên tính toán khi cần thiết.

## RAG là gì và tại sao cần dùng?

### RAG là gì?

Retrieval-Augmented Generation (RAG) là phương pháp nâng cao khả năng của các mô hình ngôn ngữ lớn (LLMs) bằng cách tích hợp thông tin từ bên ngoài vào các phản hồi của chúng. Thay vì chỉ dựa vào kiến thức tĩnh bên trong mô hình, RAG truy xuất động dữ liệu liên quan từ các cơ sở dữ liệu bên ngoài, nguồn tài nguyên internet, hoặc các cơ sở kiến thức tùy chỉnh. Điều này dẫn đến các phản hồi chính xác hơn, phù hợp với ngữ cảnh hơn và được cập nhật mới nhất.

### Tại sao sử dụng RAG?

- **Chính xác hơn**: Bằng cách tích hợp thông tin theo thời gian thực và thông tin cụ thể theo lĩnh vực, RAG cải thiện đáng kể độ chính xác của các phản hồi từ LLMs.
- **Phù hợp với ngữ cảnh**: RAG giúp duy trì ngữ cảnh bằng cách truy xuất thông tin cụ thể, liên quan, làm cho tương tác trở nên có ý nghĩa và chính xác hơn.
- **Thông tin cập nhật**: Không giống như các LLMs truyền thống, dựa vào dữ liệu được huấn luyện sẵn có thể bị lỗi thời, RAG đảm bảo rằng các phản hồi phản ánh thông tin mới nhất hiện có.
- **Hiệu quả về chi phí**: Kiến trúc không máy chủ đảm bảo rằng bạn chỉ phải trả tiền cho những gì bạn sử dụng, giảm thiểu chi phí liên quan đến tài nguyên tính toán không hoạt động.

### Vấn đề mà RAG giải quyết

- **Lỗi thời**: LLMs có thể cung cấp thông tin lỗi thời vì dữ liệu huấn luyện của chúng là tĩnh. RAG giải quyết vấn đề này bằng cách truy xuất dữ liệu mới nhất.
- **Không chính xác**: Nếu không có việc truy xuất dữ liệu theo thời gian thực, LLMs có thể đưa ra các giả định không chính xác. RAG giảm thiểu điều này bằng cách truy cập các nguồn thông tin đáng tin cậy.
- **Khả năng mở rộng**: Cơ sở hạ tầng truyền thống yêu cầu quản lý tài nguyên rộng rãi, có thể tốn kém và phức tạp. Một cách tiếp cận không máy chủ tự động mở rộng quy mô theo nhu cầu.

## Giải pháp

Để giải quyết các thách thức trong việc tích hợp thông tin mới nhất và chính xác vào LLMs, chúng ta sử dụng kiến trúc không máy chủ trên AWS. Cách tiếp cận này sử dụng AWS Lambda để tính toán, Amazon Bedrock cho khả năng AI sinh, và các dịch vụ AWS khác nhau để lưu trữ, truy xuất và quản lý dữ liệu. Bằng cách sử dụng công nghệ không máy chủ, chúng ta đảm bảo rằng giải pháp có thể mở rộng, hiệu quả về chi phí và dễ quản lý, làm cho nó trở thành lựa chọn lý tưởng để triển khai các ứng dụng RAG.

### Các thành phần chính

- **Amazon Bedrock**: Hỗ trợ việc tạo câu trả lời và nhúng tài liệu bằng cách sử dụng các mô hình tiên tiến nhất.
- **AWS Lambda**: Thực thi mã theo sự kiện, xử lý yêu cầu tạo và hoạt động nhúng.
- **Amazon API Gateway (WebSocket)**: Quản lý giao tiếp thời gian thực giữa khách hàng và backend.
- **Amazon Cognito**: Cung cấp xác thực và ủy quyền người dùng.
- **AWS Amplify**: Đơn giản hóa việc triển khai ứng dụng front-end.
- **Amazon Elastic Container Registry (ECR)**: Lưu trữ hình ảnh Docker được sử dụng bởi các hàm Lambda.
- **Amazon S3**: Lưu trữ tài liệu của người dùng và cơ sở dữ liệu vector LanceDB.
- **Amazon DynamoDB**: Duy trì sổ đăng ký tài liệu và theo dõi trạng thái kết nối WebSocket.
- **Amazon SQS**: Xếp hàng thông báo khi người dùng tải lên mới để xử lý nhúng.

## Kiến trúc

Kiến trúc của giải pháp RAG không máy chủ của chúng ta được thiết kế để linh hoạt và mở rộng, tích hợp nhiều dịch vụ AWS để xử lý các khía cạnh khác nhau của ứng dụng. Dưới đây là sơ đồ mô tả kiến trúc:

![architecture.png](https://file.notion.so/f/f/82d24988-e924-4f96-8610-1a16223be9b4/28ce552f-84cb-4458-a62a-0e6e299944ba/architecture.png?table=block&id=d4b4090c-d250-473d-a63a-589bd3763495&spaceId=82d24988-e924-4f96-8610-1a16223be9b4&expirationTimestamp=1725012000000&signature=KR5D6I1FyCjd9FYY6SVoXbTSUIIiMP2ZwI45PR0QaDw&downloadName=architecture.png)

### Các thành phần kiến trúc và quy trình làm việc

1. **Tương tác người dùng**: Người dùng tương tác với ứng dụng front-end, được lưu trữ trên AWS Amplify, cung cấp truy vấn đầu vào và tài liệu.
2. **Xác thực**: Amazon Cognito xử lý xác thực người dùng và đảm bảo truy cập an toàn vào ứng dụng.
3. **Xử lý yêu cầu**: Yêu cầu được gửi qua Amazon API Gateway (sử dụng WebSocket) tới các hàm AWS Lambda.
4. **Lưu trữ dữ liệu**: Tài liệu của người dùng được lưu trữ trong Amazon S3, với siêu dữ liệu được theo dõi trong Amazon DynamoDB.
5. **Nhúng tài liệu**: Khi tài liệu mới được tải lên, Amazon SQS thông báo cho hàm Lambda để tạo nhúng sử dụng Amazon Bedrock. Các nhúng được lưu trữ trong LanceDB trên S3.
6. **Tạo phản hồi**: Đối với các truy vấn của người dùng, một hàm Lambda truy xuất dữ liệu liên quan từ LanceDB, xử lý nó với Amazon Bedrock, và tạo ra phản hồi phù hợp với ngữ cảnh.
7. **Phản hồi thời gian thực**: Phản hồi được gửi lại cho người dùng thông qua kết nối WebSocket được quản lý bởi API Gateway.
