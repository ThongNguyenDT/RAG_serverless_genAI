---
title: "Test the configured User Pool"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 6.2. </b> "
---

Replace the following fields in ***appconfig.json*** with the information obtained from the previous steps:

- `<YOUR REGION>`
- `<YOUR USER POOL ID>`
- `<YOUR USER POOL CLIENT ID>`

You can now attempt to create an account and log in on your localhost. If the Cognito configuration steps were done correctly, you will be able to log in and see the following interface:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%205.png)

At this point, things should be working fine. You should also test the **sign out** function to ensure that the system operates correctly:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%206.png)

For this section in ***appconfig.json*** , configure it similarly to the settings in your **user pool**.

```json
"password_policy": {
          "min_length": 8,
          "require_numbers": true,
          "require_lowercase": true,
          "require_uppercase": true,
          "require_symbols": true
        },
```