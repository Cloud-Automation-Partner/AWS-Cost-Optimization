# Lambda Setup Guide

## Overview
This guide provides steps to set up AWS Lambda functions as part of the initial environment for the cost optimization POC.

## Steps

1. **Login to AWS Management Console**: Navigate to the [AWS Management Console](https://aws.amazon.com/).

2. **Create Lambda Functions**:
   - Go to the Lambda Dashboard.
   - Click on `Create function`.
   - Choose `Author from scratch`.
   - Function name: `MyFunction`.
   - Runtime: Choose a runtime (e.g., Python 3.8).
   - Role: Choose an existing role or create a new one with basic Lambda permissions.
   - Click `Create function`.

3. **Configure Lambda Function**:
   - Under the Function code section, add your code. For example, a simple function:
     ```python
     import json

     def lambda_handler(event, context):
         return {
             'statusCode': 200,
             'body': json.dumps('Hello from Lambda!')
         }
     ```
   - Click `Deploy`.

4. **Set Environment Variables** (Optional):
   - Scroll down to the Environment variables section.
   - Add key-value pairs as needed.

5. **Set up Triggers**:
   - Click `Add trigger`.
   - Choose a trigger (e.g., API Gateway, S3, CloudWatch Events).
   - Configure the trigger as needed.
   - Click `Add`.

6. **Test the Lambda Function**:
   - Click `Test`.
   - Configure a test event (e.g., HelloWorld).
   - Click `Create` and then `Test` again to execute the function.

## Conclusion
Your Lambda functions are now set up and running. Proceed to the [RDS Setup Guide](rds-setup.md) to continue with the POC setup.
