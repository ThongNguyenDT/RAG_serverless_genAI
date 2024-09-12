---
title: "Trích xuất thông tin từ dữ liệu người dùng"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 8.2. </b> "
---


Tại dịch vụ **Lambda**, tiến hành tạo function mới.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2011.png)

Tiếp theo, tạo một Lambda function từ **Container image**:

- Khởi tạo Lambda từ **Container image**
- Đặt tên Lambda
- Chọn image

Sau đó, tiến hành khởi tạo.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2017.png)

### Cấu hình biến môi trường

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Cấu hình các biến môi trường như sau:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2018.png)

- **WEBSOCKET_ENDPOINT**  
  Copy từ file `appconfig.json`
  
- **DYNAMODB_WEBSOCKET_STATE_TABLE**  
  Copy từ file `appconfig.json` hoặc:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2019.png)

- **SQS_QUEUE_URL**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2020.png)

- **DYNAMODB_DOCUMENT_REGISTRY_TABLE**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2021.png)

- **DYNAMODB_MD5_BY_S3_PATH_INDEX**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2022.png)

- **LANCEDB_BUCKET**  
  Tạo ở những bước đầu.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2023.png)

Hai mục còn lại bạn tìm trong file này:

- **EMBEDDING_MODEL**
- **EMBEDDING_SIZE**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2024.png)

### Chỉnh dung lượng bộ nhớ

Đi đến phần thiết lập như trong hình:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2025.png)

Tại đây, chỉnh **memory function** lên 2048 và chỉnh thời gian timeout lên 5 phút.

Chú ý đến mục **Role** để chuẩn bị cho phần tiếp theo.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2026.png)

### Chỉnh sửa Role

Tại mục **Existing role**, click chọn như hình:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2027.png)

Chỉnh sửa tập JSON như sau và thêm các **statement**:

```json
	{
			"Action": [
				"sqs:ChangeMessageVisibility",
				"sqs:DeleteMessage",
				"sqs:GetQueueAttributes",
				"sqs:GetQueueUrl",
				"sqs:ReceiveMessage"
			],
			"Resource": "<ARN DOCUMENT PROCESS QUEUE>",
			"Effect": "Allow"
		},
		{
			"Action": [
				"dynamodb:BatchGetItem",
				"dynamodb:BatchWriteItem",
				"dynamodb:ConditionCheckItem",
				"dynamodb:DeleteItem",
				"dynamodb:DescribeTable",
				"dynamodb:GetItem",
				"dynamodb:GetRecords",
				"dynamodb:GetShardIterator",
				"dynamodb:PutItem",
				"dynamodb:Query",
				"dynamodb:Scan",
				"dynamodb:UpdateItem"
			],
			"Resource": [
				"<ARN DYNAMODB DOCUMENT TABLE>",
				"<ARN DYNAMODB WEBSOCKET STATE TABLE>",
				"<ARN DYNAMODB DOCUMENT TABLE>/index/*"
			],
			"Effect": "Allow"
		},
		{
			"Action": [
				"s3:Abort*",
				"s3:DeleteObject*",
				"s3:GetBucket*",
				"s3:GetObject*",
				"s3:List*",
				"s3:PutObject",
				"s3:PutObjectLegalHold",
				"s3:PutObjectRetention",
				"s3:PutObjectTagging",
				"s3:PutObjectVersionTagging"
			],
			"Resource": [
				"<ARN lANCEDB VECTOR BUCKET>",
				"<ARN DOCUMMENT BUCKET>",
				"<ARN lANCEDB VECTOR BUCKET>/*",
				"<ARN DOCUMMENT BUCKET>/*"
			],
			"Effect": "Allow"
		},
		{
			"Action": "s3:DeleteObject*",
			"Resource": "<ARN lANCEDB VECTOR BUCKET>/*",
			"Effect": "Allow"
		},
		{
			"Action": [
				"bedrock:InvokeModel",
				"bedrock:InvokeModelWithResponseStream",
				"execute-api:ManageConnections"
			],
			"Resource": "*",
			"Effect": "Allow"
		}
```

Sau khi chỉnh sửa, review lại, có dạng như hình:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2028.png)

### Thêm trigger cho Lambda

Tại tab **Configuration**, truy cập vào mục **Trigger**.

Thực hiện thêm trigger:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2029.png)

Chọn đối tượng sẽ gọi hàm Lambda.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2030.png)

Trong trường hợp này, hàm Lambda sẽ được gọi mỗi khi **User_document_bucket** nhận được tệp PDF, thông qua dịch vụ trung gian là **SQS**.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2031.png)

Bật **Trigger** và chỉnh **batch size** thành 5, các thông số còn lại giữ nguyên như trong hình:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2032.png)

**Lưu ý**: Sau khi thêm trigger, kiểm tra xem trạng thái của trigger đã **Enable** hay chưa:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2033.png)

Chờ đến khi nó chuyển sang trạng thái **Enable**:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2034.png)

