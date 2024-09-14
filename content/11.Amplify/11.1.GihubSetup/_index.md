---
title: "Create a Github Repository"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 11.1. </b> "
---

## Step 1: Access Github

To get started, you need to visit the main Github website at the following link:

[Github](https://github.com/)

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image.png)

## Create a Github Account

If you don’t already have a Github account, you’ll need to create a new one. Here are the steps to follow:

1. Click on the **Sign Up** button on the homepage.
2. Fill in the required information:
   - Your **Email** address.
   - A **Password** for your account.
   - A **Username** that’s unique.
   - Solve the captcha to verify you're not a robot.
3. Go to your **email inbox** and look for a confirmation email from Github. Click on the link in the email to verify your account.

Congratulations, you’ve successfully created a Github account!

## Sign in to Github

### Logging in on the Github website

Once your account is created, go back to the homepage of Github and log in by:

1. Clicking the **Sign In** button.
2. Entering your login details:
   - **Email** or **Username**.
   - Your **Password**.
3. Completing the captcha verification if prompted.

### Logging in on Git Local (using terminal)

If you are working with git via the terminal, you’ll need to log in to your Github account using the following commands:

```bash
 git config --global user.name "<Username>"
 git config --global user.email "<Email>"
```

## Create a New Repository

After logging in, you will see the Github homepage. Follow these steps to create a new repository:

1. Click the **New** button to start creating a new repository.

   ![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%201.png)

2. On the repository creation screen, fill in the necessary details:

   ![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%202.png)

   - **Repository Name**: This must be a unique name within your account.
   - **Public** or **Private**: For easier deployment, it's recommended to set the repository to **Public**.
   - You can leave the other options as default if you're unsure or don’t need any custom settings.

3. Once completed, click the **Create** button to finalize your new repository.

When the repository is successfully created, you'll see a screen like this:

![Untitled](/images/Amplify%203cbaff98d368481ca9f4263f39f203c8/image%203.png)