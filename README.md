<h1 align="center">Hosting Static Website on S3</h1>
  

<B>PRE-REQUISITES</B>
  <br />

To complete this project, you will need the following: 
- AWS Account
- Static Website 
- Knowledge of Basic Linux Navigation and File Management. 
Here is a diagram to provide a sense of what the file structure of the project will look like once you have completed the tutorial: 
 
  
<B>Step 1 — Login to your AWS console</B>
 <p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/login.png">
</p>

<b>Step 2 — Navigate to S3</b>
 <p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/s3.png">
</p>
<b>Step 3 - Click on create Bucket</b>

-Enter Bucket Name
- Select your Region
- Unclick Block all public access
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/block all.png">
</p>
-leave the rest to default and click Create Bucket
<b> Step 4 - Upload file to the bucket</b>
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/upload.png">
</p>

<b>Step 5 -  Got to properties</b>
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/properties.png">
</p>
- Scroll to the end of page you will find Static website hosting
- Click on Edit
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/create bucket.png">
</p>
- Enable Static website hosting
-Hosting type:Host a static website
-Index document: enter your website name (mine is index.html)
- Click save changes
<b>Setp 6 - Assign Bucket policy</b>
- Go to permissions
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/permissions.png">
</p>
- Go to bucket policy and click edit 

'''diff
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "PublicReadGetObject",
			"Effect": "Allow",
			"Principal": "*",
			"Action": "s3:GetObject",
			"Resource": "arn:aws:s3:::Bucket-name/*"
		}
	]
}
'''
- Thing you need to know:
-"Effect": "Allow"
<p> Tell whether to allow of deny. In this case allow.</p>
-"Principal": "*"
<p> Defines who can perform the operation. "*" or "wildcard" mean anyone can perform this operation.</p>
-"Action": "s3:GetObject"
<p>Define the level of acces to the bucket. In this case the user can perform only get object operation.</P>
-"Resource": "arn:aws:s3:::Bucket-name/*"
<p>Define on what resource the specified permission are to be applied. In this case on your s3 bucket.<b> Replace "Bucket-name" with the name of your bucket.</b><p>
- Click Save changes
<b>Step 7 - Go Back to Properties</b>
<p align="center">
  <img width="600" src="https://github.com/jairajpatil8/Hosting-static-website-on-s3/blob/main/s3-images/url.png">
</p>
- Navigate to Static website hosting, and your should have your AWS Hosted Public URL ready.
- If you followed everything correctly your website should be live .



