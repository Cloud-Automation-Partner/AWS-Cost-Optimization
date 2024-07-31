# EC2 Setup Guide

## Overview
This guide provides steps to set up EC2 instances as part of the initial environment for the cost optimization POC.

## Steps

1. **Login to AWS Management Console**: Navigate to the [AWS Management Console](https://aws.amazon.com/).

2. **Launch EC2 Instances**:
   - Go to the EC2 Dashboard.
   - Click on `Launch Instance`.
   - Select an Amazon Machine Image (AMI).
   - Choose instance types (e.g., t2.micro, m5.large).
   - Configure instance details:
     - Number of instances: 2 (one for web server, one for database).
     - Network: Select default VPC.
     - Subnet: Select a subnet.
     - Enable Auto-assign Public IP.
   - Add Storage:
     - Root volume: 8 GB (General Purpose SSD).
     - Additional volume: 20 GB (General Purpose SSD) for database instance.
   - Add Tags (Optional):
     - Key: Name, Value: WebServer/Database
   - Configure Security Group:
     - Allow SSH (port 22), HTTP (port 80), and HTTPS (port 443) for the web server.
     - Allow SSH (port 22) and MySQL/Aurora (port 3306) for the database instance.
   - Review and Launch.

3. **Post-Launch Setup**:
   - SSH into the instances using the key pair created/downloaded during setup.
   - Install necessary software (e.g., Apache, MySQL).

4. **Verify Setup**:
   - Ensure the web server is accessible via HTTP/HTTPS.
   - Ensure the database server is running and accessible from the web server.

## Conclusion
Your EC2 instances are now set up and running. Proceed to the [Lambda Setup Guide](lambda-setup.md) to continue with the POC setup.
