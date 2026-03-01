#### Disk Partitioning (Ubuntu MBR \& Windows GPT)





##### Part 1 – Ubuntu (MBR using fdisk)

Environment: AWS EC2 Ubuntu Instance



Secondary EBS Volume (2GB)



Steps Performed:



Attached a new 2GB EBS volume to the Ubuntu EC2 instance.



Verified disk using:



lsblk



Opened fdisk:



sudo fdisk /dev/nvme1n1



Created MBR partition table (DOS disklabel).



Created a 500MB primary partition.



Wrote changes using:



w



Verified using:



sudo fdisk -l /dev/nvme1n1

Result



Disklabel type: dos (MBR)



One primary partition created (500MB)



Partition type: Linux (83)



##### Part 2 – Windows (GPT using Disk Management)

Environment: AWS Windows EC2 Instance



New 2GB EBS Volume Attached



Steps Performed



Created and attached a new EBS volume.



Connected via RDP.



Opened:



Disk Management



Initialized new disk as:



GPT (GUID Partition Table)



Created a new Simple Volume.



Formatted as NTFS.



Assigned drive letter.



Result:



Disk initialized as GPT



New NTFS partition created



Volume successfully mounted

