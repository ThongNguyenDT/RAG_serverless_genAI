---
title: "Lambda"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
---

### Remove Permissions

You need to remove 4 roles associated with the Lambda function.

1. Access the **IAM** service.
2. In the **Policy** tab, find the default permissions of your Lambda function.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2041.png)

Proceed to delete these permissions.

### Remove Functions

In the **Lambda** section, remove the following 4 functions:

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2042.png)

Select all the functions, then choose **Action** → **Delete**.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2043.png)

Confirm the deletion.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2044.png)

Wait until the deletion process is complete before proceeding to the next steps.

![image](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2045.png)