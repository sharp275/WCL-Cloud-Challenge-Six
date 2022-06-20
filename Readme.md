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


Login into AWS and search/choose *SNS*.

<p align="center">
  <img width="1000" src="create sns 1.jpg">
</p>

Type in *mySnsChallengeTopic* under **Topic name**.

Click *Next step*.

<p align="center">
  <img width="1000" src="create sns 2.jpg">
</p>

Click *Create topic*.

<p align="center">
  <img width="1000" src="create sns 3.jpg">
</p>

 Click *Create subscription*.

<p align="center">
  <img width="1000" src="create sub 1.jpg">
</p>

Under **Protocol**, select *Email*.

Under **Endpoint**, type in an appropriate email address.

Click *Create subscription*.

<p align="center">
  <img width="1000" src="create sub 2.jpg">
</p>

Check the email and confirm the subscription.

<p align="center">
  <img src="confirm 1.jpg">
</p>
<p align="center">
  <img src="confirm 2.jpg">
</p>

Search and chooose *S3*.

<p align="center">
  <img width="1000" src="create bucket 1.jpg">
</p>

Click *Create bucket*.

<p align="center">
  <img width="1000" src="create bucket 2.jpg">
</p>

Input a bucket name and then click *Create bucket*.

<p align="center">
  <img  width="1000" src="create bucket 3.jpg">
</p>

Selct the new bucket and Click *Copy ARN*.

Paste the bucket's ARN somewhere for later use.

<p align="center">
  <img width="1000" src="copy ARN.jpg">
</p>

Navigate back to **SNS**/**Topics** and click on *mySnsChallengeTopic*.

<p align="center">
  <img width="1000" src="access policy 1.jpg">
</p>

Click *Edit*.

<p align="center">
  <img width="1000" src="access policy 2.jpg">
</p>

Replace the selected portions with <code>"ArnLike": {"aws:SourceArn": "yourbucketsARN"</code>.

Click *Save changes*.

<p align="center">
  <img width="1000" src="access policy 3.jpg">
</p>

<p align="center">
  <img width="1000" src="access policy 4.jpg">
</p>

Navigate back to **S3**/**Buckets** and click on your bucket.

<p align="center">
  <img width="1000" src="create event 1.jpg">
</p>

Click *Properties*.

<p align="center">
  <img width="1000" src="create event 2.jpg">
</p>

Click *Create event notifications*.

<p align="center">
  <img width="1000" src="create event 3.jpg">
</p>

Input *uploadObjectS3Event* under **Event name**.

Under **Event types**/**Object creation**, check *Put*.

Under **Destination**, select *SNS Topic*, *Choose from your SNS topics* and *mySnsChallengeTopic*.

Click *Save changes*.

<p align="center">
  <img width="1000" src="create event 4.jpg">
</p>

Under **Objects**, click *Upload*.

<p align="center">
  <img width="1000" src="upload 1.jpg">
</p>

Click *Add files* and select an PNG file to upload.

Verify you choose a file.

Click *Upload*.

<p align="center">
  <img width="1000" src="upload 2.jpg">
</p>

<h1>Lab is complete</h1>

<p align="center">
  <img src="validation.jpg">
</p>

<h1><a href="https://youtu.be/qbfdUv-r66Y">Video Example</a></h1>

