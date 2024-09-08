---
title: "Phân quyền với Identity Pool"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 6.4 </b> "
---

## Cấu hinì Role người dùng Cognito

### Role WebSocket state

Bạn cần tạo role này thủ công hoặc chỉnh sửa file JSON dưới đây cho phù hợp với dự án của bạn.

{{% notice tip %}}
💡 ARN của bảng DynamoDB có định dạng: 
➡️  **⭐arn:aws:dynamodb:`<REGION>`:`<Mã người dùng>`:table/`<TÊN BẢNG>`⭐**
{{% /notice %}}

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Condition": {
				"ForAllValues:StringEquals": {
					"dynamodb:LeadingKeys": [
						"${cognito-identity.amazonaws.com:sub}"
					]
				}
			},
			"Action": [
				"dynamodb:DeleteItem",
				"dynamodb:GetItem",
				"dynamodb:PutItem",
				"dynamodb:Query",
				"dynamodb:UpdateItem"
			],
			"Resource": "<arn websocket state table>",
			"Effect": "Allow"
		}
	]
}
```

### Quyền truy cập Bedrock Models

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": "bedrock:ListFoundationModels",
			"Resource": "*",
			"Effect": "Allow"
		}
	]
}
```

### Tải tài liệu (Document load)

Trong phần này, chúng ta cần tạo hai quyền (permissions).

#### Quyền gọi Lambda

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": "lambda:InvokeFunctionUrl",
			"Resource": "<ARN INTERFACE LAMBDA>",
			"Effect": "Allow"
		}
	]
}
```

#### Quyền thao tác với S3

```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": [
				"s3:DeleteObject",
				"s3:GetObject",
				"s3:ListBucket",
				"s3:PutObject"
			],
			"Resource": [
				"<ARN DOCUMMENT BUCKET>",
				"<ARN DOCUMMENT BUCKET>/private/${cognito-identity.amazonaws.com:sub}/*"
			],
			"Effect": "Allow"
		}
	]
}
```
