#### Task 4 – Auto Scaling Group (ASG) with Elastic Load Balancer (ELB)



Objective:



To understand and implement High Availability and Automatic Scaling in AWS using Auto Scaling Group (ASG) integrated with Elastic Load Balancer (ELB).



---



Introduction:



In cloud environments, applications must remain available even during failures or high traffic. AWS provides Auto Scaling and Load Balancing services to achieve scalability, fault tolerance, and high availability.



An Auto Scaling Group (ASG) automatically maintains a specified number of EC2 instances.

An Elastic Load Balancer (ELB) distributes incoming traffic across multiple EC2 instances.



When combined, these services ensure that applications remain available and responsive.



---



Core Concepts:



1\. High Availability:

&nbsp;  High availability ensures that the application remains accessible even if one or more instances fail. This is achieved by distributing instances across multiple Availability Zones.



2\. Fault Tolerance:

&nbsp;  If an EC2 instance becomes unhealthy, the Auto Scaling Group automatically replaces it with a new instance.



3\. Elasticity:

&nbsp;  Elasticity refers to the ability of the system to automatically scale out (add instances) during high traffic and scale in (remove instances) during low traffic.



4\. Load Distribution:

&nbsp;  The Load Balancer evenly distributes incoming user requests across healthy instances to prevent overloading a single server.



---



Components Involved:



1\. Launch Template:

&nbsp;  Defines configuration details for EC2 instances such as AMI, instance type, security groups, and user data.



2\. Target Group:

&nbsp;  A logical grouping of EC2 instances that receive traffic from the Load Balancer. It performs health checks to determine instance health status.



3\. Elastic Load Balancer (Application Load Balancer):

&nbsp;  Receives incoming traffic and forwards it to healthy targets in the Target Group.



4\. Auto Scaling Group:

&nbsp;  Manages EC2 instances by maintaining desired capacity and replacing unhealthy instances automatically.



---



Working Principle:



1\. The user sends a request to the Load Balancer.

2\. The Load Balancer forwards the request to the Target Group.

3\. The Target Group selects a healthy EC2 instance.

4\. The EC2 instance processes the request and sends a response.

5\. If an instance fails health checks, it is marked unhealthy.

6\. The Auto Scaling Group terminates the unhealthy instance and launches a new one.

7\. If traffic increases, ASG launches additional instances.

8\. If traffic decreases, ASG terminates extra instances.



---



Health Check Mechanism:



The Load Balancer continuously performs health checks on registered EC2 instances using a specified protocol and path (e.g., HTTP /).



If an instance responds successfully, it is marked Healthy.

If it fails repeatedly, it is marked Unhealthy and removed from traffic.



Health checks are initiated only when:



\* The Target Group is attached to a Load Balancer

\* Instances are registered in the Target Group



---



Advantages:



\* Improved application reliability

\* Automatic scaling based on demand

\* Better resource utilization

\* Reduced manual intervention

\* Increased fault tolerance



---



Conclusion:



By integrating Auto Scaling Group with Elastic Load Balancer, we achieve a highly available, scalable, and fault-tolerant infrastructure. The system automatically adjusts resources based on traffic conditions and ensures continuous application availability even during failures.



---



