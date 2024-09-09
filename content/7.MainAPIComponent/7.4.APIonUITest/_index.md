---
title: "Test API on the interface"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 7.4. </b> "
---

Finally, replace the following items in ***appconfig.json*** with the information you have from the previous steps:

- `<YOUR WebSocket URL>`
- `<YOUR WebSocket DynamoDB StateTable TableName>`

### On the localhost page

On the homepage, press **F12** to open the **DevTools** interface, navigate to the **Console** tab to check the log.

After the **connecting to backend** panel on the interface disappears, if you see the log in the following format, it means you have succeeded.

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%207.png)

