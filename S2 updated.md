# AWS Database Deployment Assessment

## Lab Overview

In this assessment, you will deploy and secure AWS database services by launching an Amazon EC2 instance, creating a database subnet group, deploying an Amazon RDS MySQL database, and configuring secure communication between application and database resources.

## Scenario

You have joined an organization as a Cloud Engineer. The company requires a secure and highly available database environment for its applications. Your task is to deploy the required compute and database resources, configure secure access, and ensure that database connectivity follows AWS security best practices.

## Solution

To meet these requirements, you will launch an Amazon EC2 instance, create a database subnet group using private subnets, deploy an Amazon RDS MySQL database, and configure security groups to allow only authorized application servers to access the database. This approach ensures secure database access while keeping the database isolated from direct public access.

# Assessment Objectives

This lab environment is designed to evaluate your practical skills in deploying and securing AWS database services. As part of this assessment, you will deploy an Amazon EC2 instance, configure a private Amazon RDS MySQL database, implement secure connectivity between resources, and validate database access.

You are expected to follow AWS best practices and use the specified resource names to ensure successful validation.

> **Note:** To ensure successful validation and consistency across all assessment tasks, you must deploy all AWS resources in **one of the following supported AWS Regions only**:
>
> - us-east-2 (Ohio)
>
> Resources deployed in any other AWS Region may not be detected by the validation scripts and could result in assessment failures.

---

## Task 1: Launch an EC2 Instance

> **Note:** Follow the specified naming conventions exactly to ensure validation works properly.

1. Launch an Amazon Linux 2 EC2 instance named **Lab1-App-Server**.
2. Use either a **t2.micro** or **t3.micro** instance type.
3. Deploy the instance in one of the public subnets created in Scenario 1.

### Success Criteria

- An EC2 instance named **Lab1-App-Server** exists.
- The instance is in the **Running** state.
- The instance type is **t2.micro** or **t3.micro**.

<validation step="951a19c4-e1ce-4dff-b5df-e2f981bbc880" />

---

## Task 2: Create a Database Subnet Group

> **Note:** Follow the specified naming conventions exactly to ensure validation works properly.

1. Create a DB Subnet Group named **Lab1-DB-Subnet-Group**.
2. Add only the private subnets created in Scenario 1 to the subnet group.

---

## Task 3: Deploy a MySQL RDS Instance

> **Note:** Follow the specified naming conventions exactly to ensure validation works properly.

1. Create an Amazon RDS instance.
2. Configure the database engine as **MySQL 8.x**.
3. Use the instance class **db.t3.micro**.
4. Deploy the database using **Lab1-DB-Subnet-Group**.
5. Ensure **Public Access** is set to **Disabled**.
6. Multi-AZ deployment is optional.

### Success Criteria

- Database engine is **MySQL 8.x**.
- Instance class is **db.t3.micro**.
- Public accessibility is disabled.
- The instance status is **Available**.

<validation step="79e50816-7960-48f0-a9e4-07188109fb78" />

---

## Task 4: Configure Secure Database Access

> **Note:** Follow the specified naming conventions exactly to ensure validation works properly.

1. Create a security group named **Lab1-EC2-SG** for the EC2 instance.
2. Create a security group named **Lab1-RDS-SG** for the RDS instance.
3. Configure the security groups so that only **Lab1-App-Server** can connect to the RDS database on port **3306**.
---

## You have successfully completed the Assessment.
