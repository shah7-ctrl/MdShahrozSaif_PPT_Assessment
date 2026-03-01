#### Automated EC2 Monitoring using CloudWatch Alarm with Auto Stop and Email Notification



---



\## 🎯 Objective



To monitor EC2 CPU utilization using Amazon CloudWatch and automatically:



\* Stop the EC2 instance when CPU usage exceeds 70%

\* Send an email notification to the user



This task demonstrates understanding of:



\* Cloud monitoring

\* Alarm configuration

\* Automated actions

\* SNS notifications

\* Infrastructure automation



---



\## 🛠️ Services Used



\* Amazon EC2

\* Amazon CloudWatch

\* Amazon SNS (Simple Notification Service)



---



\## 🏗️ Architecture Overview



1\. EC2 instance runs normally.

2\. CloudWatch monitors CPU utilization.

3\. If CPU ≥ 70%:



&nbsp;  \* CloudWatch Alarm triggers

&nbsp;  \* EC2 instance stops automatically

&nbsp;  \* SNS sends email notification



---



\## ⚙️ Step-by-Step Implementation



\### Step 1: Launch EC2 Instance



\* Launch a new EC2 instance.

\* Ensure monitoring is enabled.

\* Note the Instance ID.



---



\### Step 2: Create SNS Topic



1\. Go to \*\*Amazon SNS\*\*

2\. Click \*\*Create Topic\*\*

3\. Choose \*\*Standard\*\*

4\. Enter Topic Name: `HighCPUAlert`

5\. Create subscription:



&nbsp;  \* Protocol: Email

&nbsp;  \* Endpoint: Your email address

6\. Confirm subscription from email inbox



---



\### Step 3: Create CloudWatch Alarm



1\. Go to \*\*CloudWatch → Alarms\*\*

2\. Click \*\*Create Alarm\*\*

3\. Select Metric:



&nbsp;  \* EC2 → Per-Instance Metrics

&nbsp;  \* Choose \*\*CPUUtilization\*\*

4\. Configure Metric:



&nbsp;  \* Statistic: Average

&nbsp;  \* Period: 1 Minute

&nbsp;  \* Threshold Type: Static

&nbsp;  \* Condition: Greater than 70%

5\. Click Next



---



\### Step 4: Configure Alarm Actions



\#### A) Send Email Notification



\* Select existing SNS topic: `HighCPUAlert`



\#### B) EC2 Auto Stop Action



\* Choose \*\*EC2 action\*\*

\* Select \*\*Stop this instance\*\*

\* Choose the target EC2 instance



---



\### Step 5: Name the Alarm



\* Alarm Name: `EC2-HighCPU-Stop-Alarm`

\* Description: Stops EC2 and sends email when CPU exceeds 70%



Click \*\*Create Alarm\*\*



---





Once CPU exceeds 70%:



\* Alarm state changes to \*\*In Alarm\*\*

\* Email notification is received

\* EC2 instance automatically stops



---



\## 📊 Expected Output



| Condition       | Result                 |

| --------------- | ---------------------- |

| CPU < 70%       | Instance runs normally |

| CPU ≥ 70%       | Alarm triggers         |

| Alarm Triggered | Email sent             |

| Alarm Triggered | EC2 instance stopped   |



---





\## 📌 Conclusion



In this project, we successfully created a CloudWatch alarm that monitors EC2 CPU usage. When CPU utilization exceeds 70%, the system automatically stops the EC2 instance and sends an email notification using SNS.



This demonstrates practical implementation of AWS monitoring and automation.



---



