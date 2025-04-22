# Amazon SOA-C02 Sample Questions

## Question # 1
A SysOps administrator creates two VPCs, VPC1 and VPC2, in a company’s AWS accountThe SysOps administrator deploys a Linux Amazon EC2 instance in VPC1 and deploys anAmazon RDS for MySQL DB instance in VPC2. The DB instance is deployed in a privatesubnet. An application that runs on the EC2 instance needs to connect to the database.What should the SysOps administrator do to give the EC2 instance the ability to connect tothe database?

   - A. Enter the DB instance connection string into the VPC1 route table.
   - B. Configure VPC peering between the two VPCs.
   - C. Add the same IPv4 CIDR range for both VPCs.
   - D. Connect to the DB instance by using the DB instance’s public IP address. 

Answer: B
Explanation:VPC peering allows two VPCs to communicate with each other securely. By configuringVPC peering between the two VPCs, the SysOps administrator will be able to give the EC2instance in VPC1 the ability to connect to the database in VPC2. Once the VPC peering isconfigured, the EC2 instance will be able to communicate with the database using theprivate IP address of the DB instance in the private subnet. 


## Question # 2
A company has a policy that requires all Amazon EC2 instances to have a specific set oftags. If an EC2 instance does not have the required tags, the noncompliant instance shouldbe terminated.What is the MOST operationally efficient solution that meets these requirements?

A. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to send all EC2instance state changes to an AWS Lambda function to determine if each instance iscompliant. Terminate any noncompliant instances.
B. Create an IAM policy that enforces all EC2 instance tag requirements. If the requiredtags are not in place for an instance, the policy will terminate noncompliant instance.
C. Create an AWS Lambda function to determine if each EC2 instance is compliant andterminate an instance if it is noncompliant. Schedule the Lambda function to invoke every 5minutes.
D. Create an AWS Config rule to check if the required tags are present. If an EC2 instanceis noncompliant, invoke an AWS Systems Manager Automation document to terminate theinstance.

Answer: D
Explanation: https://docs.aws.amazon.com/systems-manager/latest/userguide/systemsmanager-automation.html 


## Question # 3
A company has a compliance requirement that no security groups can allow SSH ports tobe open to all IP addresses. A SysOps administrator must implement a solution that willnotify the company's SysOps team when a security group rule violates this requirement.The solution also must remediate the security group rule automatically.Which solution will meet these requirements?

A. Create an Amazon EventBridge (Amazon CloudWatch Events) rule that invokes anAWS Lambda function when a security group changes. Configure the Lambda function toevaluate the security group for compliance, remove all inbound security group rules on allports, and notify the SysOps team if the security group is noncompliant.
B. Create an AWS CloudTrail metric filter for security group changes. Create an AmazonCloudWatch alarm to notify the SysOps team through an Amazon Simple NotificationService (Amazon SNS) topic when (he metric is greater than 0. Subscribe an AWS Lambdafunction to the SNS topic to remediate the security group rule by removing the rule.
C. Activate the AWS Config restricted-ssh managed rule. Add automatic remediation to theAWS Config rule by using the AWS Systems Manager Automation AWSDisablePublicAccessForSecurityGroup runbook. Create an Amazon EventBridge (AmazonCloudWatch Events) rule to notify the SysOps team when the rule is noncompliant.
D. Create an AWS CloudTrail metric filter for security group changes. Create an AmazonCloudWatch alarm for when the metric is greater than 0. Add an AWS Systems Manageraction to the CloudWatch alarm to suspend the security group by using the SystemsManager Automation AWS-DisablePublicAccessForSecurityGroup runbook when the alarmis in ALARM state. Add an Amazon Simple Notification Service (Amazon SNS) topic as asecond target to notify the SysOps team.

Answer: C 


### Question # 4
A company has an application that is deployed 10 two AWS Regions in an active-passiveconfiguration. The application runs on Amazon EC2 instances behind an Application LoadBalancer (ALB) in each Region. The instances are in an Amazon EC2 Auto Scaling groupin each Region. The application uses an Amazon Route 53 hosted zone (or DNS. ASysOps administrator needs to configure automatic failover to the secondary Region.What should the SysOps administrator do to meet these requirements?

A. Configure Route 53 alias records that point to each ALB. Choose a failover routingpolicy. Set Evaluate Target Health to Yes.
B. Configure CNAME records that point to each ALB. Choose a failover routing policy. SetEvaluate Target Health to Yes.
C. Configure Elastic Load Balancing (ELB) health checks for the Auto Scaling group. Add atarget group to the ALB in the primary Region. Include the EC2 instances in the secondaryRegion astargets.
D. Configure EC2 health checks for the Auto Scaling group. Add a target group to the ALBin the primary Region. Include the EC2 instances in the secondary Region as targets.

Answer: A


## Question # 5
A company stores its data in an Amazon S3 bucket. The company is required to classifythe data and find any sensitive personal information in its S3 files.Which solution will meet these requirements? 

A. Create an AWS Config rule to discover sensitive personal information in the S3 files andmark them as noncompliant.
B. Create an S3 event-driven artificial intelligence/machine learning (AI/ML) pipeline toclassify sensitive personal information by using Amazon Recognition.
C. Enable Amazon GuardDuty. Configure S3 protection to monitor all data inside AmazonS3.  
D. Enable Amazon Macie. Create a discovery job that uses the managed data identifier. 

Answer: D
Explanation: Amazon Macie is a security service designed to help organizations find,classify, and protect sensitive data stored in Amazon S3. Amazon Macie uses machinelearning to automatically discover, classify, and protect sensitive data in Amazon S3.Creating a discovery job with the managed data identifier will allow Macie to identifysensitive personal information in the S3 files and classify it accordingly. Enabling AWSConfig and Amazon GuardDuty will not help with this requirement as they are not designedto automatically classify and protect data. 


## Question # 6
A company has an application that customers use to search for records on a website. Theapplication's data is stored in an Amazon Aurora DB cluster. The application's usage variesby season and by day of the week.The website's popularity is increasing, and the website is experiencing slower performancebecause of increased load on the DB cluster during periods of peak activity. Theapplication logs show that the performance issues occur when users are searching forinformation. The same search is rarely performed multiple times.A SysOps administrator must improve the performance of the platform by using a solutionthat maximizes resource efficiency.Which solution will meet these requirements?

A. Deploy an Amazon ElastiCache for Redis cluster in front of the DB cluster. Modify theapplication to check the cache before the application issues new queries to the database.Add the results of any queries to the cache.
B. Deploy an Aurora Replica for the DB cluster. Modify the application to use the readerendpoint for search operations. Use Aurora Auto Scaling to scale the number of replicasbased on load. Most Voted
C. Use Provisioned IOPS on the storage volumes that support the DB cluster to improveperformance sufficiently to support the peak load on the application.
D. Increase the instance size in the DB cluster to a size that is sufficient to support the peak load on the application. Use Aurora Auto Scaling to scale the instance size based on load.

Answer: B
Explanation: https://docs.amazonaws.cn/en_us/AmazonRDS/latest/AuroraUserGuide/aurora-replicasadding.html


## Question # 7
A company’s reporting job that used to run in 15 minutes is now taking an hour to run. Anapplication generates the reports. The application runs on Amazon EC2 instances andextracts data from an Amazon RDS for MySQL database.A SysOps administrator checks the Amazon CloudWatch dashboard for the RDS instanceand notices that the Read IOPS metrics are high, even when the reports are not running.The SysOps administrator needs to improve the performance and the availability of theRDS instance.Which solution will meet these requirements?

A. Configure an Amazon ElastiCache cluster in front of the RDS instance. Update thereporting job to query the ElastiCache cluster.
B. Deploy an RDS read replica. Update the reporting job to query the reader endpoint.
C. Create an Amazon CloudFront distribution. Set the RDS instance as the origin. Updatethe reporting job to query the CloudFront distribution.
D. Increase the size of the RDS instance. 

Answer: B
Explanation:Using an RDS read replica will improve the performance and availability of the RDSinstance by offloading read queries to the replica. This will also ensure that the reportingjob completes in a timely manner and does not affect the performance of other queries thatmight be running on the RDS instance. Additionally, updating the reporting job to query thereader endpoint will ensure that all read queries are directed to the read replica.Reference:[1] https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html


## Question # 8
A Sysops administrator needs to configure automatic rotation for Amazon RDS databasecredentials. The credentials must rotate every 30 days. The solution must integrate withAmazon RDS.Which solution will meet these requirements with the LEAST operational overhead? 

A. Store the credentials in AWS Systems Manager Parameter Store as a secure string.Configure automatic rotation with a rotation interval of 30 days.
B. Store the credentials in AWS Secrets Manager. Configure automatic rotation with arotation interval of 30 days.
C. Store the credentials in a file in an Amazon S3 bucket. Deploy an AWS Lambda functionto automatically rotate the credentials every 30 days.
D. Store the credentials in AWS Secrets Manager. Deploy an AWS Lambda function toautomatically rotate the credentials every 30 days. 

Answer: B
Explanation: Storing the credentials in AWS Secrets Manager and configuring automatic rotation with a rotation interval of 30 days is the most efficient way to meet the requirements with the least operational overhead. AWS Secrets Manager automatically rotates the credentials at the specified interval, so there is no need for an additional AWS Lambda function or manual rotation. Additionally, Secrets Manager is integrated with Amazon RDS, so the credentials can be easily used with the RDS database


## Question # 9
A company updates its security policy to clarify cloud hosting arrangements for regulatedworkloads. Workloads that are identified as sensitive must run on hardware that is notshared with other customers or with other AWS accounts within the company.Which solution will ensure compliance with this policy?

A. Deploy workloads only to Dedicated Hosts.
B. Deploy workloads only to Dedicated Instances.
C. Deploy workloads only to Reserved Instances.
D. Place all instances in a dedicated placement group. 

Answer: A
Explanation:Dedicated Hosts are physical servers that are dedicated to a single customer, ensuring thatthe customer’s workloads are not shared with other customers or with other AWS accountswithin the company. This will ensure that the company’s security policy is followed and thatsensitive workloads are running on hardware that is not shared with other customers orwith other AWS accounts within the company. 


## Question # 10
A company is implementing a monitoring solution that is based on machine learning. Themonitoring solution consumes Amazon EventBridge (Amazon CloudWatch Events) eventsthat are generated by Amazon EC2 Auto Scaling. The monitoring solution providesdetection of anomalous behavior such as unanticipated scaling events and is configured asan EventBridge (CloudWatch Events) API destination.During initial testing, the company discovers that the monitoring solution is not receivingevents. However, Amazon CloudWatch is showing that the EventBridge (CloudWatchEvents) rule is being invoked. A SysOps administrator must implement a solution toretrieve client error details to help resolve this issue.Which solution will meet these requirements with the LEAST operational effort? 

A. Create an EventBridge (CloudWatch Events) archive for the event pattern to replay theevents. Increase the logging on the monitoring solution. Use replay to invoke themonitoring solution. Examine the error details.
B. Add an Amazon Simple Queue Service (Amazon SQS) standard queue as a dead-letterqueue for the target. Process the messages in the dead-letter queue to retrieve errordetails.
C. Create a second EventBridge (CloudWatch Events) rule for the same event pattern totarget an AWS Lambda function. Configure the Lambda function to invoke the monitoringsolution and to record the results to Amazon CloudWatch Logs. Examine the errors in thelogs.
D. Configure the EventBridge (CloudWatch Events) rule to send error messages to anAmazon Simple Notification Service (Amazon SNS) topic. 

Answer: A
Explanation: "In EventBridge, you can create an archive of events so that you can easilyreplay them at a later time. For example, you might want to replay events to recover fromerrors or to validate new functionality in your application."https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-archive.html 


## Question # 11
A company is hosting applications on Amazon EC2 instances. The company is hosting adatabase on an Amazon RDS for PostgreSQL DB instance. The company requires allconnections to the DB instance to be encrypted.What should a SysOps administrator do to meet this requirement?

A. Allow SSL connections to the database by using an inbound security group rule.
B. Encrypt the database by using an AWS Key Management Service (AWS KMS)encryption key.
C. Enforce SSL connections to the database by using a custom parameter group.
D. Patch the database with SSL/TLS by using a custom PostgreSQL extension. 

Answer: C
Explanation:https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/PostgreSQL.Concepts.General.SSL.htmAmazon RDS supports SSL/TLS encryption for connections to the database, and this canbe enabled by creating a custom parameter group and setting the rds.force_ssl parameterto 1. This will ensure that all connections to the database are encrypted, protecting the dataand maintaining compliance with the company's requirements.l 


## Question # 12
A company needs to take an inventory of applications that are running on multiple AmazonEC2 instances. The company has configured users and roles with the appropriatepermissions for AWS Systems Manager. An updated version of Systems Manager Agenthas been installed and is running on every instance. While configuring an inventorycollection, a SysOps administrator discovers that not all the instances in a single subnetare managed by Systems Manager.What must the SysOps administrator do to fix this issue?

A. Ensure that all the EC2 instances have the correct tags for Systems Manager access.
B. Configure AWS Identity and Access Management Access Analyzer to determine andautomatically remediate the issue.
C. Ensure that all the EC2 instances have an instance profile with Systems Manageraccess.
D. Configure Systems Manager to use an interface VPC endpoint.

Answer: C
Explanation:Ensuring that all the EC2 instances have an instance profile with Systems Manager accessis the most effective way to fix this issue. Having an instance profile with Systems Manageraccess will allow the SysOps administrator to configure the inventory collection for all theinstances in the subnet, regardless of whether or not they are managed by SystemsManager. 


## Question # 13
A company recently migrated its application to a VPC on AWS. An AWS Site-to-Site VPN connection connects the company’s on-premises network to the VPC. The application retrieves customer data from another system that resides on premises. The application uses an on-premises DNS server to resolve domain records. After the migration, the application is not able to connect to the customer data because of name resolution errors.Which solution will give the application the ability to resolve the internal domain names? 

A. Launch EC2 instances in the VPC. On the EC2 instances, deploy a custom DNSforwarder that forwards all DNS requests to the on-premises DNS server. Create anAmazon Route 53 private hosted zone that uses the EC2 instances for name servers.
B. Create an Amazon Route 53 Resolver outbound endpoint. Configure the outboundendpoint to forward DNS queries against the on-premises domain to the on-premises DNSserver.
C. Set up two AWS Direct Connect connections between the AWS environment and theon-premises network. Set up a link aggregation group (LAG) that includes the twoconnections. Change the VPC resolver address to point to the on-premises DNS server.
D. Create an Amazon Route 53 public hosted zone for the on-premises domain. Configurethe network ACLs to forward DNS requests against the on-premises domain to the Route53 public hosted zone.

Answer: B
Explanation:https://docs.aws.amazon.com/zh_tw/Route53/latest/DeveloperGuide/resolver-forwardingoutbound-queries.... 


## Question # 14
A company needs to archive all audit logs for 10 years. The company must protect the logsfrom any future edits.Which solution will meet these requirements?

A. Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. Configure AWSKey Management Service (AWS KMS) encryption.
B. Store the data in an Amazon S3 Glacier vault. Configure a vault lock policy for writeonce, read-many (WORM) access.
C. Store the data in Amazon S3 Standard-Infrequent Access (S3 Standard-IA). Configureserver-side encryption.
D. Store the data in Amazon S3 Standard-Infrequent Access (S3 Standard-IA). Configuremulti-factor authentication (MFA). 

Answer: B
Explanation: To meet the requirements of the workload, a company should store the datain an Amazon S3 Glacier vault and configure a vault lock policy for write-once, read-many(WORM) access. This will ensure that the data is stored securely and cannot be edited inthe future. The other solutions (storing the data in an Amazon Elastic Block Store (AmazonEBS) volume and configuring AWS Key Management Service (AWS KMS) encryption,storing the data in Amazon S3 Standard-Infrequent Access (S3 Standard-IA) andconfiguring server-side encryption, or storing the data in Amazon S3 Standard-InfrequentAccess (S3 Standard-IA) and configuring multi-factor authentication (MFA)) will not meetthe requirements, as they do not provide a way to protect the audit logs from future edits.https://docs.aws.amazon.com/zh_tw/AmazonS3/latest/userguide/object-lock.html 


## Question # 15
A company has a memory-intensive application that runs on a fleet of Amazon EC2instances behind an Elastic Load Balancer (ELB). The instances run in an Auto Scalinggroup. A Sysops administrator must ensure that the application can scale based on thenumber of users that connect to the application.Which solution will meet these requirements? 

A. Create a scaling policy that will scale the application based on theActiveConnectionCount Amazon CloudWatch metric that is generated from the ELB.
B. Create a scaling policy that will scale the application based on the mem used AmazonCloudWatch metric that is generated from the ELB.
C. Create a scheduled scaling policy to increase the number of EC2 instances in the AutoScaling group to support additional connections.
D. Create and deploy a script on the ELB to expose the number of connected users as acustom Amazon CloudWatch metric. Create a scaling policy that uses the metric. 

Answer: D
Explanation: This solution will allow the application to scale based on the number of usersthat connect to the application. The other solutions (creating a scaling policy that uses theActiveConnectionCount Amazon CloudWatch metric generated from the ELB, creating ascaling policy that uses the mem used Amazon CloudWatch metric generated from theELB, or creating a scheduled scaling policy to increase the number of EC2 instances in theAuto Scaling group to support additional connections) will not meet the requirements, asthey do not allow the application to scale based on the number of users that connect to theapplication. 


## Question # 16
A company needs to automatically monitor an AWS account for potential unauthorizedAWS Management Console logins from multiple geographic locations.Which solution will meet this requirement?

A. Configure Amazon Cognito to detect any compromised 1AM credentials.
B. Set up Amazon Inspector. Scan and monitor resources for unauthorized logins.
C. Set up AWS Config. Add the iam-policy-blacklisted-check managed rule to the account.
D. Configure Amazon GuardDuty to monitor theUnauthorizedAccess:IAMUser/ConsoleLoginSuccess finding.

Answer: D


## Question # 17
A company has two VPC networks named VPC A and VPC B. The VPC A CIDR block is10.0.0.0/16 and the VPC B CIDR block is 172.31.0.0/16. The company wants to establish aVPC peering connection named pcx-12345 between both VPCs.Which rules should appear in the route table of VPC A after configuration? (Select TWO.)

A. Destination: 10.0.0.0/16, Target: Local
B. Destination: 172.31.0.0/16, Target: Local
C. Destination: 10.0.0.0/16, Target: pcx-12345
D. Destination: 172.31.0.0/16, Target: pcx-12345
E. Destination: 10.0.0.0/16. Target: 172.31.0.0/16

Answer: A,D
Explanation: https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-routing.html 


## Question # 18
A company needs to implement a managed file system to host Windows file shares for users on premises. Resources in the AWS Cloud also need access to the data on these file shares. A SysOps administrator needs to present the user file shares on premises and make the user file shares available on AWS with minimum latency. What should the SysOps administrator do to meet these requirements? 

A. Set up an Amazon S3 File Gateway.
B. Set up an AWS Direct Connect connection.
C. Use AWS DataSync to automate data transfers between the existing file servers andAWS.
D. Set up an Amazon FSx File Gateway. 

Answer: D
Explanation:Amazon FSx provides a fully managed file system that is optimized for Windows-basedworkloads and can be used to create file shares that can be accessed both on premisesand in the AWS Cloud. The file shares that are created in Amazon FSx are highly availableand can be accessed with low latency. Additionally, Amazon FSx supports Windows-basedauthentication, making it easy to integrate with existing Windows user accounts.References: [1] https://aws.amazon.com/fsx/ [2] https://aws.amazon.com/storage/filestorage/ [3] https://docs.aws.amazon.com/fsx/latest/WindowsGuide/whatis.html [4] https://aws.amazon.com/premiumsupport/knowledge-center/fsx-file-gatewayaccess/ 


## Question # 19
A company has created a NAT gateway in a public subnet in a VPC. The VPC alsocontains a private subnet that includes Amazon EC2 instances. The EC2 instances use theNAT gateway to access the internet to download patches and updates. The company hasconfigured a VPC flow log for the elastic network interface of the NAT gateway. Thecompany is publishing the output to Amazon CloudWatch Logs.A SysOps administrator must identify the top five internet destinations that the EC2instances in the private subnet communicate with for downloads.What should the SysOps administrator do to meet this requirement in the MOSToperationally efficient way?

A. Use AWS CloudTrail Insights events to identify the top five internet destinations.
B. Use Amazon CloudFront standard logs (access logs) to identify the top five internetdestinations.
C. Use CloudWatch Logs Insights to identify the top five internet destinations.
D. Change the flow log to publish logs to Amazon S3. Use Amazon Athena to query the logfiles in Amazon S3.

Answer: C


## Question # 20
A SysOps administrator needs to delete an AWS CloudFormation stack that is no longer inuse. The CloudFormation stack is in the DELETE_FAILED state. The SysOps administratorhas validated the permissions that are required to delete the Cloud Formation stack.

A. The configured timeout to delete the stack was too low for the delete operation tocomplete.
B. The stack contains nested stacks that must be manually deleted fast.
C. The stack was deployed with the -disable rollback option.
D. There are additional resources associated with a security group in the stack
E. There are Amazon S3 buckets that still contain objects in the stack.

Answer: D,E


## Question # 21
A SysOps administrator needs to track the costs of data transfer between AWS Regions.The SysOps administrator must implement a solution to send alerts to an email distributionlist when transfer costs reach 75% of a specific threshold.What should the SysOps administrator do to meet these requirements?

A. Create an AWS Cost and Usage Report. Analyze the results in Amazon Athena.Configure an alarm to publish a message to an Amazon Simple Notification Service(Amazon SNS) topic when costs reach 75% of the threshold. Subscribe the emaildistribution list to the topic.
B. Create an Amazon CloudWatch billing alarm to detect when costs reach 75% of thethreshold. Configure the alarm to publish a message to an Amazon Simple NotificationService (Amazon SNS) topic. Subscribe the email distribution list to the topic.
C. Use AWS Budgets to create a cost budget for data transfer costs. Set an alert at 75% ofthe budgeted amount. Configure the budget to send a notification to the email distributionlist when costs reach 75% of the threshold.
D. Set up a VPC flow log. Set up a subscription filter to an AWS Lambda function toanalyze data transfer. Configure the Lambda function to send a notification to the emaildistribution list when costs reach 75% of the threshold. 

Answer: B
Explanation: The reason is that it uses the Amazon CloudWatch billing alarm which is abuilt-in service specifically designed to monitor and alert on cost usage of your AWSaccount, which makes it a more suitable solution for this use case. The alarm can beconfigured to detect when costs reach 75% of the threshold and when it is triggered, it canpublish a message to an Amazon Simple Notification Service (Amazon SNS) topic. Theemail distribution list can be subscribed to the topic, so that they will receive the alertswhen costs reach 75% of the threshold.AWS Budgets allows you to track and manage your costs, but it doesn't specifically focuson data transfer costs between regions, and it might not provide as much granularity asCloudWatch Alarms. 


## Question # 22
A company hosts a web application on an Amazon EC2 instance. The web server logs arepublished to Amazon CloudWatch Logs. The log events have the same structure andinclude the HTTP response codes that are associated with the user requests. Thecompany needs to monitor the number of times that the web server returns an HTTP 404response.  What is the MOST operationally efficient solution that meets these requirements?

A. Create a CloudWatch Logs metric filter that counts the number of times that the webserver returns an HTTP 404 response.
B. Create a CloudWatch Logs subscription filter that counts the number of times that theweb server returns an HTTP 404 response.
C. Create an AWS Lambda function that runs a CloudWatch Logs Insights query thatcounts the number of 404 codes in the log events during the past hour.
D. Create a script that runs a CloudWatch Logs Insights query that counts the number of404 codes in the log events during the past hour. 

Answer: A
Explanation: This is the most operationally efficient solution that meets the requirements,as it will allow the company to monitor the number of times that the web server returns anHTTP 404 response in real-time. The other solutions (creating a CloudWatch Logssubscription filter, an AWS Lambda function, or a script) will require additional steps andresources to monitor the number of times that the web server returns an HTTP 404response.A metric filter allows you to search for specific terms, phrases, or values in your log events,and then to create a metric based on the number of occurrences of those search terms.This allows you to create a CloudWatch Metric that can be used to create alarms anddashboards, which can be used to monitor the number of HTTP 404 responses returned bythe web server. 


## Question # 23
A company’s AWS Lambda function is experiencing performance issues. The Lambdafunction performs many CPU-intensive operations. The Lambda function is not running fastenough and is creating bottlenecks in the system.What should a SysOps administrator do to resolve this issue?

A. In the CPU launch options for the Lambda function, activate hyperthreading.
B. Turn off the AWS managed encryption.
C. Increase the amount of memory for the Lambda function.
D. Load the required code into a custom layer. 

Answer: C
Explanation:Increasing the amount of memory for the Lambda function will help to improve theperformance of the function. This is because the Lambda function is CPU-intensive andincreasing the memory will give it access to more CPU resources and help it run faster.The other options (activating hyperthreading in the CPU launch options for the Lambdafunction, turning off the AWS managed encryption, and loading the required code into acustom layer) will not help to improve the performance of the Lambda function and are notthe correct solutions for this issue.https://docs.aws.amazon.com/lambda/latest/dg/configuration-functioncommon.html#configuration-memory-... 


## Question # 24
A company plans to migrate several of its high performance computing (MPC) virtualmachines (VMs) to Amazon EC2 instances on AWS. A SysOps administrator must identifya placement group for this deployment. The strategy must minimize network latency andmust maximize network throughput between the HPC VMs.Which strategy should the SysOps administrator choose to meet these requirements?

A. Deploy the instances in a cluster placement group in one Availability Zone.
B. Deploy the instances in a partition placement group in two Availability Zones
C. Deploy the instances in a partition placement group in one Availability Zone
D. Deploy the instances in a spread placement group in two Availably Zones

Answer: A


## Question # 25
A company is using Amazon CloudFront to serve static content for its web application to itsusers. The CloudFront distribution uses an existing on-premises website as a customorigin.The company requires the use of TLS between CloudFront and the origin server. Thisconfiguration has worked as expected for several months. However, users are nowexperiencing HTTP 502 (Bad Gateway) errors when they view webpages that includecontent from the CloudFront distribution.What should a SysOps administrator do to resolve this problem?

A. Examine the expiration date on the certificate on the origin site. Validate that thecertificate has not expired. Replace the certificate if necessary.
B. Examine the hostname on the certificate on the origin site. Validate that the hostnamematches one of the hostnames on the CloudFront distribution. Replace the certificate ifnecessary.
C. Examine the firewall rules that are associated with the origin server. Validate that port443 is open for inbound traffic from the internet. Create an inbound rule if necessary.
D. Examine the network ACL rules that are associated with the CloudFront distribution.Validate that port 443 is open for outbound traffic to the origin server. Create an outboundrule if necessary. 

Answer: A
Explanation:HTTP 502 errors from CloudFront can occur because of the following reasons:There's an SSL negotiation failure because the origin is using SSL/TLS protocols andciphers that aren't supported by CloudFront. There's an SSL negotiation failure because the SSL certificate on the origin is expired orinvalid, or because the certificate chain is invalid.There's a host header mismatch in the SSL negotiation between your CloudFrontdistribution and the custom origin.The custom origin isn't responding on the ports specified in the origin settings of theCloudFront distribution.The custom origin is ending the connection to CloudFront too quickly.https://aws.amazon.com/premiumsupport/knowledge-center/resolve-cloudfront-connectionerror/ 
