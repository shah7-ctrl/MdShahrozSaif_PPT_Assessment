### \# Task 3: Attach EBS Volume Across AZ using Snapshot



\## Objective

To demonstrate cross-AZ EBS volume handling using snapshots.



\## Steps Performed



1\. Created EC2 instance in us-east-1a

2\. Attached EBS volume and created test file

3\. Created snapshot of volume

4\. Restored new volume in us-east-1b

5\. Attached new volume to EC2 in us-east-1b

6\. Verified data integrity



\## Result

Successfully restored data across Availability Zones using snapshot mechanism.



\## Key Learning

\- EBS volumes are AZ-specific

\- Snapshots are region-wide

\- Cross-AZ volume migration requires snapshot restore

