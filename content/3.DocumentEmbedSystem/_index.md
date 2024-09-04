---
title: "Setting Up a Document Processing System for User Submissions"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

In this section, we will configure a system to receive documents from users, store them, and automatically send notifications. The system utilizes a queue to optimize traffic and enhance processing efficiency.

#### The specific steps are as follows:

1. [Create Dead Letter Queue](3.1.deedletterqueue/)
2. [Create LanceDB Vector Bucket](3.2.lancedbvectorbucket/)
3. [Create Documents Bucket](3.3.documentsbucket/)
4. [Create Document Processing Queue](3.4.documentprocessingqueue/)
5. [Configure Document Bucket to Send Notifications to SQS](3.5.s3notificationtosqs/)
6. [Set Up CORS](3.6.addcors/)