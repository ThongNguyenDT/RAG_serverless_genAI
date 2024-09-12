---
title: "Thiết lập Lambda Function"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 8.3.1 </b> "
---

Tại trang console của AWS, tìm kiếm dịch vụ **Lambda** và tiến hành khởi tạo một hàm Lambda từ **ECR**.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image.png)

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2035.png)

### Cấu Hình Biến Môi Trường

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Cấu hình các biến môi trường như sau:

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2036.png)

- **s3BucketName**: Tương tự như ENV `LANCEDB_BUCKET` của Document Processor, được tạo ở các bước đầu.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2023.png)

- Sao chép từ `appconfig.json`:
  - **region**,
  - **IDENTITY_POOL_ID**,
  - **USER_POOL_ID**,
  - **StackName**.
  
- Tương tự như ở Document Processor:
  - **EMBEDDING_MODEL**,
  - **EMBEDDING_SIZE**: 
- **LANGCHAIN_VERBOSE**: true.

### Cấu Hình Bộ Nhớ

Đi đến vị trí thiết lập như trong hình dưới đây.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2025.png)

Tại đây, bạn cần điều chỉnh bộ nhớ của function lên **2048 MB** và đặt thời gian tối đa là **5 phút**. Lưu ý chuẩn bị cho phần tiếp theo về **role**.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2037.png)

### Cấu Hình Quyền

Tương tự như các bước trên, tại đây bạn cần chỉnh sửa quyền mặc định của function theo mẫu sau:

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": [
				"bedrock:InvokeModel",
				"bedrock:InvokeModelWithResponseStream",
				"bedrock:ListFoundationModels",
				"cognito-identity:GetCredentialsForIdentity",
				"cognito-identity:GetId",
				"ssm:GetParameter"
			],
			"Resource": "*",
			"Effect": "Allow"
		},
		{
			"Action": "s3:GetObject",
			"Resource": [
				"<ARN LANCED VECTOR BUCKET>",
				"<ARN LANCED VECTOR BUCKET>/*"
			],
			"Effect": "Allow"
		},
		{
			"Action": "s3:ListBucket",
			"Resource": "<ARN LANCED VECTOR BUCKET>",
			"Effect": "Allow"
		}
	]
}
```

### **Function URL**

Truy cập mục **Configuration** và tìm đến **Function URL** để tiến hành tạo function.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2038.png)

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2039.png)

#### Kích Hoạt CORS

Tại mục **CORS**, bạn thiết lập như sau:

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2040.png)