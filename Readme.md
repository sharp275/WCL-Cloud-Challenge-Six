<h1 align="center">
Whizlabs Challenge League
</h1>

<h2 align="center">
Challenge Lab Six
</h2>

<h2 align="center">
Configure SNS Email Notification on S3 Bucket Event
</h2>

---

WhizLabs is running a cloud challenge between May and July 2022.  The challenge is to complete various tasks in either AWS, GCP, or Azure to test cloud skills.  Following is my solution to challenge lab four.

---
<h3>From Whizlabs</h3>

[Cloud Challenge Details](inst.jpg)

>In this challenge, your Amazon SNS and Amazon S3 skills are put to the test. You'll be given a requirement and you have to reach it using your knowledge of Amazon SNS and Amazon S3. This Challenge will help you understand the real-time scenarios. 
A company XYZ is deploying a new web application that helps customers to upload files to S3 Bucket. As a part of the infrastructure, the Administrator needs to be notified via Email whenever an object is put into their S3 bucket. Now your challenge is to setup the AWS architecture to perform this operation. 
>
>Follow the below instructions to complete this challenge.
>
>1. Create a Standard Amazon SNS topic named **mySnsChallengeTopic**.
>2.	Add an Email subscription to that topic and verify it.
>3.	Create a S3 bucket with a globally unique name.
>4.	Update the Amazon SNS Topic **Access Policy** and add permission for S3 to publish messages to SNS Topic that you have created.
>5.	Now, Create a S3 Notification Event named **uploadObjectS3Event**. 
>     1. Select S3 Event type as Put.
>     2. Select your SNS Topic as event Destination.
>6.	Test the Configuration by uploading any sample PNG image file to S3 Bucket and see if you're notified. 

---
<br><br>
Download the zip file and extract index.html and error.html

Login into AWS and search/choose *S3*.

<p align="center">
  <img width="1000" src="choose s3.jpg">
</p>

Click *Create bucket*.

<p align="center">
  <img width="1000" src="create bucket 1.jpg">
</p>

Enter a globally unique bucket name.

Uncheck *Block all public access*.

Check the box to acknowledge the bucket being public

Click *Create bucket*.

<p align="center">
  <img width="1000" src="create bucket 2.jpg">
</p>

Open notepad or any other text editor.

Copy and paste the bucket policy into it.

Back in AWS, select the bucket and click *Copy ARN*.

Replace *S3_BUCKET_ARN* with the actual ARN in the text editor.

Click on your bucket.

<p align="center">
  <img width="1000" src="copy arn.jpg">
</p>

Click *Upload*.

<p align="center">
  <img width="1000" src="upload 1.jpg">
</p>

Click *Add files*.

<p align="center">
  <img width="1000" src="add files.jpg">
</p>
Select both index.html and error.html and click open.

Both files will appear in **Files and Folders**.

Check *Upload*.

<p align="center">
  <img src="upload 2.jpg">
</p>

Navigate to the bucket and click *Permissions*.

<p align="center">
  <img width="1000" src="permissions 1.jpg">
</p>

Under **Bucket policy**, click *Edit*.

<p align="center">
  <img  width="1000" src="permissions 2.jpg">
</p>

Delete the current policy.

<p align="center">
  <img width="1000" src="permissions 3.jpg">
</p>

From the text editor, copy and paste the policy then click *Save chnages*.

<p align="center">
  <img width="1000" src="permissions 4.jpg">
</p>

Click *Properties*.

<p align="center">
  <img width="1000" src="website 1.jpg">
</p>

Under **Static website hosting** click *Edit*.

<p align="center">
  <img width="1000" src="website 2.jpg">
</p>

Select *Enable* and *Host a static website*.

For **Index document**, type *index.html*.

For **error document**, type *error.html*.

Click *Save changes*.

<p align="center">
  <img width="1000" src="website 3.jpg">
</p>

<h1>Lab is complete</h1>

<p align="center">
  <img src="validation.jpg">
</p>

<h1>Video Example</h1>

[![Video Example](vid.jpg)](https://youtu.be/1KOqOgfG8HQ)
