
# Infrastructure as Code (IaC)

## Overview
This guide provides an example of using AWS CloudFormation and Terraform to manage and deploy resources in a cost-efficient manner.

## AWS CloudFormation

### 1. CloudFormation Template

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: AWS Cost Optimization Project

Resources:
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0
      Tags:
        - Key: AutoStop
          Value: true

  MyRDSInstance:
    Type: 'AWS::RDS::DBInstance'
    Properties:
      DBInstanceClass: db.t2.micro
      Engine: MySQL
      MasterUsername: admin
      MasterUserPassword: password
      AllocatedStorage: 20
```

### 2. Deploy CloudFormation Stack

```bash
aws cloudformation create-stack --stack-name my-cost-optimization-poc --template-body file://cloudformation-template.yaml
```

## Terraform

### 1. Terraform Configuration

```tf
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "my_ec2_instance" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name     = "MyEC2Instance"
    AutoStop = "true"
  }
}

resource "aws_db_instance" "my_rds_instance" {
  allocated_storage    = 20
  storage_type         = "gp2"
  engine               = "mysql"
  instance_class       = "db.t2.micro"
  name                 = "mydatabase"
  username             = "admin"
  password             = "password"
  skip_final_snapshot  = true
}
```

### 2. Deploy Terraform Configuration

```bash
terraform init
```
```bash
terraform apply
```

## Conclusion
Using IaC tools like CloudFormation and Terraform can help you manage and deploy AWS resources efficiently. Proceed to the Continuous Improvement guide for regular cost reviews and updates.
