---
title: "Clean Up Resources"
date :  "`r Sys.Date()`" 
weight : 99
chapter : false
---

### Why Do We Need to Delete Resources After a Lab Exercise?
Cleaning up AWS resources is crucial for several reasons:

**1. Cost Management:** Unused or unnecessary resources can accumulate and increase costs. By regularly cleaning up, you avoid paying for resources that are not being utilized.

**2. Security:** Unused resources can become vulnerable over time if not properly maintained. Cleaning up helps reduce the attack surface and minimizes potential security risks.

**3. Resource Limits:** AWS imposes quotas on the number of resources that can be provisioned. Removing unused resources ensures that you do not hit these limits, which could affect the deployment of new resources.

**4. Organizational Efficiency:** A clutter-free environment allows teams to manage and monitor active resources more effectively, improving overall efficiency and reducing administrative overhead.

**5. Compliance:** Regular cleanup helps ensure compliance with organizational policies and regulatory requirements, which often mandate minimizing unused or redundant resources.

#### In this exercise, you need to follow the steps below to delete the resources:
- [SQS](SQS/)
- [S3](S3/)
- [DynamoDB](DynamoDB/)
- [ECR](ECR/)
- [Lambda](Lambda/)
- [API Gateway](API_Gateway/)
- [Amplify](Amplify/)
- [System Manager](SystemManager/)
