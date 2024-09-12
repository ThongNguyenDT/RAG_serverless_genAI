---
title: "Lambda Function setup"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 8.3.1 </b> "
---

On the AWS console page, search for the **Lambda** service and proceed to initialize a Lambda function from **ECR**.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image.png)

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2035.png)

### Environment Variable Configuration

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Configure the environment variables as follows:

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2036.png)

- **s3BucketName**: Similar to ENV `LANCEDB_BUCKET` of the Document Processor, created in the initial steps.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2023.png)

- Copy from `appconfig.json`:
  - **region**,
  - **IDENTITY_POOL_ID**,
  - **USER_POOL_ID**,
  - **StackName**:
-  Similar to the Document Processor:
   - **EMBEDDING_MODEL**,
   - **EMBEDDING_SIZE**
- **LANGCHAIN_VERBOSE**: true.

### Memory Configuration

Go to the settings location as shown below.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2025.png)

Here, you need to set the function memory to `2048 MB` and configure the timeout to `5 minutes`. Note to prepare for the next section regarding **role**.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2037.png)

### Role Configuration

Similar to the previous steps, you need to edit the default permissions of the function according to the following template:

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

Navigate to the **Configuration** section and access the **Function URL** to create the function.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2038.png)

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2039.png)

#### Enable CORS

In the **CORS** section, configure as follows:

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2040.png)