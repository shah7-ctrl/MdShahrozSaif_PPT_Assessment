



### Host a Static Website Using Amazon S3



---



\## 🎯 Objective



The objective of this project is to learn how to host a static website using \*\*Amazon S3\*\* without using any traditional web server. This demonstrates serverless hosting in AWS.



---



\## 🛠️ Services Used



\* Amazon S3

\* AWS Management Console

\* Basic HTML/CSS files



---



\## 📖 Description



In this task, a static website was hosted using an Amazon S3 bucket. The website files (HTML, CSS, images) were uploaded to the bucket, and static website hosting was enabled.



The bucket was configured with:



\* Public access settings

\* Bucket policy for public read access

\* Static website hosting enabled

\* Index document configured (index.html)



After configuration, AWS generated a public website endpoint URL that allows users to access the website through a browser.



---



\## 🚀 Implementation Steps



\### 1️⃣ Create S3 Bucket



\* Logged in to AWS Management Console

\* Navigated to Amazon S3

\* Created a new bucket with a unique name

\* Selected appropriate AWS region



\### 2️⃣ Disable Block Public Access



\* Disabled "Block all public access"

\* Confirmed warning



\### 3️⃣ Upload Website Files



\* Uploaded:



&nbsp; \* index.html

&nbsp; \* style.css (if any)

&nbsp; \* image files (if any)



\### 4️⃣ Enable Static Website Hosting



\* Opened bucket properties

\* Enabled "Static website hosting"

\* Set:



&nbsp; \* Index document: `index.html`

&nbsp; \* (Optional) Error document: `error.html`



\### 5️⃣ Configure Bucket Policy



Added a bucket policy to allow public read access:



```json

{

&nbsp; "Version": "2012-10-17",

&nbsp; "Statement": \[

&nbsp;   {

&nbsp;     "Sid": "PublicReadGetObject",

&nbsp;     "Effect": "Allow",

&nbsp;     "Principal": "\*",

&nbsp;     "Action": "s3:GetObject",

&nbsp;     "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/\*"

&nbsp;   }

&nbsp; ]

}

```



---



\## 🌐 Output



After configuration, AWS generated a \*\*Website Endpoint URL\*\*, which allows the static website to be accessed publicly via browser.



---

