---
title: "Extracting Information from User Data"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 8.1. </b> "
---

In the **Lambda** service, create a new function.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2011.png)

Next, create a Lambda function using a **Container image**:

- Initialize the Lambda from a **Container image**
- Name your Lambda
- Select an image

Then, proceed with the initialization.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2017.png)

### Configure Environment Variables

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Set up the environment variables as follows:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2018.png)

- **WEBSOCKET_ENDPOINT**  
  Copy this from the `appconfig.json` file.
  
- **DYNAMODB_WEBSOCKET_STATE_TABLE**  
  Copy this from the `appconfig.json` file or:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2019.png)

- **SQS_QUEUE_URL**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2020.png)

- **DYNAMODB_DOCUMENT_REGISTRY_TABLE**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2021.png)

- **DYNAMODB_MD5_BY_S3_PATH_INDEX**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2022.png)

- **LANCEDB_BUCKET**  
  Created in earlier steps.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2023.png)

The final two variables can be found in this file:

- **EMBEDDING_MODEL**
- **EMBEDDING_SIZE**

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2024.png)

### Edit Memory

Navigate to the configuration section shown in the image:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2025.png)

Here, increase the **memory function** to 2048 MB and set the timeout to 5 minutes.

Pay attention to the **Role** setting for the next step.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2026.png)

### Edit Role

Under **Existing role**, select as shown:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2027.png)

Edit the JSON policy by adding the following statements:

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

After adding the statements, review your changes, which should look like this:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2028.png)

### Add a Lambda Trigger

Go to the **Configuration** tab and access the **Trigger** section.

Proceed to add a trigger:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2029.png)

Select the event that will invoke the Lambda function.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2030.png)

In this case, the Lambda function will be triggered each time the **User_document_bucket** receives a PDF file via an intermediate service, **SQS**.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2031.png)

Activate the trigger, and set the **batch size** to 5. Leave the other settings as shown:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2032.png)

**Note**: After adding the trigger, verify whether its status is set to **Enabled**:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2033.png)

Wait for the trigger to switch to the **Enabled** state:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2034.png)