---
title: "Add CORS"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 3.6. </b> "
---

### Step 1: Select the bucket containing user documents

### Step 2: Enable CORS

Go to the **Permissions** tab in the document bucket.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/image.png)

Scroll to the bottom, find the **Cross-origin resource sharing (CORS)** section, and click **Edit**.

![Untitled](/images/S3%201e967f97bd6b44cb87a6ba7401452fde/image%201.png)

### Step 3: Configure CORS

Paste the following configuration and save:
```json
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET",
            "HEAD",
            "PUT",
            "POST",
            "DELETE"
        ],
        "AllowedOrigins": [
            "https://dtxxmgtpzjun0.cloudfront.net",
            "http://localhost:5173",
            "https://localhost:5173"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 0
    }
]
```