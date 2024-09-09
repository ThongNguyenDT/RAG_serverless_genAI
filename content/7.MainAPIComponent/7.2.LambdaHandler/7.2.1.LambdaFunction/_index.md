---
title: "Setup AWS lambda"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.2.1. </b> "
---

In the AWS console, search for the Lambda service and proceed to create a new **Lambda function**.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image.png)

Next, create a **Lambda function** running `Node.js` version ***20***:

- Name your **Lambda function**.
- Select Node.js 20 as the Runtime.
- Click **Create function** to complete the setup.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%201.png)

The source code is stored in the GitHub repository provided earlier. You can refer to it and copy this source code here:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%202.png)

Paste your source code into the editor:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%203.png)

## Configure Environment Variables

Next, configure the environment variables for your **Lambda function** to ensure it operates correctly.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%204.png)

Create environment variables as follows:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%205.png)

## Retrieve WebSocket Link

In the Stage section of your API, copy the URL of the stage to assign it to your environment variables.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%206.png)

Once you have the link, paste it into the environment variables:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%207.png)

- Click **Save** to save the configuration.

Return to the code section and deploy the **Lambda function** you created.

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%208.png)

Proceed to the next step.

## Edit Role

In the Lambda settings interface, select:

**Configuration** → **Permissions** → *Role*

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%209.png)

You will see the default role for the **Lambda function**:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2010.png)

Select this role and edit it to add the following statement:

```json
"Statement": [
		{
			"Action": "execute-api:ManageConnections",
			"Resource": "*",
			"Effect": "Allow"
		}
	]
```

- Click **Save** to save the changes.