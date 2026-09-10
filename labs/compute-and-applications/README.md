# Compute & Applications

## Overview
This section contains labs focused on AWS compute services and application integration, covering EC2 instances, serverless computing with Lambda, and related infrastructure.

---

## Labs Completed

### 1. [Introduction to Amazon EC2](./Introduction-to-Amazon-EC2.md)
Learn the fundamentals of Amazon Elastic Compute Cloud (EC2):
- Launching and managing EC2 instances
- Configuring security groups and key pairs
- Connecting to instances via EC2 Instance Connect
- Understanding instance lifecycle and monitoring

---

### 2. [Working with AWS Lambda](./working-with-aws-lambda.md)
Deploy a serverless sales analysis reporting solution using AWS Lambda:
- Creating Lambda layers for dependency management
- Building multi-function Lambda architectures
- Configuring VPC and database connectivity
- Implementing automated scheduling with CloudWatch Events
- Integrating SNS for email notifications

---

### 3. [Troubleshooting the Creation of an EC2 Instance](./troubleshoot-create-instance.md)
Launch a LAMP EC2 instance via the AWS CLI and troubleshoot a buggy provisioning script:
- Launching an EC2 instance with the AWS CLI (`run-instances`)
- Diagnosing Region-specific AMI errors (`InvalidAMIID.NotFound`)
- Using the open-source nmap utility to test port reachability
- Fixing security group inbound rules to allow HTTP (port 80)
- Verifying a user data (cloud-init) LAMP deployment

---

## Skills Gained

✅ EC2 instance management  
✅ Serverless architecture patterns  
✅ Lambda function development  
✅ VPC networking and security  
✅ Event-driven automation  
✅ Application integration  
✅ AWS CLI infrastructure automation  
✅ Troubleshooting with nmap  
✅ Security group configuration  
