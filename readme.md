<div style="display: flex; flex-direction: column; align-items: center;">
    <image src="static/images/ai.png" width=150></image>
    <H1 >RAG_serverless_genAI</h1>
</div>


![AWS](https://img.shields.io/badge/AWS-FF9900?logo=amazon-aws&logoColor=white) ![Lambda](https://img.shields.io/badge/AWS%20Lambda-FF9900?logo=aws-lambda&logoColor=white) ![API Gateway](https://img.shields.io/badge/AWS%20API%20Gateway-FF4B00?logo=amazon-api-gateway&logoColor=white) ![Cognito](https://img.shields.io/badge/AWS%20Cognito-FF4B00?logo=aws-cognito&logoColor=white) ![Amplify](https://img.shields.io/badge/AWS%20Amplify-FF4B00?logo=aws-amplify&logoColor=white)

## 🚀 **Overview**

**RAG_serverless_genAI** is a cutting-edge project leveraging **AWS Bedrock** to build a serverless, real-time AI application. This project uses **AWS API Gateway WebSocket**, **AWS Lambda**, **AWS Cognito**, and **AWS Amplify** to create a scalable and secure architecture for generative AI solutions.

## 🛠️ **Architecture**

![Architecture Diagram](https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS/raw/main/assets/architecture.png)

1. **AWS Bedrock**: Foundation for generative AI capabilities.
2. **API Gateway WebSocket**: For real-time communication between the client and server.
3. **AWS Lambda**: Serverless functions to handle business logic.
4. **AWS Cognito**: Secure user authentication and authorization.
5. **AWS Amplify**: Simplifies the front-end development and deployment.

## 📋 **Features**

- **Scalable**: Leverages the power of AWS services for scalability and performance.
- **Secure**: Uses AWS Cognito for secure authentication and authorization.
- **Real-time**: WebSocket API enables real-time communication.
- **Serverless**: Built using serverless architecture for reduced operational overhead.

## 🚀 **Getting Started**

### **Prerequisites**

- AWS Account
- AWS CLI installed
- NodeJS >= v18.18.2 and NVM for node version management
- Docker
- AWS Cloud Development Kit (CDK) cli >= 2.142.1

### **Self Deploy to AWS**

**To self deploy the application**, follow the instructions in the [workshop](https://thongnguyendt.github.io/RAG_serverless_genAI).

or

Folow this Installation for automatic deploy
### **Installation**
1. **Clone the repository**:
    
    ```bash
    git clone https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS.git
    cd RAG_serverless_genAI
    ```
    
2. **Configure AWS CLI**:
    
    ```bash
    aws configure
    ```

    Input your username pass work

1. **Install dependencies**:
    
    ```bash
    npm install
    ```
    
2. **Config**:
    
    <p style="font-weight: 800; color: darkcyan; margin-top:30px;">Supported Regions</p>

    This sample only supports regions where Bedrock is available and at least one Embedding model is present. As of July 2024, this sample supports.
    
    ```json
    us-east-1
    us-east-2
    us-west-2
    eu-central-1
    eu-west-2
    eu-west-3
    ap-south-1
    ap-southeast-2
    ap-northeast-1
    ca-central-1
    sa-east-1
    ```
    
    <p style="font-weight: 800; color: darkcyan; margin-top:30px;">Change support region</p>
    
    You can switch the default region  by changing the env or  config file at `/bin/serverless-rag-on-aws-stack.ts`.

    <p style="font-weight: 800; color: darkcyan; margin-top:30px;">Embedding Configuration</p>

    You can switch the default embedding model by changing the config file at `lib/llm-config.json`.
    
    Once the sample is deployed you should NOT switch the embedding model. Changing it may lead to errors or unexpected results in your semantic search.
    
    <p style="font-weight: 800; color: darkcyan; margin-top:30px;">Sample Configuration</p>

    ```json
    {
        "us-west-2":{
            "embedding":{
                "model":"amazon.titan-embed-text-v1",
                "size":1536
            }
        },
    ...
    }
    ```

    <p style="font-weight: 800; color: darkcyan;">Changing the Default Prompt Dynamically</p>

    To change the default prompt dynamically for all users, follow these steps:
    - Open the [`prompt-templates.yml`](https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS/blob/main/lib/prompt-templates.yml) file.
    -  Update the prompt templates as per your requirements.
    -  Save the changes.
    -  Run the [`update-default-prompt-templates.ts`](https://github.com/aws-samples/Serverless-Retrieval-Augmented-Generation-RAG-on-AWS/blob/main/update-default-prompt-templates.ts) script using the following command:

    <p style="font-weight: 800; color: darkcyan;">Deploy</p>

    * For greater access to LLMs (at the time of writing), deploy the stack in the `us-west-2` region.
    * Deploying for the first time should take around 20 minutes (depending on your upload speed)
    <br>
    <br>
    ```bash
    cdk deploy
    ```



## 🧩 **Contributing**


### **Contributor**: [Thong Nguyen](https://github.com/ThongNguyenDT) ![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?logo=github)

## 🔗 **Useful Links**

- [AWS Bedrock Documentation](https://docs.aws.amazon.com/bedrock)
- [AWS API Gateway](https://docs.aws.amazon.com/apigateway)
- [AWS Lambda](https://docs.aws.amazon.com/lambda)
- [AWS Cognito](https://docs.aws.amazon.com/cognito)
- [AWS Amplify](https://docs.amplify.aws)

## 📜 **License**

This project is licensed under the MIT License - see the [LICENSE](https://github.com/yourusername/RAG_serverless_genAI/blob/main/LICENSE) file for details.

## 🌐 **Source Repository**

Find the complete source code [here](https://github.com/yourusername/RAG_serverless_genAI).
