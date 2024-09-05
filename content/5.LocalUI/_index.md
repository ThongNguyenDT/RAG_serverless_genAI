---
title: "Setup UI on local"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

## Install Node.js

Visit the Node.js homepage and download the version suitable for your device:

[Node.js — Run JavaScript Everywhere](https://nodejs.org/en)

## Open Project in VS Code

- Open the terminal.
- Navigate to the folder containing your code.

Run the following command to open the project in VS Code:

```bash
code .
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image.png)

## Install Packages

Run the following command to install the necessary packages:

```powershell
npm i
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image.png)

## Local Setup

Run the following command to start the project in development mode:

```powershell
npm run dev
```

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%201.png)

Open your browser and go to the ***local*** link:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%202.png)

Create an ***appconfig.json*** file in the ***public*** folder:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%203.png)

Content of ***appconfig.json***:


```json
{
    "inferenceURL": "<YOUR Interface Lambda URL>>",
      "websocketURL": "<YOUR WebSocket URL>",
      "websocketStateTable": "<YOUR WebSocket DynamoDB StateTable tableName>",
      "stackName": "<StackName>",
      "region": "<YOUR REGION>",
      "bucketName": "<YOUR Document Bucket Name>",
      "auth": {
        "user_pool_id": "<YOUR USER POOL ID>",
        "aws_region": "<YOUR REGION>",
        "user_pool_client_id":"<YOUR USER POOL CLIENT ID>",
        "identity_pool_id": "identityPoolId",
        "standard_required_attributes": ["email"],
        "username_attributes": ["email"],
        "user_verification_types": ["email"],
        "password_policy": {
          "min_length": 8,
          "require_numbers": true,
          "require_lowercase": true,
          "require_uppercase": true,
          "require_symbols": true
        },
        "unauthenticated_identities_enabled": true
      },
      "version": "1",
      "storage": {
        "bucket_name": "<YOUR Document Bucket Name>",
        "aws_region": "<YOUR REGION>"
      }
}
```

You need to fill in the known information here. The `<StackName>` is the name of your project.

### UI Testing

Visit [Localhost:5173](http://Localhost:5173) to view the web interface:

![image.png](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%204.png)

{{% notice tip %}} 
❗ Note: After each change to `appconfig.json`, you need to terminate `npm run dev` using the key combination **ctrl+c** → **y** → **enter** and then run `npm run dev` again to apply the configuration!
{{% /notice %}}