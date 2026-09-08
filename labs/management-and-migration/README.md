# Management & Migration

## Overview

This section contains labs focused on AWS management, monitoring, and migration services, covering database migration to managed services, infrastructure provisioning with the AWS CLI, and performance monitoring with CloudWatch.

## Labs Completed

### 1. ![Migrating to Amazon RDS](./migrating-to-amazon-RDS.md)

Migrate a café web application from a local database to a fully managed Amazon RDS instance:

- Creating an Amazon RDS MariaDB instance using the AWS CLI
- Provisioning VPC networking components (private subnets, subnet groups, security groups)
- Migrating data from a MariaDB database on EC2 to Amazon RDS using `mysqldump`
- Configuring encrypted (SSL/TLS) database connections
- Externalizing database configuration with AWS Systems Manager Parameter Store
- Monitoring the RDS instance with Amazon CloudWatch metrics

## Skills Gained

✅ Managed database provisioning (Amazon RDS)
✅ Database migration and data backup/restore
✅ AWS CLI infrastructure automation
✅ VPC networking and security groups
✅ Configuration management with Parameter Store
✅ Performance monitoring with CloudWatch
