---
title: "Document Processing Queue"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

Similar to creating a **Dead Letter Queue**, we need to perform the following steps:

- **Name the Queue**.
- Set **Visibility Timeout** to `120` seconds.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%204.png)

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%205.png)

### Configure Permissions for S3

To allow S3 to grant access to the queue, we need to configure the following permissions:

- Select as shown below:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%206.png)

- Copy and replace the following `"Resource": "<YOUR CURRENT SQS ARN>"` in the JSON block below:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": [
        "sqs:GetQueueAttributes",
        "sqs:GetQueueUrl",
        "sqs:SendMessage"
      ],
      "Resource": "<YOUR CURRENT SQS ARN>",
      "Condition": {
        "ArnLike": {
          "aws:SourceArn": "<YOUR DOCUMENT BUCKET ARN>"
        }
      }
    }
  ]
}
```

- To obtain "`<YOUR DOCUMENT BUCKKET ARN>`", you can find the ARN from your bucket as shown:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%207.png)

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%208.png)

### Set Up Dead Letter Queue
After replacing the values, proceed to set up the **Dead Letter Queue**:

- Open **Dead-letter queue**.
- Select the previously created **Dead-letter queue**.
- Set the **Maximum Receives**.
- Finally, click **Create Queue** to complete.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%209.png)