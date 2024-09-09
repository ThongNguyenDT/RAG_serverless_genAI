---
title: "Set up WebSocket with API Gateway"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 7.1. </b> "
---

To get started, you need to access the API Gateway service on AWS. This service allows you to manage and configure your APIs with ease.

You can access the API Gateway service using the following link:

[API Gateway Console](https://us-west-2.console.aws.amazon.com/apigateway/home?region=us-west-2)

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image.png)

### WebSocket API

After logging into the API Gateway Console, you'll need to create a new WebSocket API. WebSocket APIs enable two-way communication between the client and server, which is ideal for applications that require real-time updates.

In the API Gateway interface, follow these steps to create a WebSocket API:

1. **Create a WebSocket API**:
   - Click on the button to start the creation process and select **WebSocket API**.
   
   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%201.png)

2. **Name the WebSocket API**:
   - You will need to provide a name for your WebSocket API. This name will be used to identify the API within the system.
   - In the Route selection expression field, enter `request.body.action`. This allows the API to identify actions from incoming requests.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%202.png)

3. **Skip unnecessary steps**:
   - Click **Next** to continue. You may skip other detailed configuration steps if they are not required for your use case.

4. **Provide state name**:
   - At this step, you need to naming your deploy **state** and click **Next** to proceed.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%203.png)

5. **Complete the API creation**:
   - Finally, click **Create API** to complete the creation of your WebSocket API.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%204.png)

Once created, you will see the management interface for the newly created WebSocket API. This interface will allow you to configure and manage routes and other aspects of the API.

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%205.png)

**Next**, you need to access the Stage section to prepare for the following steps in configuring and deploying your WebSocket API.

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%206.png)