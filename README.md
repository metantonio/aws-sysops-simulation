# AWS SysOps Administrator Practice Exam

## 50 Essential Questions with Answers

### Monitoring and Reporting

**1. What AWS service helps you collect and track metrics, monitor log files, and set alarms?**
- A) Amazon Inspector
- B) AWS CloudTrail
- C) Amazon CloudWatch
- D) AWS Config

**Answer: C) Amazon CloudWatch**

CloudWatch is AWS's monitoring service that provides data and actionable insights for AWS resources and applications.

**2. Which CloudWatch metric should you monitor to identify if an EC2 instance is running out of memory?**
- A) CPUUtilization
- B) MemoryUtilization
- C) Memory available
- D) CloudWatch doesn't monitor memory usage by default

**Answer: D) CloudWatch doesn't monitor memory usage by default**

CloudWatch doesn't monitor memory usage by default. You need to install the CloudWatch agent to collect memory metrics.

**3. When configuring CloudWatch alarms, what is the minimum evaluation period?**
- A) 10 seconds
- B) 1 minute
- C) 5 minutes
- D) 15 minutes

**Answer: B) 1 minute**

The minimum evaluation period for CloudWatch alarms is 1 minute.

**4. How can you track API calls made to your AWS account?**
- A) VPC Flow Logs
- B) CloudTrail
- C) CloudWatch Events
- D) AWS Config

**Answer: B) CloudTrail**

CloudTrail tracks API calls made to your AWS account and delivers log files to an S3 bucket.

**5. Which AWS service can automatically remediate non-compliant resources?**
- A) AWS Config
- B) AWS Systems Manager
- C) AWS Trusted Advisor
- D) Amazon Inspector

**Answer: A) AWS Config**

AWS Config can use remediation actions to automatically fix non-compliant resources.

### High Availability and Elasticity

**6. What is the minimum number of Availability Zones recommended for a highly available architecture?**
- A) 1
- B) 2
- C) 3
- D) 4

**Answer: B) 2**

AWS recommends at least 2 Availability Zones for high availability.

**7. Which of the following is NOT a benefit of using an Auto Scaling group?**
- A) Automatically replace unhealthy instances
- B) Scale capacity based on demand
- C) Distribute traffic across multiple instances
- D) Provide redundancy across Availability Zones

**Answer: C) Distribute traffic across multiple instances**

That's the primary function of Elastic Load Balancing, not Auto Scaling groups.

**8. What is the difference between horizontal and vertical scaling?**
- A) Horizontal scaling increases instance size, vertical scaling adds more instances
- B) Horizontal scaling adds more instances, vertical scaling increases instance size
- C) Horizontal scaling uses load balancers, vertical scaling uses Auto Scaling groups
- D) Horizontal scaling is for EC2, vertical scaling is for RDS

**Answer: B) Horizontal scaling adds more instances, vertical scaling increases instance size**

Horizontal scaling (scaling out) adds more instances, while vertical scaling (scaling up) increases the size of existing instances.

**9. Which AWS service should you use to create a highly available database that can fail over automatically?**
- A) Amazon RDS Multi-AZ deployment
- B) Amazon DynamoDB
- C) Amazon ElastiCache
- D) Amazon Redshift

**Answer: A) Amazon RDS Multi-AZ deployment**

RDS Multi-AZ deployments provide high availability with automatic failover to a standby instance.

**10. What is the primary purpose of an Elastic Load Balancer?**
- A) To automatically scale EC2 instances
- B) To distribute incoming traffic across multiple targets
- C) To cache frequently accessed content
- D) To provide DDoS protection

**Answer: B) To distribute incoming traffic across multiple targets**

ELB distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses.

### Deployment and Provisioning

**11. Which AWS service allows you to create a repeatable template for your infrastructure?**
- A) AWS CloudFormation
- B) AWS Systems Manager
- C) AWS Config
- D) AWS OpsWorks

**Answer: A) AWS CloudFormation**

CloudFormation allows you to create templates that describe all the AWS resources you need.

**12. When using AWS CloudFormation, what is a stack?**
- A) A collection of AWS resources created as a single unit
- B) A set of CloudFormation templates
- C) A group of EC2 instances
- D) A list of stack policies

**Answer: A) A collection of AWS resources created as a single unit**

A CloudFormation stack is a collection of AWS resources that you create, update, or delete as a single unit.

**13. Which service can be used to run commands on multiple EC2 instances simultaneously?**
- A) AWS Lambda
- B) AWS Systems Manager Run Command
- C) AWS CloudWatch
- D) AWS CloudTrail

**Answer: B) AWS Systems Manager Run Command**

Systems Manager Run Command lets you run commands on multiple EC2 instances without requiring SSH access.

**14. What is the main advantage of using AWS Elastic Beanstalk?**
- A) It provides more control over the underlying infrastructure
- B) It automatically handles capacity provisioning, load balancing, and application health monitoring
- C) It's less expensive than managing EC2 instances directly
- D) It provides more security features than regular EC2 deployments

**Answer: B) It automatically handles capacity provisioning, load balancing, and application health monitoring**

Elastic Beanstalk automatically handles deployment details like capacity provisioning, load balancing, and monitoring.

**15. Which AWS service enables you to centrally manage AWS resources across multiple accounts and regions?**
- A) AWS Organizations
- B) AWS Control Tower
- C) AWS Systems Manager
- D) AWS Config

**Answer: C) AWS Systems Manager**

Systems Manager provides a unified interface to view operational data from multiple AWS services and automate tasks across AWS resources.

### Security and Compliance

**16. What is the AWS Shared Responsibility Model?**
- A) AWS is responsible for all security in the cloud
- B) Customers are responsible for all security in the cloud
- C) AWS is responsible for security of the cloud, customers are responsible for security in the cloud
- D) AWS and customers share all security responsibilities equally

**Answer: C) AWS is responsible for security of the cloud, customers are responsible for security in the cloud**

AWS manages the security of the underlying infrastructure, while customers are responsible for securing their data and applications.

**17. Which AWS service helps you analyze potential security issues in your CloudFormation templates before deployment?**
- A) AWS Config
- B) AWS CloudTrail
- C) AWS CloudFormation Guard
- D) Amazon Inspector

**Answer: C) AWS CloudFormation Guard**

CloudFormation Guard allows you to check CloudFormation templates for policy compliance before deployment.

**18. What is the primary purpose of an AWS Security Group?**
- A) To encrypt data in transit
- B) To control inbound and outbound traffic to AWS resources
- C) To set permissions for AWS users
- D) To monitor security threats

**Answer: B) To control inbound and outbound traffic to AWS resources**

Security Groups act as a virtual firewall to control inbound and outbound traffic to AWS resources.

**19. Which AWS service helps you protect your applications from web exploits?**
- A) AWS Shield
- B) AWS WAF
- C) AWS Network Firewall
- D) AWS GuardDuty

**Answer: B) AWS WAF**

AWS WAF (Web Application Firewall) helps protect your applications from common web exploits.

**20. What is the recommended way to manage AWS credentials for applications running on EC2 instances?**
- A) Store credentials in environment variables
- B) Use IAM roles for EC2 instances
- C) Store credentials in the instance's user data
- D) Use AWS access keys and secret keys in application code

**Answer: B) Use IAM roles for EC2 instances**

IAM roles for EC2 instances eliminate the need to store credentials on the instance.

### Networking

**21. What is the purpose of a Network ACL in AWS?**
- A) To control traffic between subnets
- B) To provide DNS resolution
- C) To route traffic between VPCs
- D) To establish a VPN connection

**Answer: A) To control traffic between subnets**

Network ACLs control traffic entering and leaving subnets within a VPC.

**22. How does a Network ACL differ from a Security Group?**
- A) Network ACLs apply to subnets, Security Groups apply to instances
- B) Network ACLs are stateful, Security Groups are stateless
- C) Network ACLs can only filter inbound traffic, Security Groups filter both inbound and outbound
- D) Network ACLs are managed by AWS, Security Groups are managed by users

**Answer: A) Network ACLs apply to subnets, Security Groups apply to instances**

Network ACLs operate at the subnet level (stateless), while Security Groups operate at the instance level (stateful).

**23. What AWS service allows you to connect your on-premises network to AWS using an IPsec VPN?**
- A) AWS Direct Connect
- B) AWS Site-to-Site VPN
- C) AWS Transit Gateway
- D) AWS PrivateLink

**Answer: B) AWS Site-to-Site VPN**

AWS Site-to-Site VPN creates an encrypted connection between your network and your VPC.

**24. Which AWS service is used to create a private connection between your VPC and another AWS service without using the public internet?**
- A) AWS Direct Connect
- B) AWS Transit Gateway
- C) AWS PrivateLink
- D) VPC Peering

**Answer: C) AWS PrivateLink**

AWS PrivateLink provides private connectivity between VPCs and AWS services without exposing traffic to the public internet.

**25. What is the primary function of a NAT Gateway in AWS?**
- A) To provide internet access to instances in a private subnet
- B) To connect VPCs to on-premises networks
- C) To accelerate content delivery
- D) To route traffic between VPCs

**Answer: A) To provide internet access to instances in a private subnet**

NAT Gateways allow instances in private subnets to connect to the internet or other AWS services while preventing inbound connections.

### Storage and Data Management

**26. Which AWS service automatically replicates data across multiple Availability Zones for high durability?**
- A) Amazon EC2
- B) Amazon S3
- C) Amazon EBS
- D) AWS Storage Gateway

**Answer: B) Amazon S3**

Amazon S3 automatically replicates data across multiple Availability Zones for high durability.

**27. What is the most cost-effective S3 storage class for infrequently accessed data that requires immediate access?**
- A) S3 Standard
- B) S3 Intelligent-Tiering
- C) S3 Standard-IA
- D) S3 Glacier

**Answer: C) S3 Standard-IA**

S3 Standard-IA (Infrequent Access) is designed for data that is accessed less frequently but requires immediate access when needed.

**28. Which EBS volume type provides the highest performance for applications requiring intense I/O operations?**
- A) General Purpose SSD (gp3)
- B) Provisioned IOPS SSD (io2)
- C) Throughput Optimized HDD (st1)
- D) Cold HDD (sc1)

**Answer: B) Provisioned IOPS SSD (io2)**

Provisioned IOPS SSD (io2) volumes provide the highest performance for I/O-intensive workloads.

**29. What is the primary use case for Amazon EFS?**
- A) Block storage for EC2 instances
- B) Object storage for static files
- C) Shared file storage for multiple EC2 instances
- D) Archival storage for long-term data retention

**Answer: C) Shared file storage for multiple EC2 instances**

Amazon EFS provides scalable file storage for use with EC2 instances and can be accessed by multiple instances simultaneously.

**30. Which AWS service is designed for moving large amounts of data into and out of AWS?**
- A) AWS DataSync
- B) AWS Direct Connect
- C) AWS Storage Gateway
- D) AWS Snow Family

**Answer: D) AWS Snow Family**

The AWS Snow Family is designed for physically transporting large amounts of data into and out of AWS.

### Automation and Optimization

**31. Which AWS service helps you optimize your AWS costs by identifying idle resources and suggesting cost-saving opportunities?**
- A) AWS Cost Explorer
- B) AWS Trusted Advisor
- C) AWS Budgets
- D) AWS Cost and Usage Report

**Answer: B) AWS Trusted Advisor**

AWS Trusted Advisor provides recommendations to help optimize your AWS infrastructure, including cost optimization recommendations.

**32. What is the primary purpose of AWS Systems Manager Parameter Store?**
- A) To store and manage configuration data
- B) To store and manage encryption keys
- C) To store and manage log files
- D) To store and manage database credentials

**Answer: A) To store and manage configuration data**

Parameter Store provides secure, hierarchical storage for configuration data management and secrets management.

**33. Which service allows you to schedule automated actions for AWS resources?**
- A) AWS CloudWatch Events
- B) AWS Step Functions
- C) AWS Batch
- D) AWS Lambda

**Answer: A) AWS CloudWatch Events**

CloudWatch Events (now part of Amazon EventBridge) allows you to schedule automated actions for AWS resources.

**34. What is the main benefit of using AWS Systems Manager Patch Manager?**
- A) It automatically backs up your EC2 instances
- B) It automatically scans your EC2 instances for vulnerabilities
- C) It automates the process of patching EC2 instances
- D) It provides real-time monitoring of EC2 instance performance

**Answer: C) It automates the process of patching EC2 instances**

Patch Manager automates the process of patching your EC2 instances with both security updates and other types of updates.

**35. Which AWS service allows you to create pre-configured templates for EC2 instances?**
- A) Launch Templates
- B) CloudFormation
- C) Systems Manager
- D) OpsWorks

**Answer: A) Launch Templates**

Launch Templates allow you to create pre-configured templates for EC2 instances.

### Database Services

**36. What is the purpose of Amazon RDS Multi-AZ deployments?**
- A) To improve read performance
- B) To provide high availability
- C) To reduce costs
- D) To increase storage capacity

**Answer: B) To provide high availability**

RDS Multi-AZ deployments provide high availability through automatic failover to a standby instance in case of a failure.

**37. Which AWS service should you use for a NoSQL database requiring consistent single-digit millisecond latency?**
- A) Amazon RDS
- B) Amazon Redshift
- C) Amazon DynamoDB
- D) Amazon ElastiCache

**Answer: C) Amazon DynamoDB**

DynamoDB is a fully managed NoSQL database service designed to provide consistent single-digit millisecond latency.

**38. What is the maximum size of an Amazon RDS database instance?**
- A) 16 TB
- B) 32 TB
- C) 64 TB
- D) 128 TB

**Answer: C) 64 TB**

The maximum storage size for an Amazon RDS database instance is 64 TB for most database engines.

**39. Which AWS service would you use for real-time analysis of streaming data?**
- A) Amazon Redshift
- B) Amazon Kinesis
- C) Amazon Athena
- D) Amazon EMR

**Answer: B) Amazon Kinesis**

Amazon Kinesis is designed for real-time processing of streaming data.

**40. What is the primary purpose of DynamoDB Accelerator (DAX)?**
- A) To provide automatic scaling for DynamoDB
- B) To provide automatic backups for DynamoDB
- C) To provide a caching layer for DynamoDB
- D) To provide encryption for DynamoDB

**Answer: C) To provide a caching layer for DynamoDB**

DAX is an in-memory cache for DynamoDB that improves read performance.

### Disaster Recovery and Business Continuity (continued)

**41. What is the RTO (Recovery Time Objective)?**
- A) The maximum acceptable time for a system to be unavailable
- B) The maximum acceptable amount of data loss
- C) The time it takes to restore a system from backup
- D) The time it takes to detect a system failure

**Answer: A) The maximum acceptable time for a system to be unavailable**

RTO is the maximum acceptable time for a system to be unavailable following a disaster.

**42. What is the RPO (Recovery Point Objective)?**
- A) The maximum acceptable time for a system to be unavailable
- B) The maximum acceptable amount of data loss
- C) The point in time to which data must be recovered
- D) The point at which a system is considered recovered

**Answer: B) The maximum acceptable amount of data loss**

RPO is the maximum acceptable amount of data loss measured in time.

**43. Which AWS service provides continuous backup of your applications with point-in-time recovery?**
- A) AWS Backup
- B) AWS CloudFormation
- C) AWS Elastic Disaster Recovery
- D) AWS Systems Manager

**Answer: A) AWS Backup**

AWS Backup provides centralized backup management with point-in-time recovery capabilities.

**44. What is the most cost-effective disaster recovery strategy in AWS?**
- A) Multi-region active-active deployment
- B) Pilot light
- C) Warm standby
- D) Backup and restore

**Answer: D) Backup and restore**

Backup and restore is the most cost-effective disaster recovery strategy, though it has the longest recovery time.

**45. Which of the following is NOT a benefit of using AWS Elastic Disaster Recovery?**
- A) Continuous replication of data
- B) Automated failover during disaster
- C) Ability to conduct non-disruptive recovery drills
- D) Support for both on-premises and cloud-based source servers

**Answer: B) Automated failover during disaster**

AWS Elastic Disaster Recovery doesn't provide fully automated failover; it requires initiating a recovery to launch the recovery instances.

### Cost Management and Optimization

**46. Which AWS tool provides cost and usage reports with comprehensive cost and usage data?**
- A) AWS Trusted Advisor
- B) AWS Cost Explorer
- C) AWS Budgets
- D) AWS Cost and Usage Report

**Answer: D) AWS Cost and Usage Report**

AWS Cost and Usage Report provides the most comprehensive set of cost and usage data available.

**47. What is the most cost-effective EC2 purchasing option for applications that can be interrupted but need to run for extended periods?**
- A) On-Demand Instances
- B) Reserved Instances
- C) Spot Instances
- D) Dedicated Hosts

**Answer: C) Spot Instances**

Spot Instances provide the largest discount but can be interrupted with short notice.

**48. Which AWS service helps you visualize, understand, and manage your AWS costs and usage over time?**
- A) AWS Budgets
- B) AWS Cost Explorer
- C) AWS Trusted Advisor
- D) AWS Organizations

**Answer: B) AWS Cost Explorer**

AWS Cost Explorer provides visualizations of your AWS costs and usage over time.

**49. What is the recommended way to optimize costs for predictable workloads?**
- A) Use On-Demand Instances
- B) Use Reserved Instances
- C) Use Spot Instances
- D) Use Auto Scaling

**Answer: B) Use Reserved Instances**

Reserved Instances provide a significant discount compared to On-Demand pricing for predictable workloads.

**50. Which AWS service helps you track and allocate costs by tagging resources?**
- A) AWS Cost Categories
- B) AWS Budgets
- C) AWS Cost Allocation Tags
- D) AWS Organizations

**Answer: C) AWS Cost Allocation Tags**

Cost Allocation Tags help you organize your resources and cost allocation tracking.

## Essential AWS CLI Commands for SysOps

### EC2 Management

```bash
# List all EC2 instances
aws ec2 describe-instances

# Filter EC2 instances by state
aws ec2 describe-instances --filters "Name=instance-state-name,Values=running"

# Start/Stop EC2 instances
aws ec2 start-instances --instance-ids i-1234567890abcdef0
aws ec2 stop-instances --instance-ids i-1234567890abcdef0

# Create an AMI from an instance
aws ec2 create-image --instance-id i-1234567890abcdef0 --name "MyInstanceAMI"

# Describe all AMIs owned by you
aws ec2 describe-images --owners self

# Get console output from instance
aws ec2 get-console-output --instance-id i-1234567890abcdef0
```

### Auto Scaling

```bash
# Describe Auto Scaling groups
aws autoscaling describe-auto-scaling-groups

# Update an Auto Scaling group
aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-asg --min-size 2 --max-size 10

# Execute a scaling policy
aws autoscaling execute-policy --auto-scaling-group-name my-asg --policy-name my-scaling-policy

# Set desired capacity
aws autoscaling set-desired-capacity --auto-scaling-group-name my-asg --desired-capacity 3
```

### CloudWatch

```bash
# List CloudWatch alarms
aws cloudwatch describe-alarms

# Get metrics for an EC2 instance
aws cloudwatch get-metric-statistics --namespace AWS/EC2 --metric-name CPUUtilization --dimensions Name=InstanceId,Value=i-1234567890abcdef0 --start-time 2023-01-01T00:00:00Z --end-time 2023-01-02T00:00:00Z --period 3600 --statistics Average

# Create an alarm
aws cloudwatch put-metric-alarm --alarm-name high-cpu-usage --alarm-description "High CPU usage" --metric-name CPUUtilization --namespace AWS/EC2 --dimensions Name=InstanceId,Value=i-1234567890abcdef0 --statistic Average --period 300 --evaluation-periods 3 --threshold 80 --comparison-operator GreaterThanThreshold --alarm-actions arn:aws:sns:region:account-id:topic-name
```

### S3

```bash
# List all S3 buckets
aws s3 ls

# List objects in a bucket
aws s3 ls s3://mybucket

# Copy local file to S3
aws s3 cp file.txt s3://mybucket/

# Copy S3 object to local file
aws s3 cp s3://mybucket/file.txt .

# Sync local directory with S3
aws s3 sync local-dir s3://mybucket/remote-dir

# Enable bucket versioning
aws s3api put-bucket-versioning --bucket mybucket --versioning-configuration Status=Enabled
```

### IAM

```bash
# List IAM users
aws iam list-users

# Create IAM user
aws iam create-user --user-name newuser

# Attach policy to user
aws iam attach-user-policy --user-name newuser --policy-arn arn:aws:iam::aws:policy/AdministratorAccess

# List attached policies for a user
aws iam list-attached-user-policies --user-name newuser

# Create access key for a user
aws iam create-access-key --user-name newuser
```

### VPC and Networking

```bash
# Describe VPCs
aws ec2 describe-vpcs

# Describe subnets
aws ec2 describe-subnets

# Describe security groups
aws ec2 describe-security-groups

# Create a security group
aws ec2 create-security-group --group-name MySG --description "My security group" --vpc-id vpc-1234567890abcdef0

# Add rule to security group
aws ec2 authorize-security-group-ingress --group-id sg-1234567890abcdef0 --protocol tcp --port 22 --cidr 203.0.113.0/24
```

### RDS

```bash
# List RDS instances
aws rds describe-db-instances

# Create a DB snapshot
aws rds create-db-snapshot --db-instance-identifier mydbinstance --db-snapshot-identifier mydbsnapshot

# Restore DB instance from snapshot
aws rds restore-db-instance-from-db-snapshot --db-instance-identifier mynewdbinstance --db-snapshot-identifier mydbsnapshot

# Modify DB instance
aws rds modify-db-instance --db-instance-identifier mydbinstance --allocated-storage 10 --apply-immediately
```

### CloudFormation

```bash
# List stacks
aws cloudformation list-stacks

# Create stack
aws cloudformation create-stack --stack-name mystack --template-body file://template.yaml --parameters ParameterKey=KeyName,ParameterValue=mykey

# Update stack
aws cloudformation update-stack --stack-name mystack --template-body file://updated-template.yaml

# Delete stack
aws cloudformation delete-stack --stack-name mystack

# Validate template
aws cloudformation validate-template --template-body file://template.yaml
```

### Systems Manager

```bash
# List all managed instances
aws ssm describe-instance-information

# Run a command on instances
aws ssm send-command --document-name "AWS-RunShellScript" --parameters 'commands=["ls -la"]' --targets "Key=instanceids,Values=i-1234567890abcdef0"

# Get command execution status
aws ssm list-command-invocations --command-id "command-id" --details

# Get parameter from Parameter Store
aws ssm get-parameter --name "my-parameter" --with-decryption

# Create a parameter in Parameter Store
aws ssm put-parameter --name "my-parameter" --value "my-value" --type String
```

### Lambda

```bash
# List Lambda functions
aws lambda list-functions

# Invoke a Lambda function
aws lambda invoke --function-name my-function --payload '{"key":"value"}' output.txt

# Update function code
aws lambda update-function-code --function-name my-function --zip-file fileb://function.zip

# Get function configuration
aws lambda get-function-configuration --function-name my-function
```

### Other Useful Commands

```bash
# Get AWS account ID
aws sts get-caller-identity

# List all regions
aws ec2 describe-regions

# List all availability zones in a region
aws ec2 describe-availability-zones --region us-east-1

# Get service quotas
aws service-quotas list-service-quotas --service-code ec2

# Get current AWS CLI configuration
aws configure list
```
