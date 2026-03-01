

#### \## Task 7: Create Amazon EFS and Connect to Multiple EC2 Instances (Amazon Linux \& Ubuntu)



---



\## 📌 Task Overview



\*\*Simple Definition:\*\*

Mount shared storage across multiple EC2 instances.



\*\*Objective:\*\*

To understand and implement scalable shared file systems in AWS using Amazon Elastic File System (EFS).



---



\## 🛠️ Services Used



\* Amazon EC2

\* Amazon EFS

\* Security Groups

\* NFS (Network File System)



---



\## 🔧 Implementation Steps



\### Step 1: Create Amazon EFS



1\. Go to AWS Console → EFS

2\. Click \*\*Create File System\*\*

3\. Select VPC

4\. Keep default settings

5\. Create mount targets in required Availability Zones

6\. Create file system



---



\### Step 2: Configure Security Group



Allow:



| Type | Protocol | Port | Source             |

| ---- | -------- | ---- | ------------------ |

| NFS  | TCP      | 2049 | EC2 Security Group |



Attach this security group to EFS.



---



\### Step 3: Launch EC2 Instances



Create:



\* 1 Amazon Linux EC2

\* 1 Ubuntu EC2



Ensure:



\* Both are in same VPC

\* Same Security Group (or allowed in NFS rule)



---



\### Step 4: Connect and Install NFS Client



\#### On Amazon Linux:



```bash

sudo yum install -y amazon-efs-utils

sudo mkdir /mnt/efs

sudo mount -t efs <EFS-ID>:/ /mnt/efs

```



---



\#### On Ubuntu:



```bash

sudo apt update

sudo apt install -y nfs-common

sudo mkdir /mnt/efs

sudo mount -t nfs4 <EFS-DNS-NAME>:/ /mnt/efs

```



---



\### Step 5: Verify Shared Storage



On Amazon Linux:



```bash

cd /mnt/efs

sudo nano a.txt

```



On Ubuntu:



```bash

cd /mnt/efs

ls

```



If `a.txt` appears → Shared storage working successfully.



---



\## 🏁 Conclusion



Successfully created an Amazon EFS file system and mounted it across:



\* Amazon Linux EC2

\* Ubuntu EC2



Both instances were able to access and modify shared storage, demonstrating scalable and distributed file system implementation in AWS.







