# CloudFormation Templates for AWS Resource Deployment

This repository contains AWS CloudFormation templates to automate the provisioning of key AWS resources such as S3 buckets and EC2 instances.

## Templates Included

### 1. **S3 Bucket Creation**
- Creates an S3 bucket named `my-sample-bucket-2020`.
- **How to use**:
  - Open the **AWS Console**.
  - Go to **CloudFormation** → **Create Stack**.
  - Upload the `s3-bucket-template.yaml` file.
  - Proceed with default settings to deploy the stack.

### 2. **EC2 Instance Deployment via AWS CLI**
- Launches an Amazon EC2 instance using a predefined Amazon Linux AMI.
- Template file example: `awslinuxid.yaml`.
- **Prerequisites**:
  - AWS CLI installed and configured (`aws configure`).
  - Required IAM permissions.
- **How to use**:
  1. Save the EC2 YAML template locally (e.g., `awslinuxid.yaml`).
  2. Run:
     bash
     aws cloudformation create-stack --stack-name MyEC2Stack \
     --template-body file://C:/Users/Filepath/awslinuxid.yaml \
     --capabilities CAPABILITY_NAMED_IAM
     
  3. Verify deployment:
     bash
     aws cloudformation describe-stacks --stack-name MyEC2Stack \
     --query "Stacks[0].StackStatus"
     
- Statuses include:
  - `CREATE_IN_PROGRESS`
  - `CREATE_COMPLETE`
  - `ROLLBACK_IN_PROGRESS`

##  Purpose
To simplify AWS infrastructure setup using Infrastructure as Code (IaC) through CloudFormation templates for reproducible and scalable environments.

##  Deployment Methods
- **Console-based deployment** for S3 bucket.
- **Command-line-based deployment** for EC2 using AWS CLI.

