# Monitoring and Reporting

1. CloudWatch for Production Alerts

Scenario: Your company's e-commerce platform experiences intermittent slowdowns during peak hours. The operations team needs to track performance metrics and set up automated alerts when CPU utilization exceeds 80%.

Question: Which AWS service should you use to collect metrics, monitor logs, and trigger alarms when thresholds are breached?

A) AWS CloudTrail
B) Amazon Inspector
C) Amazon CloudWatch
D) AWS Config
Answer: C) Amazon CloudWatch
CloudWatch provides real-time monitoring, log analysis, and alarm triggering for AWS resources.

# 2. EC2 Memory Monitoring

Scenario: A critical application running on an EC2 instance crashes unexpectedly. The development team suspects memory exhaustion but finds no CloudWatch metrics for memory usage.

Question: Why isn’t memory utilization visible in CloudWatch?

A) Memory metrics require a third-party tool
B) CloudWatch only tracks CPU by default
C) The instance type doesn’t support memory monitoring
D) CloudWatch doesn’t monitor memory usage by default
Answer: D) CloudWatch doesn’t monitor memory usage by default
You must install the CloudWatch agent to collect custom metrics like memory usage.

3. Rapid Response to API Failures

Scenario: Your finance team reports failed API calls when processing transactions. You need to track all AWS API activity to identify the root cause.

Question: Which AWS service logs all API calls made in your account?

A) VPC Flow Logs
B) AWS CloudTrail
C) AWS Config
D) CloudWatch Events
Answer: B) CloudTrail
CloudTrail records all AWS API activity, helping audit and troubleshoot issues.

# High Availability & Disaster Recovery

4. Multi-AZ Database Failover

Scenario: Your company’s customer database must remain available even during an AZ failure. The current RDS setup runs in a single Availability Zone.

Question: Which RDS configuration ensures automatic failover in case of an outage?

A) RDS Read Replicas
B) RDS Multi-AZ Deployment
C) Amazon DynamoDB Global Tables
D) Amazon Aurora Serverless
Answer: B) RDS Multi-AZ Deployment
Multi-AZ deployments maintain a standby replica in another AZ for automatic failover.

5. Auto Scaling Misconfiguration

Scenario: Your web application scales up during traffic spikes but fails to scale down, leading to unnecessary costs.

Question: What is the most likely issue?

A) The Auto Scaling group lacks proper scaling policies
B) The load balancer is misconfigured
C) CloudWatch alarms are not set up
D) The instances are using Reserved Capacity
Answer: A) The Auto Scaling group lacks proper scaling policies
Auto Scaling requires scaling policies (e.g., CPU-based or request-based) to scale down efficiently.

# Security & Compliance

6. Accidental S3 Bucket Exposure

Scenario: A developer mistakenly sets an S3 bucket to public, exposing sensitive customer data.

Question: Which AWS service can automatically detect and remediate this misconfiguration?

A) AWS Config with auto-remediation rules
B) AWS GuardDuty
C) Amazon Macie
D) AWS WAF
Answer: A) AWS Config with auto-remediation rules
AWS Config can detect non-compliant resources (like public S3 buckets) and trigger automated fixes.

7. Unauthorized SSH Access

Scenario: An EC2 instance is compromised due to an exposed SSH key.

Question: What is the most secure way to manage access to EC2 instances?

A) Store SSH keys in S3
B) Use IAM roles instead of long-term credentials
C) Rotate keys manually every 90 days
D) Disable SSH entirely
Answer: B) Use IAM roles instead of long-term credentials
IAM roles eliminate the need for storing SSH keys on instances.

# Networking & Troubleshooting

8. Private Subnet Internet Access

Scenario: An application in a private subnet cannot download security updates from the internet.

Question: What is the most likely missing component?

A) Internet Gateway
B) NAT Gateway
C) VPC Peering
D) Direct Connect
Answer: B) NAT Gateway
Private subnets require a NAT Gateway to access the internet while remaining secure.

9. VPC Traffic Blocked Unexpectedly

Scenario: A developer reports that traffic between two subnets is being blocked.

Question: What should you check first?

A) Security Groups
B) Network ACLs
C) Route Tables
D) AWS Shield
Answer: B) Network ACLs
Network ACLs (stateless) can block traffic at the subnet level, unlike Security Groups (stateful).

# Cost Optimization

10. Unexpected Spike in AWS Bill

Scenario: Your AWS costs suddenly increased by 40% last month.

Question: Which tool helps identify the cause?

A) AWS Trusted Advisor
B) AWS Cost Explorer
C) AWS Budgets
D) All of the above
Answer: D) All of the above

Cost Explorer visualizes spending trends.
Trusted Advisor flags underutilized resources.
Budgets alert when costs exceed thresholds.

11. Reducing Costs for Batch Processing

Scenario: Your nightly data processing job can tolerate interruptions.

Question: Which EC2 pricing model offers the highest savings?

A) On-Demand
B) Reserved Instances
C) Spot Instances
D) Dedicated Hosts
Answer: C) Spot Instances
Spot Instances provide up to 90% discount but can be interrupted.

