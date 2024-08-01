# Baseline Cost Report

## Overview
This document provides a template for creating a baseline cost report, which will be used to compare against future costs after implementing optimization strategies.

## Report Template

### 1. Summary
- **Date**: YYYY-MM-DD
- **Total Monthly Cost**: $X,XXX.XX
- **Highest Cost Services**: EC2, RDS, Lambda, S3

### 2. Cost Breakdown by Service
- **EC2**:
  - Total Cost: $XXX.XX
  - Number of Instances: XX
  - Instance Types: t2.micro, m5.large
- **RDS**:
  - Total Cost: $XXX.XX
  - Instance Type: db.t2.micro
  - Storage: XX GB
- **Lambda**:
  - Total Cost: $XX.XX
  - Number of Functions: X
  - Total Invocations: XX,XXX
- **S3**:
  - Total Cost: $XX.XX
  - Storage Used: XX GB
  - Number of Objects: XX,XXX

### 3. Cost Breakdown by Region
- **us-east-1**: $X,XXX.XX
- **us-west-2**: $XXX.XX

### 4. Cost Breakdown by Usage Type
- **Compute**: $X,XXX.XX
- **Storage**: $XXX.XX
- **Data Transfer**: $XX.XX

### 5. Anomalies and Insights
- **Anomalies**:
  - Unexpected spike in EC2 costs due to increased instance usage.
  - Higher-than-expected Lambda invocation costs.
- **Insights**:
  - Significant portion of costs attributed to underutilized EC2 instances.
  - Potential savings by switching to Reserved Instances or Savings Plans.

### 6. Recommendations
- Right-size EC2 instances.
- Consider Reserved Instances or Savings Plans.
- Optimize Lambda function configurations.
- Implement S3 lifecycle policies for infrequently accessed objects.

## Conclusion
The baseline cost report provides a detailed snapshot of current AWS spending. This will serve as a reference point to measure the impact of cost optimization strategies. Proceed to the [Optimization Strategies](../optimization-strategies/ec2-optimization.md) to start implementing cost-saving measures.
