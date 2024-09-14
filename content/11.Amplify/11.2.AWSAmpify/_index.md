---
title: "Deploy an Application on AWS Amplify"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 11.2. </b> "
---

## Push UI Code to Github

The first step is to copy the UI folder out of your project to isolate it from the project's main git repository.

Here’s the location of the UI folder:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%204.png)

After copying the UI folder to a new location, open your project in the terminal:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%205.png)

Run the following commands to push your project to Github:

```bash
git init
```

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%206.png)

Next, commit the source with a message:

```bash
git commit -m "first commit"
```

If you see a message saying some files haven’t been included in git yet:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%207.png)

Add all files to git:

```bash
git add .
```

Commit the source code:


```bash
git commit -m "UI upload"
```

After running this command, the files added to git will be displayed in the terminal.

Now, add the remote repository link to push the code:

```bash
git remote add origin <đường dẫn trong ảnh>
```

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%203.png)

Push the code to Github with the following command:

```bash
git push -u origin main
```


After pushing, visit your Github repo to check if the source code has been successfully uploaded.

## Connect AWS Amplify to Github

Now, go to the AWS Amplify console:

[Amplify Console](https://us-west-2.console.aws.amazon.com/amplify/apps)

Click the **Create new App** button:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%208.png)

In the app creation interface, choose the type of app. AWS Amplify supports various types of apps, and for this project, we are using **Vite**.

Next, choose the source code location:

- Select **Github**.
- Click **Next** to proceed with connecting to your Github account.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%209.png)

A window will appear asking you to grant access to your Github account:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2010.png)

Click the green button to grant access.

If your account is part of an organization, select the owner of the repository. If not, you can skip this step if it’s a personal account or newly created repo.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2011.png)

Click **Install**.

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2012.png)

Verify MFA if needed.

Once authentication is completed, the window will close, indicating that the connection between Github and AWS Amplify is successful.

## Deploy the Application

Next, we will deploy the application.

After successful authentication, you will be able to see your repositories listed:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2013.png)

Select your repository and click **Next**.

{{% notice tip %}}
❗ Make sure to choose the correct branch containing the source you want to deploy. AWS Amplify will automatically redeploy the branch whenever there are changes.
{{% /notice %}}

Next, give your app a name and click **Next**:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2014.png)

Review your settings and click **Save**:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2015.png)

This will bring you to the deployment interface:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2016.png)

Once the deployment is completed:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2017.png)

Visit the generated URL and log in with the account you just created locally to check the deployed app.

If you encounter an issue connecting to the backend:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%2018.png)

We will address this issue in the next step.