---
title: "Lambda Function setup"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.3.1. </b> "
---


In the AWS Lambda service, we will proceed to create a new function to Authorize WebSocket API

1. **Access Lambda Service**:
   - First, navigate to the **Lambda** service in AWS and choose the option to create a new function.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2011.png)

2. **Create a Lambda Function**:
   - In the function creation interface, you need to provide a name for your Lambda function.
   - Select **Runtime** as Node.js 20, which is the JavaScript version used to handle WebSocket operations and related requests.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2012.png)

   - After naming the function and selecting the runtime, click **Create Function** to proceed with the setup.

3. **Upload Source Code**:
   - The source code for your Lambda function is stored in the Github repository provided earlier. You can refer to this for the necessary code.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2013.png)

4. **Compress and Upload Code**:
   - To upload your code to Lambda, compress the entire code folder into a `.zip` file. Then, upload this file to Lambda using the **Upload from** option.

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2014.png)

   ![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2015.png)

## Configure Environment Variables

Next, we will configure the environment variables for the Lambda function to ensure it operates correctly.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Create the necessary environment variables similar to those defined in the `appconfig.json` file. The values in the environment variables correspond to connection information, such as the API endpoint and security parameters.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2016.png)