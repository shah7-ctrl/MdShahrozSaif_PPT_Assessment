#### 

#### \# Task 9: Access S3 from Ubuntu using IAM Roles \& Policies



\## 📌 Simple Definition



Securely access an Amazon S3 bucket from an EC2 Ubuntu instance using an IAM Role instead of Access Keys.



\## 🎯 Objective



To understand \*\*role-based access control (RBAC)\*\* in AWS and securely grant permissions to EC2 instances without storing AWS credentials inside the server.



---



\## 🛠 Services Used



\* \*\*EC2 (Amazon Instance)\*\*

\* \*\*IAM (Role \& Policy)\*\*

\* \*\*S3 (Simple Storage Service)\*\*



---



\## 🧩 Architecture Overview



EC2  → IAM Role → IAM Policy → S3 Bucket



The EC2 instance assumes an IAM Role that has permission to access the S3 bucket.



---



\## 🚀 Implementation Steps





\### Step 1: Create IAM Role



1\. Go to AWS Console → IAM → Roles

2\. Click \*\*Create Role\*\*

3\. Select \*\*AWS Service\*\*

4\. Choose \*\*EC2\*\*

5\. Attach policy:



&nbsp;  \* `AmazonS3FullAccess` (or custom S3 access policy)

6\. Name the role:



&nbsp;  ```

&nbsp;  EC2-S3-Access-Role

&nbsp;  ```

7\. Create Role



---



\### Step 2: Attach IAM Role to EC2



1\. Go to EC2 → Instances

2\. Select Ubuntu instance

3\. Click \*\*Actions → Security → Modify IAM Role\*\*

4\. Select: `EC2-S3-Access-Role`

5\. Save



---



\### Step 3: Connect to Amazon EC2



---





Verify:



```bash

aws --version

```



Step 4: Create Bucket using command and it will reflect in bucket list





---



\## 🔐 Why IAM Role is Better Than Access Keys



| IAM Role                        | Access Keys             |

| ------------------------------- | ----------------------- |

| No credentials stored in server | Keys stored in file     |

| Automatically rotated           | Manual rotation needed  |

| More secure                     | Risk of leakage         |

| Recommended by AWS              | Not recommended for EC2 |



---



