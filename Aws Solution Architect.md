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

