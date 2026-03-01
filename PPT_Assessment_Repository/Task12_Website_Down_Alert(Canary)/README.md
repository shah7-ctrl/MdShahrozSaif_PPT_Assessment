#### Website Uptime Monitoring using CloudWatch Synthetics Canary and SNS Alerts



---



\## 🎯 Objective



To monitor website availability using a Canary (synthetic monitoring) and automatically send email alerts when the website is down.



This task demonstrates understanding of:



\* Automated monitoring

\* Serverless functions

\* Alerting systems

\* Cloud-based observability



---



\## 🛠️ Services Used



\* AWS Lambda

\* Amazon SNS

\* Amazon Web Services



---



\## 🏗️ Architecture Overview



1\. CloudWatch Synthetics Canary runs on a schedule.

2\. Canary checks website availability (HTTP response).

3\. If website fails:



&nbsp;  \* CloudWatch triggers alarm.

&nbsp;  \* SNS sends email notification.

4\. User receives alert in email.



---



\## ⚙️ Step-by-Step Implementation



---



\### Step 1: Create SNS Topic



1\. Go to \*\*Amazon SNS\*\*

2\. Click \*\*Create Topic\*\*

3\. Type: Standard

4\. Topic Name: `WebsiteDownAlert`

5\. Create subscription:



&nbsp;  \* Protocol: Email

&nbsp;  \* Endpoint: Your email address

6\. Confirm email subscription



---



\### Step 2: Create CloudWatch Canary



1\. Go to \*\*CloudWatch → Synthetics\*\*

2\. Click \*\*Create Canary\*\*

3\. Choose Blueprint: \*\*Heartbeat monitoring\*\*

4\. Enter:



&nbsp;  \* Canary Name: `Website-Uptime-Check`

&nbsp;  \* URL: Your website URL (e.g., \[https://example.com](https://example.com))

5\. Schedule:



&nbsp;  \* Run every 1 minute (for testing)

6\. Runtime:



&nbsp;  \* Default Lambda runtime

7\. Create Canary



The Canary internally uses AWS Lambda to run the check.



---



\### Step 3: Create CloudWatch Alarm



1\. Go to \*\*CloudWatch → Alarms\*\*

2\. Click \*\*Create Alarm\*\*

3\. Select metric:



&nbsp;  \* Synthetics → Canary metrics

&nbsp;  \* Select \*\*Failed\*\*

4\. Condition:



&nbsp;  \* Threshold: ≥ 1

&nbsp;  \* Period: 1 minute

5\. Next → Add Action:



&nbsp;  \* Send notification to SNS topic `WebsiteDownAlert`

6\. Name the alarm:



&nbsp;  \* `Website-Down-Alarm`



Click \*\*Create Alarm\*\*



---



\## 🧪 Testing the Alert



To test:



\* Stop your web server

&nbsp; OR

\* Provide an invalid URL temporarily



When website becomes unavailable:



\* Canary run fails

\* Alarm state changes to \*\*In Alarm\*\*

\* Email notification is sent



---



\## 📊 Expected Monitoring Flow



| Event           | Result          |

| --------------- | --------------- |

| Website UP      | Canary Success  |

| Website DOWN    | Canary Failed   |

| Failure ≥ 1     | Alarm Triggered |

| Alarm Triggered | Email Sent      |



---



\## 🔐 Key Learning Outcomes



\* Understanding synthetic monitoring

\* Automated uptime checks

\* Serverless execution (Lambda backend)

\* SNS integration for alerts

\* Event-driven monitoring architecture



---



\## 🧠 Real-World Use Case



This setup is used in:



\* E-commerce websites

\* Banking applications

\* SaaS platforms

\* Production DevOps monitoring



Companies monitor:



\* Uptime

\* Response time

\* Availability

\* Endpoint failures



---



\## 📌 Conclusion



In this project, we implemented automated website uptime monitoring using CloudWatch Synthetics Canary. When the website becomes unavailable, an alarm is triggered and an email notification is sent using SNS.



This demonstrates practical implementation of automated cloud monitoring and alerting systems.



---



