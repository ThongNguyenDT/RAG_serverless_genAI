---
title: "Document Upload Test"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 10.2. </b> "
---

When the document upload window appears as shown below, it means your document upload process is working.

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2010.png)

If you encounter a connection error, check your browser's console. If you see a timeout connection message, this is likely a first-time connection issue, and subsequent attempts should work fine.

If you encounter a CORS error, verify that the bucket names in your **appconfig.json** are correct. If you've just enabled CORS, wait a moment for the changes to take effect.

If everything is set up correctly, the UI should display as follows:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2011.png)

---

## File Upload Test

Now, try uploading a file. During the upload, you will see the following two notices:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2012.png)

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2013.png)

Once the upload is complete, the result will display on the UI as follows:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2014.png)

Refresh the page to check if the server has updated. If everything runs smoothly, you will see the following result:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2015.png)

---

## SQS Check

Ensure that SQS is activated. If SQS has received a message from S3 and forwarded it to Lambda, you will see a message in the **Messages available** section if the Lambda function is in cold start mode.

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2016.png)

This confirms that the Lambda function has been successfully triggered:

![Untitled](/images/Local%20test%20ce0d4bd8857e41d8b260be36d2383dc9/image%2017.png)
