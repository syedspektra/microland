# Lab-1: AWS Infrastructure Assessment

## S1 - Design Custom VPC with Public and Private Subnets

### Tasks

1. Create a custom VPC with the CIDR block `10.0.0.0/16` in a region of your choice.

2. Create **2 public subnets** and **2 private subnets**, each using a `/24` CIDR block and distributed across a minimum of **2 Availability Zones**.

3. Attach an Internet Gateway (IGW) to the VPC and configure a route table for the public subnets with a default route (`0.0.0.0/0`) pointing to the IGW.

4. Deploy **1 NAT Gateway** in a public subnet and configure the private subnet route table to route Internet-bound traffic through the NAT Gateway.

5. Configure Security Groups and Network ACLs to allow only the required inbound and outbound traffic between resources.

---
<div style="page-break-after: always;"></div>

## S2 - Deploy MySQL RDS Instance and Connect from EC2

### Tasks

1. Launch an **Amazon Linux 2 EC2 instance** (`t2.micro` or `t3.micro`) in a public subnet created in Scenario 1.

2. Create a DB Subnet Group using only the private subnets from Scenario 1.

3. Deploy a **MySQL 8.x RDS instance** using the `db.t3.micro` instance class within the private subnets and ensure **Public Access is disabled**.

4. Configure Security Groups so that only the EC2 instance can communicate with the RDS instance on port **3306**.

5. Connect to the EC2 instance using SSH and verify successful connectivity to the MySQL RDS endpoint.

---
<div style="page-break-after: always;"></div>

## S3 - Configure Auto Scaling Group with Load Balancer

### Tasks

1. Create a Launch Template using **Amazon Linux 2** with a user-data script that installs and starts the Apache web server.

2. Deploy an **Application Load Balancer (ALB)** with an HTTP listener on port **80** in the public subnets.

3. Create a Target Group and associate it with the ALB listener.

4. Create an Auto Scaling Group using the Launch Template, place EC2 instances in the private subnets, and register them with the Target Group.

5. Configure the Auto Scaling Group with:

   * Minimum Instances: **2**
   * Desired Instances: **2**
   * Maximum Instances: **4**
   * CPU-based scaling policy that triggers when CPU utilization reaches **60% or higher**

6. Verify that the ALB DNS name returns a valid HTTP response from the web servers running in the Auto Scaling Group.
