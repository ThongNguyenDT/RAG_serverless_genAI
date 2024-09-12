---
title: "Test Interface Lambda URL"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 8.3.2 </b> "
---

After setting up the Lambda URL, you will have an **inferenceURL** as shown below:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%208.png)

### Update `appconfig.json`

You need to update the **inferenceURL** in the ***appconfig.json*** file to match the URL you have set up. This is a crucial step to ensure that your system is configured correctly.

Open the ***appconfig.json*** file and replace the **inferenceURL** value with the new URL you received from the Lambda setup step.
