#### S3 Upload Email Notification using AWS Lambda and SNS



---



\## 🎯 Objective



To implement an \*\*event-driven architecture\*\* in AWS where an email notification is automatically sent whenever a file is uploaded to an S3 bucket.



This project demonstrates how AWS services integrate using triggers and messaging systems.



---



\## 🧠 Simple Definition



When a file is uploaded to an S3 bucket →

S3 triggers a Lambda function →

Lambda publishes a message to SNS →

SNS sends an email notification.



---



\## 🏗️ Architecture Overview



```

User Uploads File → S3 Bucket

&nbsp;       ↓

S3 Event Trigger

&nbsp;       ↓

AWS Lambda Function

&nbsp;       ↓

SNS Topic

&nbsp;       ↓

Email Notification

```



---



\## 🛠️ AWS Services Used



\* \*\*Amazon S3\*\* – Stores uploaded files

\* \*\*AWS Lambda\*\* – Serverless function to process events

\* \*\*Amazon SNS (Simple Notification Service)\*\* – Sends email notifications



---



\## 🔄 Workflow Explanation



\### Step 1: Create S3 Bucket



\* Create a new S3 bucket.

\* Enable event notification for:



&nbsp; \* \*\*Event type:\*\* PUT (Object Created)

&nbsp; \* Destination: Lambda function



---



\### Step 2: Create SNS Topic



\* Create a Standard SNS Topic.

\* Create an Email subscription.

\* Confirm subscription from email inbox.



---

`



---



\## 📊 Expected Output



An email with subject:



```

S3 File Upload Notification

```



And body:



```

New file uploaded:



Bucket: example-bucket

File: a.txt

```



---







\## 🔐 IAM Permissions Required



\### Lambda Execution Role Must Have:



\* `AmazonSNSFullAccess`

\* `AWSLambdaBasicExecutionRole`



---



\## 🧹 Cleanup (Important to Avoid Charges)



\* Delete Lambda function

\* Delete SNS topic

\* Delete S3 bucket

\* Remove CloudWatch logs



---



\## 🏁 Conclusion



This project successfully demonstrates how AWS services can be integrated to create a serverless, event-driven system. Whenever a file is uploaded to S3, the system automatically sends an email notification using Lambda and SNS.



