---
title: "Set up User Pool"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 6.1. </b> "
---

## Access the Cognito Service

In the console window, navigate to the Cognito service:

[Amazon Cognito > us-east-1 | Cognito | us-east-1](https://us-east-1.console.aws.amazon.com/cognito/v2/home?region=us-east-1)

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image.png)

### Cognito User Pool

We will use email for login.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%201.png)

Click **Next**.

For password settings, you can choose according to your preference.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%202.png)

MFA is not used. You can select other options as needed.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%203.png)

Click **Next** and continue to click **Next**.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%204.png)

Select as shown and click **Next**.

At this step, on the left is the SNS service for businesses. In this lab, you only need to send a test message.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%205.png)

You need to name your user pool.

To enable access through Amplify, check the checkbox as shown.

If you do not need a domain, you can leave it at the default.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%206.png)

You need to configure the domain name according to Cognito's guidelines.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%207.png)

Select **Public** to allow login from Amplify.

- App name can be set as desired.
- The callback URL is the URL to which you will be redirected after login, which can be your Amplify URL.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%208.png)

Click **Create** to continue.

After completing the setup, you will see:

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%209.png)

Note the following two items:

- **User Pool ID**

In the **App integration** section, scroll down to **App clients and analytics**.

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%2010.png)

- **Client ID**

![Untitled](/images/Cognito%20603c5cec4976409396c6e310eda31795/image%2011.png)

These two items will be used for configuration in the next section.
