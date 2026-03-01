#### \# Task 8: Create IAM Users and Groups



\## 📌 Task Title



\*\*Create IAM Users and Groups\*\*



\## 🎯 Objective



To understand AWS Identity and Access Management (IAM) by creating users, groups, and assigning permissions using policies.



\## 📖 Simple Definition



IAM (Identity and Access Management) allows us to securely manage access to AWS services and resources by creating users, organizing them into groups, and attaching policies that define permissions.



---



\## 🛠️ Services Used



\* AWS IAM (Identity and Access Management)

\* EC2 (for permission testing)



---



\## 👤 User \& Group Details



\* \*\*IAM User Name:\*\* `HIT`

\* \*\*IAM Group Name:\*\* `HIT-Developers`

\* \*\*Policy Attached:\*\* `ec2allaccess`



---



\## 🔄 Steps Performed



\### Step 1: Login to AWS Console



\* Logged into AWS Management Console.

\* Navigated to \*\*IAM Dashboard\*\*.



\### Step 2: Create IAM Group



1\. Clicked on \*\*User Groups\*\* → \*\*Create Group\*\*

2\. Group Name: `HIT-Developers`

3\. Attached Policy: `ec2allaccess`

4\. Clicked \*\*Create Group\*\*



\### Step 3: Create IAM User



1\. Clicked on \*\*Users\*\* → \*\*Create User\*\*

2\. User Name: `HIT`

3\. Selected access type (Console access)

4\. Added user to group: `HIT-Developers`

5\. Clicked \*\*Create User\*\*



\### Step 4: Verify Permissions



\* Logged in using the IAM user `HIT`

\* Verified that EC2 service access is available

\* Confirmed EC2 permissions are working properly



---



\## 🔐 Policy Used



\*\*Policy Name:\*\* `ec2allaccess`

This policy provides full access to Amazon EC2 services, allowing the user to create, start, stop, and manage EC2 instances.





