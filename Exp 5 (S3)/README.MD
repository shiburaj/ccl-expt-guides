# Experiment 5 : S3

***Software*** : AWS Academy

***Objective*** : To deploy a static portfolio app/ any custom static app made by you to `S3`. 

***Requirements*** : Each student must deploy your static html/css website on S3 service. 

***Sample App*** : Sample app for reference DONOT use it. use your own repo.

[https://github.com/shiburaj/my-portfolio-static](https://github.com/shiburaj/my-portfolio-static)

## Steps to Start AWS Academy Lab
1. Go to AWS Academy Website [Click Here](https://awsacademy.instructure.com/login/canvas)
2. Login with your AWS Academy Credentials or use Forgot Password if you cant remember your password.
3. Go to the Cloud Foundations Course
4. Click Modules and scroll down to Sandbox
5. After opening sandbox click the button to open sandbox in a new window.
6. Click the `Start Lab` button to start the Lab.
7. After sometime when the lab starts the timer of 3hrs will start.
8. Click the `AWS` button to go to your AWS Dashboard.

## ***Steps to Deploy*** :
1. Go to Services >> Storage >> S3
2. Click the `Create Bucket` button
3. Give a Bucket Name (should be unique)
4. Remove the check box infront of Block Public Access
5. Create Bucket
6. Use the Upload Button to upload your static website files to the S3 bucket.
7. Go to `Properties` tab and scroll down and enable `Static Website Hosting` by editing it and adding the starting page.
8. Go to Permissions tab and edit the bucket policy and add the following json code after editing it as per your bucket arn.
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YourBucketName/*"
        }
    ]
}

```
9.  Go to Properties tab and Scroll Down to Static Website Hosting for the domain name of the website.
10. Open it to check out your website.
11. Take screenshot of the `bucket contents` and `the website`.