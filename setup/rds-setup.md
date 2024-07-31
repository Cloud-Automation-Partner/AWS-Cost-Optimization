# RDS Setup Guide

## Overview
This guide provides steps to set up an RDS instance as part of the initial environment for the cost optimization POC.

## Steps

1. **Login to AWS Management Console**: Navigate to the [AWS Management Console](https://aws.amazon.com/).

2. **Create RDS Instance**:
   - Go to the RDS Dashboard.
   - Click on `Create database`.
   - Choose a database creation method: `Standard Create`.
   - Engine options: Choose an engine (e.g., MySQL).
   - Version: Choose a version (e.g., MySQL 8.0).
   - Templates: Select `Free tier` or `Production`.
   - Settings:
     - DB instance identifier: `mydbinstance`.
     - Master username: `admin`.
     - Master password: `password`.
   - DB instance class: Select a class (e.g., db.t2.micro).
   - Storage:
     - Allocated storage: 20 GB.
     - Enable storage autoscaling: Yes.
   - Connectivity:
     - VPC: Select the default VPC.
     - Subnet group: Default.
     - Public access: Yes.
     - VPC security groups: Create new or select existing.
     - Availability zone: No preference.
   - Database authentication: Password authentication.
   - Additional configuration:
     - Initial database name: `mydatabase`.
     - Backup retention: 7 days.
     - Enable encryption: No.
   - Click `Create database`.

3. **Post-Launch Setup**:
   - Wait for the instance to be available.
   - Note down the endpoint and port.

4. **Connect to the RDS Instance**:
   - Use a MySQL client (e.g., MySQL Workbench) to connect to the RDS instance.
   - Hostname: Endpoint from the RDS console.
   - Port: 3306.
   - Username: `admin`.
   - Password: `password`.

5. **Verify Setup**:
   - Create a test database and table.
   - Insert and retrieve data to ensure the database is functioning correctly.

## Conclusion
Your RDS instance is now set up and running. Proceed to the [Other Resources Setup Guide](other-resources-setup.md) to continue with this project setup.
