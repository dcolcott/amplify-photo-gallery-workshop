+++
title = "Create a Cloud9 Workspace"
chapter = false
weight = 10
+++

AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes pre-packaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don't need to install files or configure your development machine to start new projects.

{{% notice note %}}
For the **AWS Sydney Partner Summit 2020** Fullstack Workshop, all resources must be deployed in the **Sydney (ap-southeast-2)** region.
{{% /notice %}}

{{% notice info %}}
Ad blockers, JavaScript disablers, and tracking blockers should be disabled for
the cloud9 domain, otherwise connecting to the workspace might be impacted.
{{% /notice %}}

### Create a new environment

1. Go to the [Cloud9 web console](https://ap-southeast-2.console.aws.amazon.com/cloud9/home?region=ap-southeast-2).
1. At the top right corner of the console, make sure you're using the Sydney (ap-southeast-2) region.
1. Select **Create environment**
1. Name it `fullstack-workshop` and go to the **Next step**
1. Select **Create a new instance for environment (EC2)** 
1. Select **Other Instance type** and pick **t2.medium**
1. Leave the remaining settings as they are, and click **Next step**
1. Click **Create environment**

{{% notice note %}}
You will be redirected to the AWS Cloud9 development environment, this will take a minute to initialise.
{{% /notice %}}

### Clean up the layout

When the environment comes up, customize the layout by closing the **welcome tab**
and **lower work area**, and opening a new **terminal** tab in the main work area:
![c9before](/images/c9before.png)

Your workspace should now look like this:
![c9after](/images/c9after.png)

If you like this theme, you can choose it yourself by selecting **View / Themes / Solarized / Solarized Dark**
in the Cloud9 workspace menu.
