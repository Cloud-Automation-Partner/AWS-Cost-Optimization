# Lambda Automation Scripts

## Overview
This guide provides examples of AWS Lambda scripts to automate routine cost optimization tasks.

## Scripts

### 1. Stop EC2 Instances During Non-Working Hours

```python
import boto3
import datetime

def lambda_handler(event, context):
    ec2 = boto3.client('ec2')
    now = datetime.datetime.now()
    if now.hour >= 20 or now.hour < 8:
        response = ec2.describe_instances(Filters=[{'Name': 'tag:AutoStop', 'Values': ['true']}])
        for reservation in response['Reservations']:
            for instance in reservation['Instances']:
                ec2.stop_instances(InstanceIds=[instance['InstanceId']])
                print(f"Stopped instance: {instance['InstanceId']}")
    return "EC2 instances stopped"
```

### 2. Delete Old EBS Snapshots

```python
import boto3
from datetime import datetime, timedelta

def lambda_handler(event, context):
    ec2 = boto3.client('ec2')
    snapshots = ec2.describe_snapshots(OwnerIds=['self'])['Snapshots']
    now = datetime.now()
    for snapshot in snapshots:
        start_time = snapshot['StartTime']
        if now - start_time > timedelta(days=30):
            ec2.delete_snapshot(SnapshotId=snapshot['SnapshotId'])
            print(f"Deleted snapshot: {snapshot['SnapshotId']}")
    return "Old EBS snapshots deleted"
```


### 3. Optimize RDS Storage

```python
import boto3

def lambda_handler(event, context):
    rds = boto3.client('rds')
    instances = rds.describe_db_instances()['DBInstances']
    for instance in instances:
        if instance['AllocatedStorage'] > 20:
            rds.modify_db_instance(DBInstanceIdentifier=instance['DBInstanceIdentifier'], AllocatedStorage=20)
            print(f"Optimized storage for RDS instance: {instance['DBInstanceIdentifier']}")
    return "RDS storage optimized"
```

## Conclusion
These Lambda scripts can automate routine cost optimization tasks, saving time and reducing costs. Proceed to the Infrastructure as Code guide to implement IaC for cost optimization.
