# AWS Lambda and S3 CSV Email Automation

This project demonstrates how to process a CSV file uploaded to an Amazon S3 bucket using an AWS Lambda function. The Lambda function parses the CSV file, extracts recipient information, and sends personalized emails using Amazon Simple Email Service (SES). It also sends a summary notification via Amazon SNS (Simple Notification Service).

## Features
- Automated processing of CSV files uploaded to S3.
- Sends personalized emails to recipients listed in the CSV using SES.
- Sends a summary notification to an SNS topic.
- Uses IAM roles and bucket policies for secure access.

## Architecture Overview
1. **S3 Bucket**: Stores the uploaded CSV files.
2. **Lambda Function**: Processes the uploaded files, sends emails, and triggers notifications.
3. **SES**: Sends emails to recipients listed in the CSV.
4. **SNS**: Sends a summary notification after processing.

## Prerequisites
- AWS account with permissions for Lambda, S3, SES, and SNS.
- AWS CLI installed and configured locally.
- CSV file containing email addresses and names of recipients.

## How to Run the Project
1. **Upload the Lambda Function**:
   - Deploy the Lambda function code using the AWS Management Console or AWS CLI.
   - Set environment variables for `SES_SENDER_EMAIL` and `SNS_TOPIC_ARN` in the Lambda function.

2. **Create and Configure the S3 Bucket**:
   - Create a new S3 bucket.
   - Add a bucket policy to allow the Lambda function to access the bucket.

3. **Verify SES Email Addresses**:
   - Verify the sender email (`SES_SENDER_EMAIL`) and recipient emails in SES.

4. **Test the Project**:
   - Upload a CSV file to the S3 bucket. The Lambda function will process it automatically.
   - Check SES for email delivery and SNS for the summary notification.

## Example CSV Format
The CSV file should follow this format:
```csv
Name,Email
John Doe,john.doe@example.com
Jane Smith,jane.smith@example.com

AWS Services Used
Lambda: Serverless computing for file processing.
S3: Object storage for storing CSV files.
SES: Email delivery service for sending emails.
SNS: Messaging service for sending notifications.
Files Included
lambda_function.py: Python script for the Lambda function.
bucket_policy.json: Example S3 bucket policy.
screenshots/: Folder containing screenshots of AWS configuration and test results.
Screenshots
Screenshots are included in the screenshots/ folder to demonstrate:

S3 bucket configuration.
Lambda function setup and permissions.
SES email verification.
Test results showing successful execution.
License
This project is licensed under the MIT License. See the LICENSE file for details.

