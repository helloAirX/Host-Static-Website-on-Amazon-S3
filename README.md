
# How to host a  static website on AWS S3

In this project i deployed a static website usingthe Amazon S3.

**Let's get started**

We are going to host a static website built with HTML, CSS and Java Script on S3 

**Step 1** 

- Login to the AWS Console

- Navigate to the S3 and click Create bucket

![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/81280857-bf67-42ca-b98c-182139607f06)


**Step 2** 

- Give your bucket a unique name
- Choose a region
- Select the ACLs disabled (recommended)
- Turn off block all public access (Note: this is not a good practice, but for this tutorial, we will turn it off
- Disable bucket versioning ( we don't need it for now)
- Enable the server-side encryption and choose the Amazon S3-managed keys (SSE-S3) encryption type
- Leave everything as default and click Create Bucket.
  
![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/959e0785-7004-4e6b-9a70-142d4c03a588)

![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/e547dc12-e56e-4f54-9339-4289b61a23af)
![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/47889c15-c26a-4560-a7f2-922b1748ac4a)
![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/571cf2a9-14d7-4800-8f09-ce78e9606401)


**Step 3**

Now that our bucket has been created, we need to upload our Website file. 
Note: You can download a sample website file online
- Click on the bucket we just created.
- Upload the website files to the bucket. You can aslo use drag and drop
- Now that our website file has been uploaded successfully, Let's make a few setting

![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/41655229-3488-43d2-afae-8bc19a7bfa31)


**Step 4** 

- Click on the properties tab and scroll down
- At the Static website hosting option, click edit to change the settings
  
  ![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/70c743a7-a205-4290-b5f8-ee2934f45ba1)
  
- Enable the static website hosting
- Select host a static website as the hosting type
- Input "Index.html" to specify the home or default page of the website.
- Input "error.html" if you have an error page or leave it (It's optional) and save changes.

![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/b4559404-edd9-412c-86f5-075cd438fd17)


**Step 5** 
- Click the permission tab, we need to change some settings to enable our website to be accessed publicly
- Scroll to the bucket policy and click edit

 ![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/a0b8e2f8-651b-457a-ba63-12b674361fda)

- Now let's copy the below policy and paste it into our text box and replace the bucket name with our own

```

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject",
                "s3:GetObjectVersion"
            ],
            "Resource": "arn:aws:s3:::bucket-web-app00/*"
        }
    ]
}

```
![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/2017dccc-0661-472c-9194-54bc4b8d1935)

Click on save. Our bucket is now public and can be accessed by everyone

**Step 6**

- Let's go back to the properties tab

- Navigate to the static website hosting option

- Copy the URL or click on the link to access our website

- ![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/4de97232-57f3-42b8-8c3f-56f71106cb3e)

Viola! Our website is up and running


This is a screenshot of the test website 

![image](https://github.com/helloAirX/Static-Website-on-Amazon-S3/assets/113798625/0b9263e5-84be-4e67-a927-213b24f88909)


