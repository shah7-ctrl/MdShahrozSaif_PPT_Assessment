

#### \# Task 6: S3 Replication and Lifecycle Policy



\## 📌 Simple Definition



This task demonstrates how to configure \*\*Amazon S3 Replication\*\* and \*\*Lifecycle Policies\*\* to ensure data backup and cost optimization.



---



\## 🎯 Objective



\* Understand how \*\*S3 replication\*\* provides automatic backup in another bucket/region.

\* Learn how \*\*Lifecycle rules\*\* reduce storage costs by transitioning or deleting old objects.

\* Implement versioning to support replication and object recovery.



---



\## 🛠 Services Used



\* Amazon S3

\* S3 Versioning

\* S3 Lifecycle Rules



---



\## 📖 Implementation Steps



\### Step 1: Create Source and Destination Buckets



1\. Login to AWS Management Console.

2\. Navigate to \*\*S3\*\*.

3\. Create two buckets:



&nbsp;  \* `source-bucket-task6`

&nbsp;  \* `destination-bucket-task6`

4\. (Optional but recommended) Create destination bucket in a different region for Cross-Region Replication.



---



\### Step 2: Enable Versioning



1\. Open \*\*source bucket\*\*.

2\. Go to \*\*Properties → Versioning\*\*.

3\. Click \*\*Enable Versioning\*\*.

4\. Repeat for the \*\*destination bucket\*\*.



✅ Versioning is mandatory for replication.



---



\### Step 3: Configure Replication Rule



1\. Open the \*\*source bucket\*\*.

2\. Go to \*\*Management → Replication Rules\*\*.

3\. Click \*\*Create replication rule\*\*.

4\. Select:



&nbsp;  \* Apply to all objects

&nbsp;  \* Destination bucket = `destination-bucket-task6`

5\. Create or select IAM role for replication.

6\. Save the rule.



Now, any new object uploaded in source bucket will automatically replicate to the destination bucket.



---



\### Step 4: Configure Lifecycle Policy



1\. Open \*\*source bucket\*\*.

2\. Go to \*\*Management → Lifecycle Rules\*\*.

3\. Click \*\*Create lifecycle rule\*\*.

4\. Configure rule:



&nbsp;  \* Apply to all objects

&nbsp;  \* Transition objects to \*\*Standard-IA\*\* after 30 days

&nbsp;  \* (Optional) Move to \*\*Glacier\*\* after 60 days

&nbsp;  \* Expire objects after 50 days

5\. Save the rule.



This helps in \*\*cost optimization\*\* by automatically moving older data to cheaper storage classes.



---



\## 🧪 Testing the Configuration



1\. Upload a sample file to the \*\*source bucket\*\*.

2\. Verify that the file appears in the \*\*destination bucket\*\*.

3\. Check object versions in both buckets.

4\. Confirm lifecycle rule is listed under management.



---



\## 🔐 Benefits of This Configuration



\* ✔ Automatic backup using replication

\* ✔ Disaster recovery readiness

\* ✔ Reduced storage costs via lifecycle rules

\* ✔ Protection against accidental deletion (versioning)



---

