+++
title = "Create an AWS account"
chapter = false
weight = 1
+++

{{% notice tip %}}
For the **AWS Sydney Partner Summit 2020** fullstack workshop, you will be given a pre-built account and can skip this step. Use this procedure if completing this workshop from another event or environment.
{{% /notice %}}

{{% notice warning %}}
Your account must have the ability to create new IAM roles and scope other IAM permissions.
{{% /notice %}}

1. **If you don't already have an AWS account with Administrator access**: [create
one now](https://aws.amazon.com/getting-started/)

1. Once you have an AWS account, ensure you are following the remaining workshop steps
as an **IAM user** with administrator access to the AWS account:
[Create a new IAM user to use for the workshop](https://console.aws.amazon.com/iam/home?region=ap-southeast-2#/users$new)

1. Enter the user details:
![Create User](/images/iam-1-create-user.png)

1. Attach the AdministratorAccess IAM Policy:
![Attach Policy](/images/iam-2-attach-policy.png)

1. Click to create the new user:
![Confirm User](/images/iam-3-create-user.png)

1. Take note of the login URL and save:
![Login URL](/images/iam-4-save-url.png)
