---
title: "Setup Inference System"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8. </b> "
---

In this section, we will set up a system to handle user prompts efficiently. Specifically, we will implement the services **Lambda** + *URL Function*, and **Bedrock** to perform the main processing tasks. By doing so, we ensure that user requests are processed quickly and with the flexibility to scale as needed.

### The setup steps include:

1. **[Working with ECR](8.1.ECR/)**  
   In this step, we configure **Elastic Container Registry (ECR)** to store and manage Docker images. This service plays an essential role in making our Lambda functions containerized and portable across different environments.

2. **[Extracting Information from User Data](8.2.UserDataEmbed/)**  
   Here, we work on pulling the necessary data from user input to process through the **Bedrock** service. The data will be formatted and structured for further processing, ensuring that prompts are analyzed and interpreted correctly.

3. **[Setup Interface Lambda](8.3.InterfaceFunc/)**  
   This step help the UI interface throught **Lambda** to communicate with other services like **Bedrock** and handle responses back to the user. Lambda will be configured to accept user prompts and deliver results effectively.

For more details on setting up these services, you can visit the official [AWS documentation for Lambda](https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html).
