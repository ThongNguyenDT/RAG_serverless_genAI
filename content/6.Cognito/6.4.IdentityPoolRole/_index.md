---
title: "Assign permissions with Identity Pool"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 6.4 </b> "
---

## WebSocket State Role

You can create this role manually or edit the following JSON to fit your project.


{{% notice tip %}}
💡 The ARN for a DynamoDB table has the format:  
➡️ **⭐ arn:aws:dynamodb:`<REGION>`:`<User code>`:table/`<NAME OF TABLE>` ⭐**
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

## Bedrock Models Access

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

## Document Load

In this section, we need to create two permissions.

### Lambda Invoke Permission

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

### S3 Access Permission

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