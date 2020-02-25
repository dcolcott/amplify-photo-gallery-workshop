+++
title = "Adding Cloud Storage"
chapter = false
weight = 30
+++

We'll need a place to store all of the photos that get uploaded to our albums. Amazon Simple Storage Service (S3) is a great option for this and Amplify's Storage module makes setting up and working with S3 very easy.

### Configuring and adding storage

First, we'll use the Amplify CLI to enable storage for our app. This will create a bucket on Amazon S3 and set it up with appropriate permissions so that users who are logged in to our app can read from and write to it. We'll also allow guests to read from the bucket, in case we ever want to allow albums to be made public. 

1. **From the photoalbums directory, run** `amplify add storage`

2. **Select 'Content'** at the prompt

3. **From 'Please provide a friendly name for your resource:'** enter: **photoalbumsstorage**

4. Accept the default value for '**Please provide bucket name:'**

4. **Chose Auth and guest users** when asked who should have access. Configure it so that **authenticated users** have access with **create/update, read, and delete access** (use the spacebar to toggle on/off, the arrow keys to move, and Enter to continue) and **guests** have **read permission**.

5. **Select _No_** when asked to add a Lambda Trigger for your S3 Bucket (we will do this next).


    Here is sample output with responses:

    ```text
    $ amplify add storage


    ? Please select from one of the below mentioned services:
    
    Content (Images, audio, video, etc.)


    ? Please provide a friendly name for your resource that will be used to label this category in the project: photoalbumsstorage


    ? Please provide bucket name: <accept the default value>


    ? Who should have access: Auth and guest users


    ? What kind of access do you want for Authenticated users? 
    ◉ create/update
    ◉ read
    ◉ delete


    ? What kind of access do you want for Guest users? 
    ◯ create/update
    ◉ read
    ◯ delete


    ? Do you want to add a Lambda Trigger for your S3 Bucket? 
    No
    ```

Run `amplify push` and confirm you'd like to continue with the updates

### Configure S3-Triggered Lambda to create Image Thumbnails.
In this section we will update the Storage to add a triggered Function (Lambda) that detects when a image is uploaded to an album and creates a Thumbnail for display.

1. **From the photoalbums directory, run** `amplify update storage`

1. **Select 'Content'** at the prompt

1. **Chose Auth and guest users** enter through the permissions for Authorized and Guest users as we don't want to change them from the previous step.

1. **Select _Yes_** when asked to add a Lambda Trigger for your S3 Bucket. This will create a Lambda function that will get triggered by S3 Events. Later on we'll use this function for photo processing.

1. Select **Create a new function**
  
1. **Select _No_** when asked to edit a the Lambda function. We'll do this at a later step in the workshop.

    Here is sample output with responses:

    ```text
    $ amplify update storage


    ? Please select from one of the below mentioned services:
    
    Content (Images, audio, video, etc.)

    ? Who should have access: Auth and guest users

    ? What kind of access do you want for Authenticated users? 
    ◉ create/update
    ◉ read
    ◉ delete

    ? What kind of access do you want for Guest users? 
    ◯ create/update
    ◉ read
    ◯ delete

    ? Do you want to add a Lambda Trigger for your S3 Bucket? Yes

    ? Select from the following options 
    Create a new function 

    ? Do you want to edit the local S3Triggerxxxxxxx lambda function now? (Y/n) 
    No
    ```

We'll modify this Lambda function later, for now we want to create the S3 bucket to host our photos.

Now we'll have Amplify modify our cloud environment, provisioning the storage resources we just added.

1. **Run** `amplify push` 
1. **Press Enter** to confirm the changes.
1. Go to the [AWS CloudFormation](https://ap-southeast-2.console.aws.amazon.com/cloudformation/home?region=ap-southeast-2) console and see the nested stacks and resources as they are being created.
1. Wait for the provisioning to finish.


{{% notice info %}}
Above, we're telling Amplify to allow read access for guest users so that if we ever want to allow albums to be made public, we won't need to make any further changes to the way the S3 bucket permissions are configured. However, we won't be making albums publicly readable as part of this workshop.
{{% /notice %}}

{{% notice tip %}}
You can read more about Amplify's Storage module [here](https://aws-amplify.github.io/amplify-js/media/storage_guide).
{{% /notice %}}
