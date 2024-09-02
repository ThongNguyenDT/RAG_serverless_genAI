---
title: "Preparation"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

Before diving into the main part of this workshop, it's essential to get the necessary preparations in place. In this session, we will be working with the [RAG Serverless GenAI](https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS.git) project. This project is designed to automate the deployment of a serverless generative AI application on AWS using the AWS Cloud Development Kit (CDK). However, for the purpose of this workshop, we will demonstrate how to set up and deploy this project using the AWS Management Console instead of the CDK.

The AWS Management Console provides a user-friendly graphical interface for managing AWS resources. By following the console-based approach, we can gain a deeper understanding of the underlying infrastructure, configuration settings, and the deployment process, giving us more control over each step.

To get started, follow these steps:

#### Step 1: Clone the Repository

First, you need to clone the repository that contains the project files. This will allow you to access all the necessary code and resources required for the deployment.

```bash
git clone https://github.com/ThongNguyenDT/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS-for-Workshop.git
cd RAG_serverless_genAI
```

Once the repository is cloned, navigate to the project directory using the command line or your file explorer.

#### Step 2: Review the Project Structure
Before moving forward, take some time to review the project structure. Familiarizing yourself with the contents of the repository will help you understand the various components and how they fit together.

In the project root directory, you will find several important files and folders:

- **lib/**, **bin/**: Contains the CDK stack definitions, which automate the creation of AWS resources. For this workshop, we'll reference these definitions but will be creating the resources manually via the AWS Management Console.
- **lambda/**: Contains the code for AWS Lambda functions that are used in the application.
- **lib/**: Also include the source config for your bedrock - genAI serverless service
- **README.md**: Provides an overview of the project and instructions on how to deploy it using CDK.


This overview gives you a sense of what the project does and what components will be involved in the deployment. Once you're comfortable with the structure, proceed to the next steps in the AWS Management Console.