# Aws Solution Architect Questions

**1) What is Amazon EC2?**

**ANS:** Amazon EC2 (Elastic Compute Cloud) is a web service offered by Amazon Web Services (AWS) that provides resizable compute capacity in the cloud. In simpler terms, EC2 allows you to rent virtual servers (known as instances) on which you can run your applications.

**2) What type of performance can you expect from Elastic Block Storage?**

**ANS:** The performance you can expect from Amazon Elastic Block Store (EBS), which is the block storage service provided by Amazon Web Services (AWS), varies based on the type of EBS volume you select. AWS offers several types of EBS volumes, each designed to meet different performance and cost requirements.

AWS offers several types of EBS volumes optimized for different performance characteristics:

**1.General Purpose SSD (gp2):**

Designed for a balance of price and performance.
Suitable for a broad range of workloads, including boot volumes and low-latency interactive applications.

**2.Provisioned IOPS SSD (io1/io2):**

Optimized for I/O-intensive workloads, such as databases, which require low-latency and consistent performance.
Allows you to specify a specific number of IOPS (up to 64,000 IOPS per volume) based on your application's needs.

**3.Cold HDD (sc1):**

Suitable for less frequently accessed workloads, where the lowest storage cost is important.

**3) How are terminating and stopping an instance different processes?**

**ANS:** **Stopping an Instance:**

Definition: Stopping an instance in AWS means shutting down the virtual server (EC2 instance) but keeping its associated resources intact, such as its EBS volumes (if they are not deleted upon termination).When you stop an instance, it moves from the "running" state to the "stopped" state. The instance's data on the EBS volumes persists.

  **Terminating an Instance:**

Terminating an instance means permanently deleting the virtual server (EC2 instance) and all associated resources, including any attached EBS volumes (depending on your settings).When you terminate an instance, it is completely removed from your AWS account. All data stored on the instance's EBS volumes (if not backed up or configured otherwise) is deleted.

**4) What is the difference between an On-demand instance and a spot instance?**

**ANS:** **On-Demand Instance:**

**What it is:** Think of On-Demand instances like ordering a regular item at full price from a store. You get it immediately and pay the standard rate.


**Key Points:**

Available instantly when you need them.

Pay a fixed, higher price per hour or second.

Best for applications that need continuous and predictable performance without interruptions.

**Spot Instance:**

**What it is:**
 Spot instances are like bidding for a discount at an auction. You specify the maximum price you're willing to pay, and if the current price is below that, you get the instance at a discounted rate.


**Key Points:**


Offered at significantly lower prices but can fluctuate based on demand.

Can be interrupted and terminated with short notice if the current price exceeds your bid.

Ideal for workloads that can handle interruptions or temporary pauses, such as batch processing or testing environments.

**5) How to vertically scale on amazon instance?**

**ANS:** Vertically scaling an Amazon EC2 instance means changing its instance type to increase or decrease its computing resources, such as CPU, memory, and storage.

1.Stop the Instance (if necessary)

2.Identify the Current Instance Type

3.Choose a New Instance Type

4.Modify the Instance

In the AWS Management Console:


Select your EC2 instance.

Click on "Actions" > "Instance Settings" > "Change Instance Type."

Choose the new instance type from the list and click "Apply."

5.Start the Instance

6.Verify Changes

**6) What is the diffrence between vertical and horizontal scaling?**

**ANS:** 
In Amazon Web Services (AWS), the difference between vertical scaling (also known as scaling up) and horizontal scaling (also known as scaling out)

**Vertical Scaling (Scaling Up):**

Definition: Vertical scaling involves increasing the capacity or power of an individual resource (such as an EC2 instance) in your system by adding more CPU, memory, or storage to the existing resource.

**Horizontal Scaling (Scaling Out):**

Definition: Horizontal scaling involves increasing the capacity or performance of your system by adding more instances (servers) to distribute the workload across multiple resources.

**7) When instance are launched in the cluster placement group, what are the network performance parameters that can be expected?**

**ANS:** 
When instances are launched in an AWS Cluster Placement Group, you can expect enhanced network performance compared to instances launched outside of a placement group.

The network performance parameters that can be expected in a placement group include:

1. Low Latency:


Instances within a placement group benefit from lower network latency. This is because they are physically located close to each other within the same data center or Availability Zone.

2. High Network Throughput:

Instances in a placement group can achieve higher network throughput compared to instances outside of a placement group.

3.Consistent Network Performance:

Instances in a placement group typically experience more predictable and consistent network performance due to the reduced variability in network latency and throughput.

4.Enhanced Inter-Instance Communication:

Placement groups facilitate optimized and efficient communication between instances within the group.

5.Cluster-Level Network Features:

AWS may provide additional networking features or optimizations specific to placement groups to further enhance network performance.

**8) What is Amazon virtual Private cloud(VPC)?**

**ANS:** Amazon Virtual Private Cloud (VPC) is a service provided by Amazon Web Services (AWS) that enables you to launch AWS resources in a logically isolated virtual network defined by you. It allows you to have complete control over your virtual networking environment, including IP address ranges, subnets, routing tables, and network gateways. 

**9) What are the states available in processor state control?**

**ANS:** 1.Running State: This is the default state of an EC2 instance where it is fully operational, running the configured operating system and applications.

2.Stopped State: An EC2 instance can be stopped, which halts its execution and releases the underlying resources (CPU, memory, etc.). The state of the instance is preserved, and it can be started again later.

3.Terminated State: When an EC2 instance is terminated, it is permanently deleted and cannot be restarted. The associated resources are released, including the processor resources.

4.Paused State (Hibernate for some instance types): Certain instance types in AWS support hibernation, where the state of the instance (including processor state) is saved to Amazon EBS (Elastic Block Store), allowing the instance to be quickly resumed from the saved state.

5.Instance Reboot: You can initiate a reboot of an EC2 instance, which temporarily stops the instance and then starts it again, maintaining its state and configuration.

6.Auto Scaling State: EC2 instances can be managed in an Auto Scaling group, where AWS automatically adjusts the number of instances based on demand. This involves launching new instances (running state) or terminating instances (stopped or terminated state) based on scaling policies.

7.Instance Type Modification: AWS allows you to modify the instance type of a running EC2 instance, which involves changing the underlying CPU and memory configuration without terminating the instance.

8.Elastic Network Interface (ENI) Attachment/Detachment: Managing the attachment and detachment of network interfaces to/from EC2 instances, which can affect connectivity and network-related operations.

**10) How to transfer an existing domain name registration to Amazon Route 53 without disrupting existing web traffic?**

**ANS:** **Pre-Transfer Preparation:**

 1.Check Domain Eligibility: Ensure that the domain name you want to transfer is eligible for transfer (i.e., it's not within the 60-day transfer lock period after registration or a recent transfer).

2.Prepare AWS Account: Make sure you have an AWS account set up with access to Route 53 and sufficient permissions to manage DNS settings.

3.Document Current DNS Settings: Take note of your current DNS settings, including records like A (IPv4), AAAA (IPv6), CNAME, MX (mail exchange), TXT (for SPF, DKIM, etc.), and any other relevant records.

**Steps to Transfer Domain to Route 53:**

1.Initiate Domain Transfer in AWS Route 53:

Sign in to the AWS Management Console.

Open the Route 53 console.

Choose "Registered domains" from the navigation pane.

Click "Transfer domain" and follow the instructions to begin the domain transfer process.


2.Prepare for DNS Configuration:

During the transfer process, AWS will provide you with Route 53 name servers.

Note down these name servers as you'll need to update your domain's DNS settings to point to these Route 53 name servers later.


3.Complete Transfer Authorization:

You will need to provide the necessary authorization codes (also known as EPP codes) during the transfer process to confirm ownership of the domain.

Follow the instructions provided by AWS to enter the authorization code and complete the domain transfer.


4.Update DNS Settings:

Once the domain transfer is initiated and nearing completion, update the DNS settings of your domain with the Route 53 name servers you obtained earlier.

This can usually be done through the control panel of your current domain registrar where you manage DNS settings.


5.Verify DNS Propagation:

After updating the DNS settings, monitor the propagation of these changes across the internet. DNS propagation can take up to 48 hours, during which time some users might still be directed to the old DNS servers.

**11) How is Elastic Beanstalk is different than AWS OpsWorks?**

**ANS:** AWS Elastic Beanstalk is a application management Platform where as AWS OpsWork is an Configuration management platform.
Beanstalk is an easy to use service which is used for deploying and scaling web applications.

**12) What happens if application stops responding to requests in beanstalk?**

**ANS:** AWS Beanstalk applications have a system in place for avoiding failures in the underlying infrastructure. If an amazon ec2 instances fails for any reason beanstalk will use auto scaling to automatically launch the new instance.

**13) An organizationwants to deploy a two-tier web applications on AWS. The application requires complex query processing amd table joins. However, the company has limited resources and requires high availability. Which is the best configuration that company can opt for based on the requirements?**

**ANS:** For deploying a two-tier web application on AWS that requires complex query processing and table joins while ensuring high availability with limited resources, the best configuration would involve using AWS services like Amazon RDS (Relational Database Service) and Elastic Beanstalk.

1.Use Amazon RDS to host your database. RDS is a managed database service that handles the heavy lifting of database management.Optimize your database schema and queries to efficiently handle complex joins and queries. Use indexing and proper database design to enhance performance.

2.Use AWS Elastic Beanstalk to deploy and manage your web application.
Configure Elastic Beanstalk to use an auto-scaling configuration to handle varying levels of traffic efficiently.

3.Choose appropriate instance types for both RDS and Elastic Beanstalk based on your application's resource requirements and budget constraints.

4.Implement security best practices by configuring security groups and access controls for both RDS and Elastic Beanstalk.

**14) How can you safeguard EC2 instance running on a VPC?**

**ANS:** 1.Use Security Groups:

Configure security groups to control inbound and outbound traffic to your EC2 instance. Only allow necessary protocols, ports, and IP ranges.

2.Implement Network ACLs:

Set up network ACLs at the subnet level to filter traffic based on IP addresses, ports, and protocols.

3.Enable VPC Flow Logs:

Enable VPC Flow Logs to capture information about network traffic going to and from your EC2 instance for monitoring and analysis.

4.Use Private Subnets:

Place EC2 instances in private subnets if they don’t need direct internet access. Use a NAT gateway or instance for outbound internet access.

5.Use IAM Roles:
Attach IAM roles to EC2 instances to grant permissions securely without exposing AWS credentials directly on the instance.

6.Implement DDoS Protection:
Use AWS Shield for DDoS protection and AWS WAF (Web Application Firewall) to filter and protect against web-based attacks.

**15) What automation tools can you use to spinup servers?**

**ANS:** 1.AWS CloudFormation

2.AWS Elastic Beanstalk

3.AWS OpsWorks

4.AWS Systems Manager (SSM)

5.HashiCorp Terraform

6.Ansible

7.Pulumi

**16) What are the important features of classic load balancer in EC2?**

**ANS:** 1. High availability

2.Health Checks

3.SSL Termination

4.Cross-Zone Load Balancing

5.Access Logs

6.Security Features

7.IPv6 Support

**17) What is AMI?**

**ANS:** AMI stands for Amazon Machine Image. It is a pre-configured template that contains the necessary information to launch an instance (virtual server) on Amazon Elastic Compute Cloud (EC2). An AMI includes the operating system, application server, and any additional software required to run an instance.

**18) What is the total number of buckets that can be created in AWS by default?**

**ANS:** 100 buckets can be created in each of the AWS Account. If additional buckets are required increase the bucket limit by submitting a service limit increase.

**19) Explain Stopping, Starting and Terminating an Amazon EC2 instance.**

**ANS:** Stopping an instance in AWS means shutting down the virtual server (EC2 instance) but keeping its associated resources intact, such as its EBS volumes (if they are not deleted upon termination).When you stop an instance, it moves from the "running" state to the "stopped" state. The instance's data on the EBS volumes persists.

Starting a stopped EC2 instance resumes its operation.
The instance's state changes from "stopped" to "running".
The instance retains its configuration, including instance ID, private IP address, and Elastic IP address (if associated).

Terminating an instance means permanently deleting the virtual server (EC2 instance) and all associated resources, including any attached EBS volumes (depending on your settings).When you terminate an instance, it is completely removed from your AWS account. All data stored on the instance's EBS volumes (if not backed up or configured otherwise) is deleted.

**20) How can S3 be cast-off with EC2 instance?**

**ANS:** 
Amazon S3 (Simple Storage Service) can be used with Amazon EC2 (Elastic Compute Cloud) instances to store and manage data.

Use Amazon S3 as a centralized storage solution for your EC2 instances.
Store application data, logs, backups, and other files in S3 buckets.
This offloads storage management from EC2 instances and provides durable and scalable object storage. 
    
