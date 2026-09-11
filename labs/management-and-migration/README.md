# Management & Migration

## Overview

This section contains labs focused on AWS management, monitoring, and migration services, covering database migration to managed services, infrastructure provisioning with the AWS CLI, and performance monitoring with CloudWatch.

---

## Labs Completed

### 1. [Migrating to Amazon RDS](./migrating-to-amazon-RDS.md)

Migrate a café web application from a local database to a fully managed Amazon RDS instance:

- Creating an Amazon RDS MariaDB instance using the AWS CLI
- Provisioning VPC networking components (private subnets, subnet groups, security groups)
- Migrating data from a MariaDB database on EC2 to Amazon RDS using `mysqldump`
- Configuring encrypted (SSL/TLS) database connections
- Externalizing database configuration with AWS Systems Manager Parameter Store
- Monitoring the RDS instance with Amazon CloudWatch metrics

---

### 2. [Using AWS Systems Manager](./using-aws-systems-manager.md)

Manage an EC2 instance at scale without SSH using AWS Systems Manager:

- Collecting software and configuration inventory with Fleet Manager and Inventory
- Installing a custom web application remotely with Run Command
- Managing application settings and feature flags with Parameter Store
- Accessing an instance shell securely with Session Manager
- Understanding the SSM Agent and IAM-based access control

---

### 3. [Automation with CloudFormation](./automation-with-cloudFormation.md)

Define infrastructure as code and deploy it as a repeatable, automated stack:

- Deploying a VPC and Security Group from a YAML CloudFormation template
- Understanding the Parameters, Resources, and Outputs template sections
- Authoring S3 bucket and EC2 instance resources by consulting AWS documentation
- Referencing resources within a template using the `!Ref` intrinsic function
- Retrieving the latest Amazon Linux AMI via Systems Manager Parameter Store
- Updating a live stack incrementally and previewing change sets
- Cleanly deleting a stack and all the resources it created

---

## Skills Gained

✅ Managed database provisioning (Amazon RDS)  
✅ Database migration and data backup/restore  
✅ AWS CLI infrastructure automation  
✅ VPC networking and security groups  
✅ Configuration management with Parameter Store  
✅ Performance monitoring with CloudWatch  
✅ Fleet inventory and configuration compliance (Systems Manager)  
✅ Remote application installation with Run Command  
✅ SSH-free instance access with Session Manager  
✅ Infrastructure as code with AWS CloudFormation  
✅ Authoring and updating CloudFormation templates (YAML)  
✅ Referencing resources with intrinsic functions (`!Ref`)  
