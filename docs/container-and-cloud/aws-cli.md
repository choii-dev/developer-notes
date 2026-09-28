# AWS CLI Cheatsheet ☁️

A quick reference guide for core AWS Command Line Interface operations across key services.

---

## 1. Configuration & Profiles

| Command | Description |
| :--- | :--- |
| `aws configure` | Interactively configure default AWS credentials, region, and output format |
| `aws configure list` | Display current active credentials and region configurations |
| `aws configure set region <region-name>` | Quick-set the active region (e.g., `eu-west-1`) |
| `aws sts get-caller-identity` | Verify current authenticated IAM user / role identity |

---

## 2. Amazon S3 (Simple Storage Service)

| Command | Description |
| :--- | :--- |
| `aws s3 ls` | List all S3 buckets in your account |
| `aws s3 ls s3://<bucket-name>/` | List objects inside a specific bucket |
| `aws s3 mb s3://<bucket-name>` | Create a new S3 bucket |
| `aws s3 cp <local-file> s3://<bucket-name>/` | Upload a local file to S3 |
| `aws s3 cp s3://<bucket-name>/<file> .` | Download a file from S3 to current local directory |
| `aws s3 sync <local-dir> s3://<bucket-name>/` | Sync local directory with an S3 bucket (only copies updated files) |
| `aws s3 rm s3://<bucket-name>/<file>` | Delete an object from an S3 bucket |

---

## 3. EC2 & Security Groups

| Command | Description |
| :--- | :--- |
| `aws ec2 describe-instances` | List details for all EC2 instances |
| `aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId,State.Name,PublicIpAddress]"` | List instance ID, state, and public IP |
| `aws ec2 start-instances --instance-ids <id>` | Start a stopped EC2 instance |
| `aws ec2 stop-instances --instance-ids <id>` | Stop a running EC2 instance |
| `aws ec2 describe-security-groups` | List security groups and associated rules |

---

## 4. AWS Lambda

| Command | Description |
| :--- | :--- |
| `aws lambda list-functions` | List all deployed Lambda functions |
| `aws lambda invoke --function-name <func-name> response.json` | Execute a function and save output to `response.json` |
| `aws lambda update-function-code --function-name <func-name> --zip-file fileb://code.zip` | Update function code via deployment zip package |

---

## 5. Amazon ECR (Elastic Container Registry)

| Command | Description |
| :--- | :--- |
| `aws ecr get-login-password --region <region> \| docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com` | Authenticate Docker client against AWS ECR |
| `aws ecr create-repository --repository-name <repo-name>` | Create a new container image repository in ECR |
| `aws ecr list-images --repository-name <repo-name>` | List all container images tagged inside an ECR repo |

---

## 6. IAM (Identity and Access Management)

| Command | Description |
| :--- | :--- |
| `aws iam list-users` | List all IAM users |
| `aws iam list-roles` | List all IAM roles |
| `aws iam list-attached-user-policies --user-name <username>` | List policies directly attached to a specific IAM user |
