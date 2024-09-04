---
title: "Add Notification To SQS"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

### Step 1: Select the bucket containing user documents

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%206.png)

### Step 2: Go to the **Properties** tab

Scroll down and find the **Event notifications** section.

Click **Create Event notifications**.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%207.png)

### Step 3: Configure the Event Notification

- Name the event.
- Select **Suffix** (file type).
- Choose the actions that trigger the event:
    - Here, we select all create and delete actions.
- Select the target for notifications, in this case, the document SQS.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%208.png)

### Step 4: Testing the Event Notification

After creating the event, you can test it by creating a PDF file, uploading it to the bucket, and checking for messages in SQS.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%209.png)

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/Untitled%2010.png)

We can see that there are 2 messages in the document queue. After some time, they will appear in the dead-letter queue and disappear from the document queue.
