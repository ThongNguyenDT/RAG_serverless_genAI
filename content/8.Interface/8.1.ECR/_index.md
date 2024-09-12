---
title: "Working with ECR"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 8.1. </b> "
---

### Docker setup

Download Docker if you haven’t already via the link below:

[Docker Download](https://www.docker.com/)

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image.png)

Download the version that matches your device.

After installation is complete, you need to log in to Docker Hub.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%201.png)

You can log in using Google, Github, or your personal account.

This step is optional.

Next, navigate to **Images → Local**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%202.png)

Currently, there are no images available. We will push the image of **interface lambda** to **ECR**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%203.png)

### Docker CLI test

Open the terminal and run the following command:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%204.png)

Now you have successfully set up Docker.

### Create ECR private **repository**

Access **ECR** through the console:

[Elastic Container Registry - Home (amazon.com)](https://us-east-1.console.aws.amazon.com/ecr/home?region=us-east-1)

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%205.png)

Proceed to create a new repository.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%206.png)

In the **Visibility settings**, you can choose between *Private* or *Public*.

{{% notice tip %}}
❗ Based on my testing, **Lambda** does not allow using public images.
{{% /notice %}}


Name the repository as you like, ensuring it follows AWS naming conventions.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%207.png)

Finally, click **Create**.

### Docker image build

Navigate to the folder where your **Lambda** code is stored.

You can find the source code on the project's Github page linked at the start of the tutorial.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%208.png)

In the ECR repository you just created, there will be detailed instructions on how to build and push the code. Simply copy and paste them into the terminal from the folder containing the source code.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%209.png)

ECR supports many operating systems. Since I’m using **Windows**, I will run the following commands.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2010.png)

If you encounter issues like I did, you can check this [StackOverflow thread](https://stackoverflow.com/questions/70393195/get-ecrlogincommand-is-not-recognized-as-the-name-of-a-cmdlet-function-scrip). You need to install AWS CLI tools before using these commands.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2011.png)

If you face login issues, you can refer to [this AWS forum](https://repost.aws/questions/QUKqrdl3lfR9ON8KnSP6FbzQ/getting-error-while-pushing-images-to-public-ecr) or [this StackOverflow solution](https://stackoverflow.com/questions/60807697/docker-login-error-storing-credentials-the-stub-received-bad-data).

{{% notice tip %}}
Personally, when using **Windows**, I needed to install extra packages and faced some errors. \
You can try running the Linux guide commands in **Powershell** as I did.
{{% /notice %}}

After logging in successfully:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2012.png)

Once logged in, build the image:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2013.png)

After building is complete:

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2014.png)

### Docker push to ECR

Next, tag the image correctly to match your repository before pushing it to **ECR**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2015.png)

Finally, push the image to **ECR**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2016.png)

All done!

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%2017.png)

### ECR with interface lambda

Repeat the steps:

- Create the repository
- Build the image
- Push the image

Do the same for **Interface Lambda**.

![Untitled](/images/ECR%208af9d63a369b4df2bdfb2e62b89d81a0/image%203.png)