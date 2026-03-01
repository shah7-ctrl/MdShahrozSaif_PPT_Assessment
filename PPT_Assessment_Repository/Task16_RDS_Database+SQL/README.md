

#### \# Task 16: RDS Database + SQL Workbench Connection \& Queries





\*\*Deploying and Connecting to Amazon RDS using MySQL Workbench\*\*



---



\## 🎯 Objective



To create a managed relational database using Amazon RDS and connect to it using MySQL Workbench to execute SQL queries.



This task demonstrates understanding of:



\* Managed database services

\* RDS instance configuration

\* Secure database connectivity

\* SQL query execution



---



\## 🛠️ Services \& Tools Used



\* Amazon RDS

\* Amazon Web Services

\* MySQL Workbench

\* MySQL Database Engine



---



\## ⚙️ Step-by-Step Implementation



---



\### Step 1: Launch RDS Instance



1\. Go to \*\*RDS Dashboard\*\*

2\. Click \*\*Create Database\*\*

3\. Choose:



&nbsp;  \* Engine type: \*\*MySQL\*\*

&nbsp;  \* Template: Free Tier

4\. Configure:



&nbsp;  \* DB Instance Identifier

&nbsp;  \* Master Username

&nbsp;  \* Master Password

5\. DB Instance Class: `db.t3.micro`

6\. Storage: 20 GB (Free tier eligible)

7\. Connectivity:



&nbsp;  \* Public access: Yes (for testing)

8\. Create Database



Wait until status becomes \*\*Available\*\*



---



\### Step 2: Configure Security Group



1\. Go to \*\*EC2 → Security Groups\*\*

2\. Edit inbound rules

3\. Add rule:



&nbsp;  \* Type: MySQL/Aurora

&nbsp;  \* Port: 3306

&nbsp;  \* Source: Your IP address (recommended)



---



\### Step 3: Get RDS Endpoint



\* Go to RDS → Databases

\* Copy \*\*Endpoint\*\*

\* Note:



&nbsp; \* Endpoint

&nbsp; \* Port (3306)

&nbsp; \* Username

&nbsp; \* Password



---



\### Step 4: Connect Using MySQL Workbench



1\. Open MySQL Workbench

2\. Click \*\*+ New Connection\*\*

3\. Enter:



&nbsp;  \* Hostname: RDS Endpoint

&nbsp;  \* Port: 3306

&nbsp;  \* Username: master username

4\. Enter password

5\. Click \*\*Test Connection\*\*

6\. Click \*\*OK\*\*



If configured correctly → Connection successful ✅



---



\## 🧪 SQL Queries Executed



\### 1️⃣ Create Database



```sql

CREATE DATABASE company\_db;

```



---



\### 2️⃣ Use Database



```sql

USE company\_db;

```



---



\### 3️⃣ Create Table



```sql

CREATE TABLE employees (

&nbsp;   id INT PRIMARY KEY AUTO\_INCREMENT,

&nbsp;   name VARCHAR(100),

&nbsp;   department VARCHAR(100),

&nbsp;   salary INT

);

```



---



\### 4️⃣ Insert Data



```sql

INSERT INTO employees (name, department, salary)

VALUES 

('Ali', 'IT', 50000),

('Sara', 'HR', 45000),

('John', 'Finance', 60000);

```



---



\### 5️⃣ Retrieve Data



```sql

SELECT \* FROM employees;

```



---



\### ✅ Expected Query Output



| id | name | department | salary |

| -- | ---- | ---------- | ------ |

| 1  | Ali  | IT         | 50000  |

| 2  | Sara | HR         | 45000  |

| 3  | John | Finance    | 60000  |



---

\## 📊 Expected Results



| Component            | Status                |

| -------------------- | --------------------- |

| RDS Instance         | Running               |

| Security Group       | Port 3306 Open        |

| Workbench Connection | Successful            |

| SQL Queries          | Executed Successfully |



---



\## 🔐 Key Learning Outcomes



\* Understanding managed database services

\* RDS configuration and deployment

\* Network \& security configuration

\* Database connectivity

\* Basic SQL operations (DDL \& DML)



---



\## 🧠 Real-World Use Case



Amazon RDS is widely used for:



\* Web application backends

\* E-commerce databases

\* ERP systems

\* SaaS platforms



It removes the need for manual database maintenance like:



\* Patching

\* Backups

\* Scaling



---



\## 📌 Conclusion



In this project, we successfully deployed a MySQL database using Amazon RDS and connected it using MySQL Workbench. We created a database, created a table, inserted records, and retrieved data using SQL queries.



This task demonstrates practical knowledge of managed relational database services in AWS.



