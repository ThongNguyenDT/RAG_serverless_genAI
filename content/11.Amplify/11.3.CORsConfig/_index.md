---
title: "Configure CORs"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 11.3. </b> "
---
In this section, you will configure CORs in two places:

- API Gateway, which is where the error you saw earlier occurred.
- Document bucket, which prevents users from uploading documents.

## Configure CORs for API Gateway

If you recall, when configuring API Gateway with websockets, we did not set up CORs. So, where do we configure CORs?

We will configure CORs in the **Lambda Authorizer**.

To do this, follow the same steps we used to configure environment variables earlier.

After accessing the Lambda Authorizer, you will see the following screen:

![Untitled](/images/Lambda%20ac32d7935d7e4ace911b6413f3776394/image%2016.png)

In the **COMMA_SEPARATED_ORIGINS** field, you may have left it blank or entered some arbitrary string. Now, we need to edit this and paste the domain name of the project you deployed here.

❗ Note: Your URL must not end with a “/”.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2019.png)

Save the changes.

Wait a few minutes and reload your web page.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2020.png)

After waiting for a while, you will see that the connection has been successfully established.

## Configure CORs for the User Document Bucket

When you access the **documents** tab, you might see an error like this:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2021.png)

As before, we need to configure CORs for the Document Bucket. Here is the CORs configuration that you can use:

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

Replace the CloudFront URL in the above code with your Amplify link. For example, in my project, it looks like this:

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
            "https://main.d24pacxd5z3be6.amplifyapp.com",
            "http://localhost:5173",
            "https://localhost:5173"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 0
    }
]
```

## Verify Everything

You should now test all the functions of your application after deployment to ensure everything is working properly before releasing the project.

This concludes our tutorial. In the final step, we need to clean up and remove any unused resources from the lab environment.

