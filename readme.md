## What is Virtualization?

Virtualization is a technology that enables the creation of virtual instances of hardware or software resources, allowing multiple operating systems or applications to run on a single physical machine. This is accomplished using hypervisors or virtualization software, which abstract the underlying hardware to provide efficient resource utilization, isolation, and management.

---

## What is a Hypervisor?

A **hypervisor** is software that creates and manages virtual machines (VMs) by abstracting the hardware resources of a physical machine. Hypervisors are classified into two types:

1. **Type 1 Hypervisor (Bare-metal):**  
    Runs directly on the host's hardware without requiring a host operating system.  
    *Examples:* VMware ESXi, Microsoft Hyper-V, Xen.

2. **Type 2 Hypervisor (Hosted):**  
    Runs on top of a host operating system and relies on the host OS for resource management.  
    *Examples:* VMware Workstation, Oracle VirtualBox, Parallels Desktop.

---

## How Hypervisors Work

1. The hypervisor shares hardware resources of the host machine with the virtual machines.
2. Each VM has its own virtual hardware, including CPU, memory, storage, and network interfaces.
3. VMs are isolated from each other, allowing them to run different operating systems and applications simultaneously without interference.

---

## Hypervisor Architecture Diagram

![Hypervisor Architecture](/public/images/virtualization.png)

*Figure: Illustration of how a hypervisor manages multiple virtual machines on a single physical host.*

---

## What is Cloud Computing?

Cloud computing is a model that enables on-demand access to a shared pool of configurable computing resources (such as servers, storage, and applications) over the internet. It allows users to access and use computing resources without the need for local infrastructure, providing flexibility, scalability, and cost-effectiveness.

---

## Types of Cloud Computing

1. **Infrastructure as a Service (IaaS):**  
    Provides virtualized computing resources over the internet, such as virtual machines, storage, and networks.  
    *Examples:* Amazon EC2, Microsoft Azure, Google Cloud Compute Engine.

2. **Platform as a Service (PaaS):**  
    Offers a platform for developers to build, deploy, and manage applications without managing the underlying infrastructure.  
    *Examples:* Google App Engine, Microsoft Azure App Service, Heroku.

3. **Software as a Service (SaaS):**  
    Delivers software applications over the internet, accessible via a web browser without installation.  
    *Examples:* Google Workspace, Microsoft 365, Salesforce.

---

## Cloud Deployment Models

1. **Public Cloud:**  
    Services are provided over the internet and shared among multiple users.  
    *Examples:* AWS, Microsoft Azure, Google Cloud Platform.

2. **Private Cloud:**  
    Dedicated infrastructure for a single organization, providing greater control and security. Can be hosted on-premises or by a third-party provider.

3. **Hybrid Cloud:**  
    Combines public and private clouds, allowing data and applications to be shared between them for flexibility and scalability.

---

## What is AWS?

**Amazon Web Services (AWS)** is a comprehensive cloud computing platform provided by Amazon. It offers a wide range of cloud services, including computing power, storage, databases, machine learning, analytics, and more. AWS enables businesses to scale their infrastructure and applications on-demand, providing flexibility and cost savings.

---

## What Makes AWS Special?

- **Scalability:** Easily scale resources up or down based on demand.
- **Global Reach:** Data centers in multiple regions worldwide for low-latency access and redundancy.
- **Reliability:** High availability and fault tolerance through distributed architecture.
- **Security:** Robust security features, including encryption, identity and access management, and compliance certifications.

---

## IAM - Identity and Access Management

**AWS Identity and Access Management (IAM)** is a service that enables you to manage access to AWS resources securely. It allows you to create and manage users, groups, and roles, and define permissions to control who can access specific AWS services and resources.

**Key Features:**

- **User Management:** Create and manage AWS users and groups, assign permissions, and control access.
- **Role-Based Access Control:** Define roles with specific permissions and assign them to users or services for temporary access.
- **Multi-Factor Authentication (MFA):** Enhance security by requiring additional authentication factors.
- **Policy Management:** Create and manage policies that define permissions for users, groups, and roles.

---

## Setting up AWS CLI

1. **Install AWS CLI:**  
    Download and install from [AWS CLI official website](https://aws.amazon.com/cli/).

2. **Configure AWS CLI:**  
    Open a terminal or command prompt and run:
    ```bash
    aws configure
    ```
    Enter your AWS Access Key ID, Secret Access Key, default region name, and output format.

3. **Verify Installation:**  
    ```bash
    aws --version
    ```

4. **List Users:**  
    ```bash
    aws iam list-users
    ```

---

## AWS IAM Best Practices

1. Avoid using the root account for everyday tasks.
2. Add user accounts to groups for efficient permission management.
3. Use password policies and enable MFA.
4. Use access keys for CLI/SDK access.
5. Never share your access keys or secret keys.
6. Audit permissions using IAM credentials report.

---

## AWS EC2 - Elastic Compute Cloud

**AWS EC2 (Elastic Compute Cloud)** is a web service that provides resizable compute capacity in the cloud. It allows users to launch and manage virtual servers (instances) on-demand, with a variety of instance types optimized for different workloads.

**Terminologies:**

- **Instance:** A virtual server in the EC2 environment.
- **AMI (Amazon Machine Image):** Pre-configured template for launching instances.
- **Instance Type:** Hardware configuration (CPU, memory, storage, networking).
- **Key Pair:** Security credentials for connecting to instances.
- **Security Group:** Virtual firewall controlling inbound/outbound traffic.
- **Storage:** Options include Amazon EBS (block storage) and Amazon S3 (object storage).
- **Network Settings:** Instances can be launched in a Virtual Private Cloud (VPC).
- **IAM Roles:** Assign permissions to instances securely.
- **User Data:** Scripts/commands executed at instance launch.
- **Elastic IP:** Static IP address for consistent access.

---

## Security Groups

- **Region Specific:** Security groups are specific to a region.
- **Only Allow Rules:** Cannot explicitly deny traffic; all inbound traffic is denied by default.
- **Default Behavior:** All inbound traffic blocked, all outbound traffic allowed.

**Rule Definitions:**

- **Protocol:** (TCP, UDP, ICMP)
- **Port Range:** (e.g., 80 for HTTP, 22 for SSH)

**Common Ports:**

- **21:** FTP
- **22:** SSH
- **222:** SFTP
- **25:** SMTP
- **80:** HTTP
- **443:** HTTPS
- **3306:** MySQL
- **3389:** RDP
- **5432:** PostgreSQL
- **8080:** Alternative HTTP/web applications

---

## AWS EC2 Instance Types

AWS offers a variety of EC2 instance types, grouped into families based on workload and hardware specs.  
See the [official AWS EC2 Instance Types page](https://aws.amazon.com/ec2/instance-types/) for details.

**Common Families:**

- **General Purpose (t3, m5):** Balanced resources.
- **Compute Optimized (c5):** High-performance processors.
- **Memory Optimized (r5, x1):** For memory-intensive workloads.
- **Storage Optimized (i3, d2):** High storage throughput.
- **Accelerated Computing (p3, g4):** GPUs/FPGAs for ML, graphics, scientific computing.

---

## AWS EBS - Elastic Block Store

**AWS EBS (Elastic Block Store)** provides persistent block storage for EC2 instances. EBS volumes are highly available and durable, and can be attached to instances as block-level storage.

### Key Features

- **Persistence:** Data retained even if the instance is stopped or terminated.
- **Scalability:** Volumes can be resized without downtime.
- **Snapshots:** Point-in-time backups for recovery or new volumes.
- **Performance:** SSD and HDD-backed options for different workloads.
- **Encryption:** Protects data at rest and in transit.

### Important Points

- **Region and AZ Specific:** EBS volumes are tied to a region and availability zone.
- **Built-in Redundancy:** Data is replicated within the same availability zone.
- **Volume Types:** General Purpose SSD (gp2), Provisioned IOPS SSD (io1), Throughput Optimized HDD (st1), Cold HDD (sc1).
- **Snapshots:** Incremental backups for recovery or new volumes.
- **Scalable:** Volumes can be resized or changed as needed.

```bash
# List block devices and their mount points
lsblk
# Example output:
# NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
# sda      8:0    0   100G  0 disk
# ├─sda1   8:1    0    96G
```

---

## Mounting an EBS Snapshot from Another Availability Zone

To access data from an EBS snapshot created in one Availability Zone (AZ) on an EC2 instance in another AZ, follow these steps:

### Steps

1. **Create a Snapshot:**  
    Take a snapshot of the EBS volume in the source AZ.

2. **Create a New Volume from Snapshot:**  
    In the AWS Console, create a new EBS volume from the snapshot in the target AZ (where your EC2 instance is running).

3. **Attach the Volume:**  
    Attach the new EBS volume to your EC2 instance in the target AZ.

4. **Identify the Device:**  
    Use `lsblk` to list block devices and identify the new volume (e.g., `/dev/nvme1n1`).

5. **Check Filesystem:**  
    ```bash
    sudo file -s /dev/nvme1n1p1
    ```
    Ensure the partition has a valid filesystem (e.g., XFS, ext4).

6. **Create a Mount Point:**  
    ```bash
    sudo mkdir /mnt/mybackup
    ```

7. **Mount the Volume:**  
    ```bash
    sudo mount -o nouuid /dev/nvme1n1p1 /mnt/mybackup
    ```
    The `-o nouuid` option is useful for XFS filesystems cloned from another volume.

8. **Verify the Mount:**  
    ```bash
    df -h
    ```
    Confirm the volume is mounted at `/mnt/mybackup`.

9. **Access Data:**  
    Navigate to the mount point and access your files:
    ```bash
    cd /mnt/mybackup/home/ec2-user/myfolder
    ls
    cat myfile
    ```

10. **Unmount the Volume:**  
     When finished, unmount the volume to safely detach it:
     ```bash
     sudo umount -l /mnt/mybackup
     ```

11. **Verify Unmount:**  
     Check that the mount point is no longer listed:
     ```bash
     df -h
     ```
     The output should no longer show `/mnt/mybackup` as a mounted filesystem.

---

### Notes

- **Cross-AZ Data Access:** You cannot directly attach an EBS volume across AZs; you must create a new volume from the snapshot in the desired AZ.
- **Filesystem Compatibility:** If mounting an XFS filesystem cloned from another volume, always use the `-o nouuid` option to avoid UUID conflicts.
- **Data Integrity:** Always unmount the volume after use to prevent data corruption.

---

## AMI - Amazon Machine Image

An **Amazon Machine Image (AMI)** is a pre-configured template used to create EC2 instances. It contains the operating system (Windows, Mac, Linux), application server (Apache, Nginx), and applications required to launch an instance.

### Key Features of AMI

- **Customizable:** Users can create custom AMIs with specific configurations, software, and settings.
- **Reusable:** AMIs can be reused to launch multiple instances with the same configuration.
- **Region Specific:** AMIs are specific to a region, but can be copied across regions.
- **Public and Private:** Users can share AMIs publicly or keep them private for their own use.

### Types of AMIs

- **Public AMIs:** Provided by AWS or the community, available for anyone to use.
- **Private AMIs:** Created by users for their own use, containing custom configurations.
- **Marketplace AMIs:** Available for purchase from the AWS Marketplace, often with additional software or support.

### Create Launch Template vs Create Image

- **Launch Template:** A reusable configuration for launching EC2 instances, including instance type, AMI, security groups, and other settings.
- **Create Image:** Creates a new AMI from an existing EC2 instance, capturing its current state, including installed software and configurations.

![AMI Comparison](/public/images/createImageVsCreateTemplate.png)

### AWS Image Builder

**AWS Image Builder** is a service that simplifies the creation, maintenance, and deployment of secure and up-to-date AMIs. It automates the process of building images, ensuring they are compliant with security standards and best practices.

---

## ELB - Elastic Load Balancer

**AWS Elastic Load Balancer (ELB)** automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses. It helps ensure high availability and fault tolerance for applications by routing traffic to healthy targets.

### Key Features of ELB

- **Automatic Scaling:** Adjusts the number of targets based on incoming traffic.
- **Health Checks:** Monitors the health of targets and routes traffic only to healthy instances.
- **SSL Termination:** Offloads SSL/TLS encryption and decryption from targets.

### Types of Load Balancers

- **Application Load Balancer (ALB):** Operates at the application layer (HTTP/HTTPS) and supports advanced routing, SSL termination, and WebSocket.
- **Network Load Balancer (NLB):** Operates at the transport layer (TCP and UDP) and is designed for high performance and low latency.
- **Gateway Load Balancer (GWLB):** Combines the features of a transparent network gateway and a load balancer, allowing you to deploy, scale, and manage third-party virtual appliances.
- **Classic Load Balancer (CLB):** Legacy load balancer that supports both HTTP and TCP protocols. It is being phased out in favor of ALB and NLB.

---

## ASG - Auto Scaling Group

**AWS Auto Scaling Group (ASG)** is a service that automatically adjusts the number of EC2 instances in a group based on demand. It helps maintain application availability and allows you to scale your resources up or down automatically.

### Functions of ASG

- **Dynamic Scaling:** Automatically adds or removes instances based on predefined policies, such as CPU utilization or network traffic.
- **Main Instance Health:** Monitors the health of instances and replaces unhealthy ones to maintain application availability.
- **Use Scaling Policies:** Define scaling policies to control how the ASG responds to changes in demand, such as increasing capacity during peak hours and reducing it during low traffic periods.
- **Ensure Availability:** Distributes instances across multiple availability zones to enhance fault tolerance and availability.
- **Scheduled Scaling:** Allows you to scale resources based on predictable traffic patterns, such as scaling up during business hours and scaling down at night.
- **Distributed Instances:** Ensures instances are distributed across multiple availability zones for high availability and fault tolerance.
- **Integrates with ELB:** Works seamlessly with Elastic Load Balancers to distribute traffic across instances in the ASG.
- **Optimizes Costs:** Automatically adjusts the number of instances to match demand, helping to optimize costs by avoiding over-provisioning.

## AWS S3 - Simple Storage Service
**AWS S3 (Simple Storage Service)** is an object storage service that provides highly scalable, durable, and secure storage for data. It is designed to store and retrieve any amount of data from anywhere on the web.

### Key Features of S3
Stores data as objects in buckets, which are containers for storing data.
Globally unique bucket names across all AWS accounts.
Region Specific: Buckets are created in specific AWS regions for low-latency access and compliance.
Each object within a bucket has a unique key (name) and can be up to 5 TB in size.
Multipart Upload is recommended for large files, allowing you to upload parts of an object in parallel.

S3 Versioning
- Enables you to keep multiple versions of an object in a bucket.
S3 Replication
- Automatically replicates objects across different AWS regions for disaster recovery and data redundancy.
- SRR (Same Region Replication) replicates objects within the same region.
- CRR (Cross Region Replication) replicates objects across different regions.
S3 Lifecycle Policies
- Automates the transition of objects to different storage classes based on age or other criteria.
S3 Snow Family
- A suite of physical devices for transferring large amounts of data to and from AWS. 
- Includes Snowcone, Snowball, and Snowmobile for different data transfer needs.
- AWS Snowcone : A small, portable device for a few terabytes of data.
- AWS Snowball : A larger device for transferring petabytes of data.
- AWS Snowmobile : A truck-sized device for transferring exabytes of data.
S3 Storage Gateway
- A hybrid cloud storage service that connects on-premises applications to S3.

## AWS RDS - Relational Database Service
**AWS RDS (Relational Database Service)** is a managed database service that simplifies the setup, operation, and scaling of relational databases in the cloud. It supports multiple database engines, including MySQL, PostgreSQL, Oracle, SQL Server, and Amazon Aurora.

Amazon Aurora Offers
- High performance and availability with up to 5X times the MySQL and 3X times the Postgres. 
- Upto 15 read replicas for scaling read workloads.
- Upto 128 TB of storage per database instance.

RDS Read Replicas - Multi Region
- Allows you to create read-only copies of your database in different regions for disaster recovery and low-latency access.
- Supports automatic failover to a read replica in case of primary database failure.

## AWS DynamoDB
**AWS DynamoDB** is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. It is designed for applications that require low-latency data access and can handle large amounts of data.

DynamoDB offers a free tier with 25 GB of storage and up to 200 million requests per month, making it cost-effective for small applications.

### Features of DynamoDB
- **Serverless:** Automatically scales up or down based on traffic, eliminating the need for manual provisioning.
- **Automatic Scaling:** Adjusts throughput capacity based on application demand.
- **Zero Downtime:** Provides high availability and durability with automatic data replication across multiple availability zones.
- **On demand pricing:** Pay only for the resources you use, with no upfront costs or long-term commitments.
- **Idle Cost Savings:** Automatically scales down to zero when not in use, reducing costs.

### DAX - DynamoDB Accelerator (DAX) is a fully managed, in-memory caching service for DynamoDB that provides fast read performance for applications with high read throughput requirements.

## AWS Lambda
**AWS Lambda** is a serverless compute service that allows you to run code without provisioning or managing servers. You can execute code in response to events, such as changes in data, HTTP requests, or scheduled tasks.

### Key Features of AWS Lambda
- **Event-Driven:** Automatically triggers code execution in response to events from AWS services or custom applications.
- **Scalable:** Automatically scales to handle incoming requests, with no need for manual intervention.
- **Pay-as-You-Go:** Charges based on the number of requests and the duration of code execution, with no upfront costs.
- **Supports Multiple Languages:** Supports various programming languages, including Python, Node.js, Java, C#, and Go.
- **Integration with AWS Services:** Easily integrates with other AWS services, such as S3, DynamoDB, and API Gateway, to build serverless applications.

### Limitations of AWS Lambda
- **Execution Time Limit:** Maximum execution time of 15 minutes per invocation.
- **Stateless:** Each invocation is stateless, meaning no data is retained between invocations.
- **Cold Start:** Initial invocation may experience a delay (cold start) as the service provisions resources.

### When to Use AWS Lambda
- **Image Processing:** Let's say you have an application that processes images uploaded to S3. You can use Lambda to automatically resize or convert images when they are uploaded.
- **Data Transformation:** If you need to transform data in DynamoDB or S3, you can use Lambda to process and modify the data as it changes.
- **Real-Time Notifications:** You can use Lambda to send notifications or trigger workflows in response to events, such as new user sign-ups or order placements.

## AWS CloudFormation
**AWS CloudFormation** is a service that allows you to define and provision AWS infrastructure as code. It enables you to create and manage AWS resources using templates written in JSON or YAML, making it easy to automate the deployment and management of your infrastructure.

### Key Features of AWS CloudFormation
- **Infrastructure as Code:** Define your infrastructure using code, making it easy to version control and share.
- **Declarative Syntax:** Describe the desired state of your infrastructure, and CloudFormation takes care of provisioning and configuring resources.
- **Stack Management:** Group related resources into stacks, allowing you to manage them as a single unit.
- **Change Sets:** Preview changes before applying them to your stacks, ensuring you understand the impact of changes.
- **Cross-Region and Cross-Account Support:** Deploy stacks across multiple AWS regions and accounts for greater flexibility and scalability.

### Why to Use AWS CloudFormation
- **Consistency:** Ensures consistent and repeatable deployments across environments.
- **Automation:** Automates the provisioning and management of AWS resources, reducing manual effort and errors.
- **Version Control:** Allows you to version control your infrastructure code, making it easy to track