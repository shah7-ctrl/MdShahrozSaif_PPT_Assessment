#### 📘 Task 10: VPC 3-Tier Architecture



\## 📌 Simple Definition



Design and implement a \*\*3-tier architecture\*\* inside a custom VPC using public and private subnets with secure communication between layers.



---





\## 🏗️ Architecture Overview



A \*\*3-Tier Architecture\*\* consists of:



1\. \*\*Presentation Layer (Web Tier)\*\* – Public Subnet

2\. \*\*Business Layer (App Tier)\*\* – Private Subnet

3\. \*\*Database Layer (DB Tier)\*\* – Private Subnet



---



\## 🧱 AWS Services Used



\* Amazon VPC

\* Amazon EC2

\* Internet Gateway

\* NAT Gateway

\* Network ACL

\* Security Groups







\# ⚙️ Implementation Steps



\## Step 1: Create Custom VPC



\* Name: `MyVPC`

\* CIDR: `10.0.0.0/24`



---



\## Step 2: Create Subnets



| Subnet Type    | Name       | CIDR        | Purpose       |

| -------------- | ---------- | ----------- | ------------- |

| Public Subnet  | Web-Subnet | 10.0.0.0/27 | Presentation  |

| Private Subnet | App-Subnet | 10.0.0.32/27| Business      |

| Private Subnet | DB-Subnet  | 10.0.0.64/26| Database      |



---



\## Step 3: Attach Internet Gateway



\* Create IGW

\* Attach to `HIT-VPC`

\* Add route in Public Route Table:



```

0.0.0.0/0 → Internet Gateway

```



---



\## Step 4: Create NAT Gateway



\* Allocate Elastic IP

\* Create NAT Gateway in \*\*Public Subnet\*\*

\* Add route in Private Route Table:



```

0.0.0.0/0 → NAT Gateway

```



---



\## Step 5: Route Tables Configuration



\### Public Route Table



\* Associated with Web Subnet

\* Route:



&nbsp; \* VPC CIDR (local)

&nbsp; \* 0.0.0.0/0 → IGW



\### Private Route Table



\* Associated with App \& DB Subnets

\* Route:



&nbsp; \* VPC CIDR (local)

&nbsp; \* 0.0.0.0/0 → NAT Gateway



---





---





\### Network ACL Rules



Public Subnet NACL:



\* Allow HTTP (80)

\* Allow HTTPS (443)

\* Allow SSH (22)



Private Subnet NACL:



\* Allow internal VPC communication

\* Allow ephemeral ports (1024-65535)



---



\# 🔑 SSH Tunneling (Private Access)





---



\# 🧪 Verification Commands



Check private internet access from App Server:



```bash

ping google.com

```



Expected Output: HTML response (shows NAT working)



Check internal connectivity:



```bash

ping 10.0.3.x

```

---



\# 🏁 Final Result



Successfully implemented a secure and scalable \*\*3-Tier VPC Architecture\*\* with:



\* Public \& Private Subnets

\* NAT Gateway

\* Internet Gateway

\* Route Tables

\* NACL Configuration

\* SSH Tunneling



---



