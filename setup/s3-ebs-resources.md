# S3 EBS Resources Setup Guide 

## Overview
This guide provides steps to set up additional AWS resources such as S3 and EBS as part of the initial environment for the cost optimization POC.

## Steps

### S3 Setup

1. **Login to AWS Management Console**: Navigate to the [AWS Management Console](https://aws.amazon.com/).

2. **Create S3 Bucket**:
   - Go to the S3 Dashboard.
   - Click on `Create bucket`.
   - Bucket name: `my-poc-bucket`.
   - Region: Select your preferred region.
   - Click `Create bucket`.

3. **Upload Files**:
   - Click on the bucket name.
   - Click `Upload`.
   - Add files to upload and click `Upload`.

### EBS Setup

1. **Create EBS Volume**:
   - Go to the EC2 Dashboard.
   - Click on `Volumes` under the `Elastic Block Store` section.
   - Click `Create Volume`.
   - Volume type: General Purpose SSD (gp2).
   - Size: 20 GB.
   - Availability Zone: Select the same as your EC2 instances.
   - Click `Create Volume`.

2. **Attach EBS Volume**:
   - Select the volume from the list.
   - Click `Actions` -> `Attach Volume`.
   - Select the instance to attach to.
   - Click `Attach`.

3. **Mount EBS Volume on EC2 Instance**:
   - SSH into the EC2 instance.
   - List block devices: `lsblk`.
   - Create a file system on the volume: `sudo mkfs -t ext4 /dev/xvdf`.
   - Create a mount point: `sudo mkdir /mnt/mydata`.
   - Mount the volume: `sudo mount /dev/xvdf /mnt/mydata`.
   - Verify the setup: `df -h`.

## Conclusion
Your additional resources are now set up and running. Proceed to the [Cost Analysis](../cost-analysis/using-cost-explorer.md) to start analyzing your AWS costs.
