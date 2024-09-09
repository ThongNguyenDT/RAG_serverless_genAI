---
title: "Handle Authorizer API with AWS lambda"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 7.3.2. </b> "
---

In this section, we will configure a **WebSocket Authorizer** to secure and authenticate user connections through API Gateway.

1. **Access WebSocket API**:
   - After creating the **WebSocket API**, navigate to the **Authorizers** section to start setting up an Authorizer for WebSocket.

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2015.png)

2. **Create a New Authorizer**:
   - Click the **Create Authorizer** button to initiate the creation of a new **Authorizer** for WebSocket.
   - In the dialog that appears, provide the necessary details:

     - **Name the Authorizer**: You can choose any name. For example:
     
     ```text
     WebsocketAuthorizer
     ```

     - **Select the region (Region)** and the **Lambda Authorizer function** that was previously created to serve as the authenticator.
   
![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2016.png)

3. **Configure Source Type**:
   - After setting up the Authorizer, you need to configure the **Identity Source Type** as shown in the image to specify the authentication source (e.g., headers or request body).

![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2017.png)


4. **Finalize Setup**:
   - Click the **Create** button to complete the process. Once successfully created, you can use this **Authorizer** to protect and verify connections to your WebSocket API.

This completes the setup for the **WebSocket Authorizer**.