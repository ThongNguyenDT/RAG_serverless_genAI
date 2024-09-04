---
title: "Dead letter Queue"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---
In this guide, we will walk through the steps to create a **Dead Letter Queue** (DLQ) using **Amazon Simple Queue Service** (SQS).

### Step 1: Access SQS in AWS Console

First, log into the **AWS Management Console** and navigate to the **SQS** service. The interface will look like this:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled.png)

### Step 2: Create a New Queue

Click on **Create Queue** to start creating a new queue.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%201.png)

### Step 3: Configure Dead Letter Queue

In this step, we will set up a **Dead Letter Queue** with the following configurations:

- **Dead Letter Queue Name:** Choose a suitable name for easy management.
- **Visibility Timeout:** Set it to **300 seconds** to allow enough time for message processing.
- Keep other settings as default.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%202.png)

### Step 4: Create Queue

Once all the information is filled in, click **Create Queue** to finalize the process.

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/Untitled%203.png)

### Result

After completing the steps, you will see the queue created successfully as shown below:

![Untitled](/images/SQS%204c16c634931e432886dad2df7a7c65af/image.png)

---

By following these steps, you've successfully created a **Dead Letter Queue** in AWS SQS, helping improve the stability and efficiency of your system by handling undeliverable messages.
