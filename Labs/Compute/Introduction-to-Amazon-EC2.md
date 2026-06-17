# Introduction to Amazon EC2

## Objective
Launch and configure an Amazon EC2 instance, modify its resources, and manage instance protection.

## Services Used
- Amazon EC2
- Amazon EBS
- Security Groups

## Steps Performed

1. **Launched an EC2 instance with termination protection enabled**
   - Proceeded without a key pair (no SSH connection required)

2. **Modified the Security Group**
   - Added an inbound rule to allow HTTP traffic
   - Added a user data script that displayed "Hello from your web server" in HTML

3. **Resized the instance**
   - Changed instance type from `t2.micro` to `t2.small`
   - Increased EBS volume from 8 GiB to 10 GiB

4. **Captured a screenshot of the instance**
   - Used the EC2 console screenshot feature to verify the instance state
   ![i-0c58dc02bd44c282e.jpg](i-0c58dc02bd44c282e.jpg)

5. **Cleanup**
   - Disabled termination protection
   - Terminated the instance and associated resources

## Key Takeaways
- EC2 instances can be resized (instance type and storage) after launch
- Termination protection prevents accidental deletion
- Security groups control inbound/outbound traffic at the instance level
- User data scripts run on instance launch and can automate setup tasks
