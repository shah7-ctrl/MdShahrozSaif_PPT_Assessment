#### Task 13: Start/Stop EC2 using Lambda + API Gateway





\*\*Serverless EC2 Control using AWS Lambda and API Gateway\*\*



---



\## 🎯 Objective



To automate starting and stopping an EC2 instance using a serverless API built with Lambda and API Gateway.



This task demonstrates understanding of:



\* Serverless compute

\* REST API creation

\* IAM permissions

\* AWS SDK integration

\* Infrastructure automation



---



\## 🛠️ Services Used



\* Amazon EC2

\* AWS Lambda

\* Amazon API Gateway

\* AWS Identity and Access Management

\* Amazon Web Services



---



\## 🏗️ Architecture Overview



1\. User sends HTTP request to API Gateway.

2\. API Gateway triggers Lambda function.

3\. Lambda uses AWS SDK (Boto3) to:



&nbsp;  \* Start EC2 instance

&nbsp;    OR

&nbsp;  \* Stop EC2 instance

4\. Lambda returns JSON response.



---



\## ⚙️ Step-by-Step Implementation



---



\## Step 1: Create IAM Role for Lambda



1\. Go to IAM → Roles

2\. Create new role for \*\*Lambda\*\*

3\. Attach policy:



&nbsp;  \* `AmazonEC2FullAccess` (for demo purposes)

4\. Create role



---



\## Step 2: Create Lambda Function



1\. Go to Lambda → Create Function

2\. Choose:



&nbsp;  \* Author from scratch

&nbsp;  \* Runtime: Python 3.x

3\. Attach IAM role created above





Click \*\*Deploy\*\*



---



\## Step 3: Create API Gateway



1\. Go to API Gateway

2\. Create API → HTTP API

3\. Add Integration → Select Lambda

4\. Choose your Lambda function

5\. Create Route:



&nbsp;  \* POST `/ec2control`

6\. Deploy API



Copy the \*\*Invoke URL\*\*



---



\## 🧪 Testing the API



Use Postman or browser (if GET configured).



\### Start EC2 (POST Request)



\*\*Request Body:\*\*



```json

{

&nbsp; "action": "start"

}

```



\### Stop EC2 (POST Request)



```json

{

&nbsp; "action": "stop"

}

```



---



---



\## 🔐 Key Learning Outcomes



\* Serverless architecture design

\* API Gateway integration with Lambda

\* IAM role configuration

\* EC2 automation using Boto3

\* REST API creation in AWS



---



\## 🧠 Real-World Use Case



This approach is used for:



\* Cost optimization (auto stop non-production servers)

\* Admin dashboards

\* DevOps automation

\* Remote infrastructure control

\* Cloud management tools



Many companies build internal APIs like this for infrastructure automation.



---



\## 📌 Conclusion



In this project, we successfully automated EC2 instance management using Lambda and API Gateway. The API endpoint allows users to start or stop EC2 instances dynamically without logging into AWS Console.



This demonstrates practical knowledge of serverless automation and API-based cloud control.



---



