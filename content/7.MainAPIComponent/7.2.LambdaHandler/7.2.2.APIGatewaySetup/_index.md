---
title: "Handle API route with AWS lambda"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 7.2.2. </b> "
---

After creating your WebSocket API, you need to configure the routes for the API.

## Configure Routes

#### 1. **Access the Route Section**:
   - In the API Gateway interface, select the API you have created.
   - Navigate to the **Routes** section to start configuring routes.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%207.png)

#### 2. **Create a Route**:
   - Click **Create Route** to begin setting up a new route.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%207.png)

#### 3. **Configure the Route**:
   - Name the route. For instance, you can use `$connect` for the `$connect` route.
   - Select **Target** to specify where the API will send data.
   - Enable **Lambda proxy integration**. This allows the API to pass the entire request information to the Lambda function you created earlier.
   - Choose the execution function. Select the WebSocket handler function that you set up in the previous steps.
   - Finally Click **Create Route** to begin setting up a new route.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%208.png)

#### 4. **Create Additional Routes**:
   - Follow the same steps for the following routes:

     - Route **`$default`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%209.png)

     - Route **`$disconnect`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2010.png)

     - Route **`message`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2011.png)

     - Route **`whoami`**:

       ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2012.png)

#### 5. **Deploy the API**:
   - After configuring all the routes, you need to deploy the API to apply the changes.
   - Go to the **Route** section, select **Deploy API** button to proceed your deployment step.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2013.png)

   - Select the current stage name and click **Deploy** to apply the changes.

   ![Untitled](/images/Websocket%202010bee6f85f4f47ad060a21c29577ca/image%2014.png)