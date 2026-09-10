# Working with AWS Lambda - Lab Summary

## Overview
Deployed a serverless sales analysis reporting solution using AWS Lambda. The system automatically generates daily sales reports by extracting data from a MySQL database and sending results via email using SNS.

**Key Services**: Lambda, SNS, Parameter Store, CloudWatch Events, VPC, IAM

---

## Lab Completion

### Task 1: Lambda Layer & Data Extractor Function

**Created**:
- Lambda layer `pymysqlLibrary` with PyMySQL library dependency
- `salesAnalysisReportDataExtractor` function (Python 3.9)
- Assigned `salesAnalysisReportDERole` with VPC and logging permissions

<img width="380" height="180" alt="Screenshot 2026-08-23 081718" src="https://github.com/user-attachments/assets/99870efc-88a1-4aef-a4b5-8af1eb2734bd" />

<img width="380" height="180" alt="Screenshot 2026-08-23 082150" src="https://github.com/user-attachments/assets/1ca589a8-e4aa-430f-87be-7443d5df87a6" />

<img width="380" height="180" alt="Screenshot 2026-08-23 082515" src="https://github.com/user-attachments/assets/52a5189e-f55d-40e1-9daf-3add1ec6f1a3" />

### Task 2: VPC Configuration

**Configured**:
- VPC: Cafe VPC
- Subnet: Cafe Public Subnet 1
- Security Group: CafeSecurityGroup

<img width="380" height="180" alt="Screenshot 2026-08-23 082653" src="https://github.com/user-attachments/assets/081efc8a-0265-42c0-b3e1-120c6e8c82be" />

### Task 3: Testing & Troubleshooting

**Initial Test**: Failed with timeout error (3 seconds)

**Root Cause**: MySQL port 3306 not open in security group

**Solution**: Added inbound rule for TCP port 3306 to CafeSecurityGroup

<img width="380" height="180" alt="Screenshot 2026-08-23 083316" src="https://github.com/user-attachments/assets/8efa8456-c6a8-4937-9a7a-1b990c1066ae" />

<img width="380" height="180" alt="Screenshot 2026-08-23 083700" src="https://github.com/user-attachments/assets/9bcbc8df-ac64-4700-9ca3-e906498bfcb7" />

**Retry Result**: Test succeeded with empty body (no database records yet)

<img width="380" height="180" alt="Screenshot 2026-08-23 083806" src="https://github.com/user-attachments/assets/f95c9b4d-2b35-408e-bd73-fdddc7c48492" />

### Task 4: Database Population & Verification

**Action**: Placed orders on café website to populate database

<img width="380" height="180" alt="Screenshot 2026-08-23 084046" src="https://github.com/user-attachments/assets/538f80f4-4ba8-4f4e-a40d-17cdce6c7a05" />

**Retest**: Function returned populated order data (Croissants, Hot Chocolate, etc.)

<img width="380" height="180" alt="Screenshot 2026-08-23 084133" src="https://github.com/user-attachments/assets/ab2fd2b9-3ddc-4c9c-ab7c-decfa91c3f56" />

### Task 5: SNS Topic & Email Notifications

**Created**:
- SNS topic: `salesAnalysisReportTopic`
- Email subscription confirmed

<img width="380" height="180" alt="Screenshot 2026-08-23 084418" src="https://github.com/user-attachments/assets/cdf9fb11-0248-4e70-8537-55b22b6581d6" />

<img width="380" height="180" alt="Screenshot 2026-08-23 084544" src="https://github.com/user-attachments/assets/df37a8a1-becc-41b3-9fa5-01e895297cee" />

### Task 6: Main Orchestrator Function

**Created** `salesAnalysisReport` function using AWS CLI:
- Runtime: Python 3.9
- Role: `salesAnalysisReportRole` (SNS, Parameter Store, Lambda invoke permissions)
- Handler: `salesAnalysisReport.lambda_handler`

**Configured**: Environment variable `topicARN` with SNS topic ARN

<img width="380" height="180" alt="Screenshot 2026-08-23 085953" src="https://github.com/user-attachments/assets/d6640c67-aa52-402b-918b-15f3c6df7aa1" />

**Function Flow**:
1. Retrieves database credentials from Parameter Store
2. Invokes salesAnalysisReportDataExtractor
3. Formats report and publishes to SNS
4. Returns success confirmation

**Tested**: Function succeeded, email received with formatted sales report

<img width="380" height="180" alt="Screenshot 2026-08-23 090100" src="https://github.com/user-attachments/assets/04bd93cc-6e3b-4796-9bfd-b6e2e7a70d8c" />

<img width="380" height="180" alt="Screenshot 2026-08-23 090122" src="https://github.com/user-attachments/assets/ce5d9a58-f2bb-47a0-aa1d-eb01ef885d01" />

### Task 7: Automated Scheduling

**Added CloudWatch Events trigger**:
- Rule: `salesAnalysisReportDailyTrigger`
- Schedule: `cron(10 7 ? * MON-SUN *)` (7:10 AM UTC, Mon-Sun)

<img width="380" height="180" alt="Screenshot 2026-08-23 090659" src="https://github.com/user-attachments/assets/a4b34527-aa7e-46db-bee4-b563166f5652" />

**Verification**: Automated email received at scheduled time

<img width="380" height="180" alt="Screenshot 2026-08-23 091142" src="https://github.com/user-attachments/assets/1e16a5d3-4aaa-4ff6-9eb1-598f9f35bc9d" />

---

## Key Outcomes

✅ Deployed multi-function serverless architecture  
✅ Configured Lambda with VPC and database connectivity  
✅ Troubleshot security group and timeout issues  
✅ Implemented automated scheduling with CloudWatch Events  
✅ Integrated SNS for email notifications  
✅ Used Lambda layers for dependency management  

## Challenges & Solutions

| Issue | Fix |
|-------|-----|
| Function timeout | Added MySQL port 3306 inbound rule to security group |
| Empty report data | Placed orders on café website to populate database |
