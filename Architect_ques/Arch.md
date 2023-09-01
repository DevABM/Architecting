## Architecting

   Solutions Architect Knowledge Badge Assessment
Single Choice
1)
Final Score: 93 %
 A solutions architect has been asked to help troubleshoot a Step Function's execution of a state machine. The users are noticing that occasionally, a task doesnt return a response and it creates a situation where the state
machine has to be reset.
 What can be added to the process flow in the state machine to help recover automatically from a stuck condition created by an un-returned result from
a task?
Create a Pass process flow to bypass the problem task. Use timeouts to avoid stuck executions.
 Comments: By default, the Amazon States Language doesn't specify
timeouts for state machine definitions. Without an explicit timeout, Step Functions often relies solely on a response from an activity worker to know that a task is complete. If something goes wrong and the TimeoutSeconds field isn't specified for an Activity or Task state,
an execution is stuck waiting for a response that will never come.
Remove the problem task from the state machine.
 Create a cron job that will automatically retrigger the state machine
after a certain amount of time.
Score: 0.79
Single Choice
2)
  A solutions architect must find the gateway that a database in an Amazon
EC2 instance on a private subnet that can initiate a session to the internet,

  but must not allow a session from the internet to initiate back to the
database.
 What gateway is it recommended to use for this private subnet directly for
this behavior for the Internet connectivity?
 Virtual Private Gateway
Transit Gateway
3)
 NAT Gateway
 Comments: NAT Gateway is used for Internet connectivity for private
subnets.
  Direct Connect Gateway
 Score: 0.79
Multiple Choice
 A company wants to allow their existing Active Directory users access to
AWS without having to recreate AWS IAM user accounts for every person.
 Which of the following methods is the most cost effective solution to meet
the requirements? (Select TWO)
X.509 Certificate OpenID Connect Cognito Identity Pool
Amazon Directory Services
 Comments: Wrong type of authentication method to leverage IAM for
internal users.
 Comments: AWS Directory Service for Microsoft Active Directory,
also known as AWS Managed Microsoft Active Directory (AD), enables your directory-aware workloads and AWS resources to use
managed Active Directory (AD) in AWS.

 SAML 2.0
Score: 0.00
Multiple Choice
4)
  What services can be used to perform hybrid network connectivity between
on-premise sites and Amazon VPCs? (Select TWO)
 Amazon VPC Reachability Analyzer VPC Peering
  AWS Direct Connect
 Comments: AWS Direct Connect can be used for an hybrid
networking connectivity.
  AWS Site-to-Site VPN
Comments: AWS Site-to-Site VPN can be used for an hybrid
networking connectivity.
Score: 0.79
Multiple Choice
 5)
 A developer with limited AWS knowledge recently joined a company. As part of their initial tasks, the developer was required to create a new bucket. However, while trying to create a new bucket, the developer kept on getting different errors. You are the senior developer of the company and you are tasked with sharing the bucket naming rules that AWS has for
creating new buckets.
What are the correct rules for creating new buckets? (Select THREE) Bucket name must be between 3-40 characters long.
 Bucket Names can use a dot(.) in the name, only if its used for
Amazon S3 static website.
 Comments: Use a dot (.) in the name only if the bucket's intended
purpose is to host an Amazon S3 static website; otherwise do not use
a dot (.) in the bucket name.

 Bucket names must not begin with xn--
Bucket names must start with a lowercase letter or number. Comments: Bucket names can be lowercase or a number.
Bucket name must be unique only for the region.
Bucket names can be formatted as an IP address (i.e. 198.68.10.2).
Score: 0.79
Single Choice
6)
 Comments: Bucket names should not begin with xn-- beginning
February 2020.
  After a budget review, you have noticed your Amazon EBS charges make up a significant portion of your bill. Currently, all EBS volumes are in use and required to stay active. All unattached volumes have been deleted after creating snapshots. Snapshots are managed with lifecycle policies and a
review has found no issue with retention.
 Which of the following options will best help you to reduce your EBS
spending?
 Detach the Amazon EBS volume from the Amazon EC2 instance.
This will make sure you are not being charged unless you are using
the EBS volume by attaching it to an EC2 instance.
 Generate snapshots of all volumes and only create and Amazon EBS
volume when the data is requested.
 Review the Amazon EBS volume size to make sure you did not over
provision EBS volumes.
Comments: If you are not consuming most of the storage on an EBS
volume, you can migrate to a smaller or less expensive EBS volume
type to reduce costs.
  Manually delete snapshots you are not currently using or anticipate
using within the next year.

  Score: 0.79
Multiple Choice
7)
 Your company uses an Identity Provider (IdP) for Single-sign on (SSO) and has tasked their solutions architect with connecting their AWS Account to the IdP so their users can leverage their corporate identity to access the
environment.
 What actions should the solutions architect take to meet these
requirements? (Select TWO)
 Create an AWS IAM User Group, associate the User Group with the
IdP and add users to the User Group.
 Create an AWS IAM User with AWS Management Console Access,
attach a policy with a trust relationship with the IdP.
 Create an AWS IAM Identity Provider by uploading the SAML
metadata document from your IdP.
Comments: This is correct, IdP metadata documents are provided in
an SAML format
 Create an AWS IAM Role with a trust relationship with the IdP.
 Comments: This is correct, Any IAM roles that will be used with IAM
federations require a trust policy to permit federation from the IdP
 Create an AWS IAM Identity Provider by uploading the JSON
metadata document from your IdP.
Score: 0.79
Multiple Choice
8)
What gateways can you use to make this connection? (Select THREE)
  You have to design a hybrid network architecture for an AWS Direct
Connect link for connecting to a customer's on-premise site.
  Egress only Gateway

  Transit Gateway
 Comments: Transit Gateway can be used for an AWS Direct Connect
link.
 NAT Gateway
 Direct Connect Gateway
 Comments: Direct Connect Gateway can be used for an AWS Direct
Connect link.
 Virtual Private Gateway
 Comments: Virtual Private Gateway can be used for an AWS Direct
Connect link.
 Internet Gateway
 Score: 0.79
Multiple Choice
9)
 Which of the following requirements must be met before you use Amazon
S3 File Gateway? (Select TWO)
 Configure your private networking, VPN, or AWS Direct Connect
between your Amazon Virtual Private Cloud (Amazon VPC) and the
on-premises environment where you are deploying your gateway.
Comments: File Gateway setup prerequisites requirements (https://
docs.aws.amazon.com/filegateway/latest/files3/Requirements.html)
  Configure Amazon Athena to count number of files transferred to
Amazon S3 bucket.
 Make sure your gateway can resolve the name of your AWS IAM
Identity Center.
Configure Microsoft Active Directory (AD).
 Comments: File Gateway setup prerequisites requirements (https://
docs.aws.amazon.com/filegateway/latest/files3/Requirements.html)
Score: 0.79

  Single Choice
10)
How can this issue be addressed?
 Your company is working on a serverless project based in Java. The developer team tested the application locally and then deployed it to AWS Lambda. While testing the application remotely, the Lambda function fails
with an access denied message.
  Include an IAM policy document at the root of the deployment
package and redeploy the Lambda function.
 Redeploy the Lambda function using an account with access to the
Administrator Access policy.
 Update the Lambda function's resource policy to include the missing
permissions.
 Update the Lambda function's execution role to include the missing
permissions.
Comments: In order to give your Lambda function the access to AWS
services and resources, Function execution role should be configured
with correct IAM policies.
Score: 0.79
Multiple Choice
  11)
Which of the following services could be used? (Select TWO) Amazon CloudFront
 As a cloud architect, you've been tasked with finding a way to restrict
access to a specific content for all users in a specific country.
 Comments: With CloudFront, you would create a distribution and use
CloudFront's geo-blocking feature to restrict access at the country
level.
 Also, AWS WAF can be used to restrict access to a CloudFront
distribution at the country-level. Alternatively, Amazon Route 53, can

  be used. However that would re-route requests from a restricted
geography, for example, to an error message page.
References:
Restricting the geographic distribution of your content Using AWS WAF to control access to your content
3 Ways to Geo-Restrict your App
Amazon Route 53 AWS Shield
AWS WAF
References:
Restricting the geographic distribution of your content Using AWS WAF to control access to your content
3 Ways to Geo-Restrict your App
AWS Network Firewall
Score: 0.79
Multiple Choice
12)
Which AWS service would they use instead? (Select TWO)
 Comments: With CloudFront, you would create a distribution and use
CloudFront's geo-blocking feature to restrict access at the country
level.
Also, AWS WAF can be used to restrict access to a CloudFront distribution at the country-level. Alternatively, Amazon Route 53, can be used. However that would re-route requests from a restricted
geography, for example, to an error message page.
   An on-premises customer uses GitHub, a code repository to store, track, and collaborate on software projects, and Jenkins, an open source automation server used to automate the building and testing of software.
The customer is migrating to AWS.
  AWS CodeBuild
 Comments: AWS CodeBuild is a fully managed continuous
integration service that compiles source code, runs tests, and

  produces ready-to-deploy software packages."
 AWS CodeCommit
 Comments: AWS CodeCommit is a secure, highly scalable, managed
source control service that hosts private Git repositories."
 AWS CodeDeploy
13)
 AWS CloudFormation
 Score: 0.79
Single Choice
 A company has several unencrypted Amazon EBS snapshots in their Amazon VPC. The solutions architect must ensure that all of the new EBS volumes restored from the unencrypted snapshots are automatically
encrypted.
 Which of these options will satisfy the requirement with the least
administrative effort?
 Enable the EBS Encryption By Default feature for specific EBS
volumes
 Launch new EBS volumes and encrypt them using an asymmetric
customer master key (CMK)
 Launch new EBS volumes and specify the symmetric customer
master key (CMK) for encryption
Enable the EBS Encryption By Default feature for the AWS Region.
 Comments: This is the correct answer and best solution which
requires no admin work
Score: 0.79
Single Choice
14)
  The finance team in your organization needs to send data to your team's
backend workflow. You want to filter inbound traffic at the subnet level

   What do you need to setup to complete this workflow?
 Create a Network Access Control List (NACL).
 Enable inbound traffic from the other team's service. Since NACL is
stateful, it will automatically enable outbound returning traffic.
 Create a Security Group.
 Enable inbound connections from the other team. Enable outbound
returning traffic to the other team's service
 Create a Network Access Control List (NACL).
Enable inbound traffic from the other team's service; enable outbound
traffic to return data to the other team's service
Comments: NACL is the correct option as it works at the subnet level.
NACL is not stateful so you must specify the inbound and outbound
traffic.
   Create a Security Group.
Enable inbound connections from the other team. Since Security Group is stateful, it will automatically enable outbound returning
traffic.
Score: 0.79
Single Choice
  15)
 You are a systems administrator for an e-commerce business running on AWS. Part of your duties involve deploying and managing the backups for the company's cloud workloads; including Amazon RDS, Amazon S3, and
multiple Amazon EC2 instances backed by Amazon EBS.
 Which of the following would be the BEST option to manage backups for
these services?
AWS Elastic Disaster Recovery (DRS)
AWS Backup
Comments: AWS Backup provides a centralized policy based
while allowing returning traffic back to the finance team's service.

  solution, to handle the auditing, reporting, and management of
backups across multiple AWS Services.
S3 Object Lock RDS Snapshots
Score: 0.79
Single Choice
16)
What is the most operationally efficient way to accomplish this task?
  Your organization's operational lead has decided to build a cost effective centralized logging solution for multiple AWS accounts. The solution includes an Amazon S3 bucket in the centralized logging account. The logs
must be deleted after three months to minimize cost.
  Archive objects to the S3 Glacier Flexible Retrieval storage class for
three months and delete manually.
  Expiration actions
Comments: These actions define when objects expire. Amazon S3
deletes expired objects on your behalf. (https:// docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-
mgmt.html)
 Transition actions
17)
 Transition objects to the S3 Standard-IA storage class 30 days after
creating them and delete manually/
Score: 0.79
Single Choice
  A company is currently running a SQL Server database on-premises and is
interested in migrating the database to Amazon Aurora.
 Which of the following methods will help migrate the existing database to
AWS?

  Use the Schema Conversion Tool to create a new schema for this
heterogenous migration. The schema will allow you to load the data
directly to Amazon Aurora.
 Use the Schema Conversion Tool to convert the existing schema for
a new database engine. Once the schema is available, use the Database Migration Service to load the data into a new Amazon
Aurora Database.
Comments: A heterogenous migration will require the Schema
Conversion Tool to convert the data before the Database Migration
Service can load the data into a new engine type.
  Use the Schema Conversion Tool to create a new schema for this
homogenous migration. A new schema will allow you to load the data
directly to Amazon Aurora.
 Use the Database Migration Service to directly read the data from the
existing SQL Server database and load the data into a new Amazon
Aurora Database.
Score: 0.79
Multiple Choice
18)
How can the route tables in this VPC be distributed? (SELECT TWO)
  An Amazon VPC with multiple public and private subnets requires that
each subnet has communication to the Internet.
  Attach the same route table for all the private subnets and don't add
any additional routes.
 Attach the same route table for all the public subnets and don't add
any additional routes.
 Attach the same route table for all the public subnets and add a route
with IP destination of 0.0.0.0/0 route to a Internet Gateway.
 Comments: Public subnets must have a route to a Internet Gateway
to exit to the Internet.

  No new route tables should be added, because Amazon VPC
automatically distributes the route tables and routes for public and
private subnets.
 Attach the same route table for all the private subnets and add a
route with IP destination of 0.0.0.0/0 route to a NAT Gateway.
Comments: Private subnets must have a route to a NAT Gateway to
exit to the Internet.
Score: 0.79
Single Choice
  19)
 As the solutions architect in an organization, you are given an assignment to build an application in AWS which is required to be deployed in an Auto Scaling group of On-Demand Amazon EC2 instances and a MongoDB database. It is expected that the database will have high-throughput
workloads performing small, random I/O operations.
 Which of the following is the most performant Amazon EBS type to use for
your database?
Cold HDD - sc1
Provisioned IOPS SSD - io1
General Purpose SSD - gp2 Throughput Optimized HDD - st1
 Comments: Provisioned IOPS SSD volumes are designed to meet
the needs of I/O-intensive workloads, particularly database workloads, that are sensitive to storage performance and
consistency.
Score: 0.79
Single Choice
20)
  What native Amazon VPC security feature can be used to allow and deny
network traffic with the same rule at the subnet level?

  Security Groups
AWS Network Firewall
  Network Access Control List (NACL)
 Comments: A NACL has reach at the subnet level.
 AWS WAF
 Score: 0.79
Multiple Choice
21)
 As an AWS solutions architect, you've been asked to scale out write performance across multiple Availability Zones within an AWS Region.
You've decided to deploy the Aurora Multi-Master.
 Which of the following are features of an Amazon Aurora Multi-Master
deployment option? (Select THREE)
You can enable cross-Region replicas from multi-master clusters. Features high availability with brief downtime during failover. Available with Amazon Aurora PostgreSQL-Compatible edition.
Supports up to four READ/WRITE nodes.
References:
Overview of Aurora multi-master clusters
Available with Amazon Aurora MySQL-Compatible edition.
 Features continuous availability with no failover when a writer DB
instance becomes unavailable.
 Comments: "Currently, you can have a maximum of four DB
instances in a multi-master cluster."
Score: 0.27
 Single Choice

 22)
What is the best possible solution from an operation point of view?
 A company runs a batch application in the AWS Cloud hosted on 200+ Amazon EC2 instances. As a solutions architect, you are asked to push debug logs to an Amazon S3 bucket every 2:00 AM for all the EC2
instances.
     Create a schedule in AWS Systems Manager Maintenance window to
move the logs to S3 bucket every 2:00 AM in the morning.
Comments: This is the correct answer as SSM Maintenance window
is used to schedule patching and some automation workflows (https:// docs.aws.amazon.com/systems-manager/latest/userguide/state-
manager-vs-maintenance-windows.html)
Score: 0.79
Single Choice
  23)
Use Systems Manager Distributor to transfer the logs every 2:00 AM
on all the AWS Systems Manager Managed instances.
Inject a user script via Ops Work to all of the Amazon EC2 instances
that will push the logs to this Amazon S3 bucket.
Use SSM Session Manager to run a shell script on all Amazon EC2
instances 2:00 AM in the morning.
 Your company is developing a new internal application in the next few days, and the development team would like to create a private subdomain accounting.example.com accessible within their Amazon VPC in order to test the application. You already have a private hosted zone for
example.com associated with this VPC.
 What do you need to do in order to allow resolution
of .accounting.example.com within the VPC?
 Create a new private hosted zone with the desired name and
associate it with the Amazon VPC.

  Create a new private hosted zone with the desired name, associate it
with the VPC and create a delegation record in the parent zone.
Comments: You cannot create DNS records in a private hosted zone
to delegate responsibility for a subdomain.
 Use health checks.
Score: 0.00
Single Choice
24)
Which one of the following database can best satisfy the requirements?
Amazon DynamoDB
Amazon ElastiCache with Redis cluster mode enabled
25)
A customer has a Linux based application which currently requires access to a shared storage solution for the application to work properly in a cluster.
 Implement a multivalued answer routing policy to route queries to the
correct endpoint.
  Your company is looking to store session information from their backend Amazon EC2 instances and they want to identify the best database which can provide them durability, high availability (HA), scalability and persistence. Since they want to store session information, they want a
database which can provide them microsecond latency.
   Amazon MemoryDB for Redis
Comments: As discussed here (https://aws.amazon.com/blogs/aws/
introducing-amazon-memorydb-for-redis-a-redis-compatible-durable-
in-memory-database-service/#:
   Amazon DocumentDB
 Score: 0.79
Single Choice

  The application has been deployed in Placement Group due to the required
node to node transaction throughputs. The application is latency sensitive.
 As a solutions architect which storage option would you choose to satisfy
the latency requirement?
Amazon S3
Amazon EBS Multi-attached Amazon EFS
Amazon Glacier
Score: 0.79
Single Choice
26)
 Comments: EFS fulfills the requirements of the shared storage file
system which is latency sensitive within a given region.
  A company uses Amazon API Gateway, AWS Lambda, and Amazon RDS for their multi-tier application. During testing, it was observed that the API Gateway requests are taking longer time to complete. They want to
investigate the slow response time of API Gateway calls.
 What is the MOST operationally efficient way for the company to determine
the cause of slow response time from API Gateway?
  Use AWS X-Ray
Comments: AWS X-Ray is the correct choice. X-Ray can be used to
trace and analyze user requests as they travel through your Amazon
API Gateway APIs to the underlying services.
 Use Amazon CloudWatch Use AWS CloudTrail
  Use VPC Flow Logs
 Score: 0.79
Single Choice

 27)
Which solution meets these requirements?
 A customer application runs on a fleet of Amazon EC2 instances. The program read and writes to Amazon DynamoDB. The application just needs last 7 days of data. However, the size of the database keeps increasing. The company needs a solution that minimizes cost and
development effort.
 Configure Amazon DynamoDB stream to invoke AWS
Lambda function when new item is created. Configure AWS
Lambda to delete items in table that are older than 7 days.
 Use AWS CloudFormation to deploy the solution and re-deploy stack
every 7 days.
 Configure application to add an attribute that has a value of current
timestamp plus 7 days to each item created in table. Configure
DynamoDB to use the attribute as TTL attribute.
Comments: Amazon DynamoDB Time to Live (TTL) allows you to
define a per-item timestamp to determine when an item is no longer needed. Shortly after the date and time of the specified timestamp, DynamoDB deletes the item from your table without consuming any write throughput. TTL is provided at no extra cost as a means to reduce stored data volumes by retaining only the items that remain
current for your workloads needs.
  Use Amazon EC2 instance to run a script to delete items that's have
timestamp older than 7 days.
Score: 0.79
Single Choice
28)
  A solutions architect needs to test the connectivity of different protocols, such as ICMP, between an Amazon EC2 instance and an Internet
Gateway, both in the same AWS account.
 Which service can the solutions architect use?

  VPC Flow Logs
Network Access Analyzer
  VPC Reachability Analyzer
 Comments: VPC Reachability Analyzer is used to test connectivity
between 2 points of various supported AWS services.
 VPC IP Address Manager (IPAM)
 Score: 0.79
Single Choice
29)
What should a solutions architect do to meet these requirements? Configure MFA (multi-factor authentication) delete.
Create a new bucket and enable object lock.
Enable Amazon S3 Intelligent-Tiering
Use presigned URL to protect the bucket from deletion.
Score: 0.79
Single Choice
30)
 A company operates in a highly regulated industry. The company stores log files in Amazon S3. Industry policy requires that the company must not
delete or overwritten the log files for at least 6 months.
 Comments: Object Lock can help prevent objects from being deleted
or overwritten for a fixed amount of time or indefinitely.
  Your company is exploring cloud computing and wants to start by building a small, event-driven application that supports Marketing campaigns. The campaign will consist of workflow that involves several discrete steps and target a small customer base. The Marketing group wants the developers to build it quickly and have it ready for customers as soon as possible. The
developers want a visual way to track the individual steps in the campaign.

  Which compute option would be best?
 Run the application on AWS Batch. Organize the steps in the batch
with AWS Step Functions for compute.
 Configure an Amazon EC2 instance and deploy the application to run
there. Write another service to run the application components when
requested on another EC2.
 Use AWS Lambda for compute. Organize the Lambdas to run within
AWS Step Functions.
Comments: AWS Lambda is great for small applications, event-driven
apps, and enables fast development speed. Step Functions are specifically made to visually organize Lambda functions in a
workflow.
  Run the application on AWS Batch. Set up Batch to call the Lambda
for compute.
 Score: 0.79
Multiple Choice
31)
Which gateways are required to achieve this architecture? (Select TWO) Virtual Private Gateway
Transit Gateway
Direct Connect Gateway
NAT Gateway
 A customer wants to place a Amazon EC2 instances with IPv4 in a private subnet on an Amazon VPC. This private subnet must have direct
connectivity to the internet and without traversing a Site-to-Site VPN.
 Comments: NAT Gateway is used for Internet direct connectivity for
private subnets. Find more here: https://docs.aws.amazon.com/vpc/
latest/userguide/VPC_Scenario2.html

 Internet Gateway
Score: 0.79
Multiple Choice
32)
 Comments: Internet Gateway is used for direct Internet connectivity
for public subnets. Find more here: https://docs.aws.amazon.com/
vpc/latest/userguide/VPC_Scenario2.html
  Which of the following are primary impacts on concurrency in AWS
Lambda? (Select TWO)
 RDS Database Engine selection AWS Region Deployment
CloudWatch Monitoring
   Invocation Model
Comments: Asynchronous event sources will retry invocations in the
case of a failed or throttled request. With a synchronous event source
there are no retries built-in.
   Service Limits
Comments: The AWS Lambda service limits the number of
concurrent functions that can be executed at one time.
Score: 0.79
Single Choice
 33)
 A storage specialist of a company created a bucket named 'demobucket2022' for the purpose of storing files for the creation of a proof of concept (POC). After the successful implementation of proof of concept, the team wanted to leverage the bucket for the development work because of the content which was generated during POC. However, they didn't want
to name it 'demobucket2022'.
 What is the solution for the team to proceed with this implementation of the
requirement?

  Use the AWS Management Console and rename the bucket using
rename bucket option.
 Amazon S3 buckets cannot be renamed once created. So, a new
bucket needs to be created and copy the content using cp/sync
command from the AWS CLI.
Comments: As S3 buckets cannot be renamed once created, the
option is to create a new bucket and copy over the content using cp
or sync commands from the CLI.
  Raise a support ticket and work with AWS support to rename the
bucket.
 Use AWS CLI and update the name of the bucket using the update
bucket api.
Score: 0.79
Single Choice
34)
  A multi-national company has services across the globe which has a web application as its customer-facing frontend. One of the features of the app is to allow users to be able to upload huge amounts of files. As part of their architecture, they use a single bucket in the us-east-1 region and all the data from users is uploaded to this bucket. Now, as the demand for applications has grown, more and more users are using the application, which has led to an increase in file uploads. Because the users are across the globe, the upload takes time when the users are geographically far from the us-east-1region, which leads to a degraded user experience. You need to improve the upload experience without making major code level
changes.
 Which is the best service that you could use to achieve this requirement?
 Amazon S3 Transfer Acceleration
 Comments: Transfer Acceleration is best suited for scenarios in
which you want to transfer data to a central location from all over the world or transfer significant amounts of data across continents
regularly. It can also help you use your available bandwidth when

   Amazon Partner Network AWS DataSync
35)
Which of the following is true for Amazon ECS? (Select THREE)
Comments: True;
Amazon ECS supports multi-cloud integration.
Comments: True;
Comments: True;
Amazon ECS manages your cluster resources for all launch types.
  AWS Transfer Family
 Score: 0.79
Multiple Choice
 As the AWS solutions architect, you need to explore whether Amazon ECS is the right choice to build sophisticated application architectures on a
microservices model.
 Amazon ECS has built-in security; all of the images are stored in a
container registry that is only accessible through HTTPS.
 Easier to manage since your entire application need to be on a single
task definition.
 A cluster may contain a mix of tasks hosted on AWS Fargate,
Amazon EC2 instances, or external instances.
 https://docs.aws.amazon.com/AmazonECS/latest/developerguide/
clusters.html
 Amazon ECS provides service discovery for a microservice
architecture.
 https://docs.aws.amazon.com/AmazonECS/latest/developerguide/
common_use_cases.html
uploading to Amazon S3.

 Score: 0.79
Multiple Choice
36)
  A company is working on a new product launch. Both production and test environments are using similar Amazon EC2 instances with attached Amazon EBS volumes. The Billing team will need a solution to monitor the
costs of both environments to identify any unexpected charges.
 What should a solutions architect implement to ensure that the Billing team
can identify the charges for each environment? (Select TWO)
 Budgets
  Cost Allocation Tag
Comments: AWS uses the cost allocation tags to organize your
resource costs on your cost allocation report, to make it easier for you to categorize and track your AWS costs. - https:// docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-
tags.html
 AWS Trusted Advisor
  Cost Explorer
Comments: Although Cost Explorer can be used to monitor the EC2
charges, it will not be a useful tool by itself if the account EC2 instances does not have tags or are allocated in different AWS
accounts.
 Savings Plans
 Score: 0.79
Multiple Choice
37)
 Some companies design their AWS workloads to update their components
regularly, in small, reversible increments.
 Which pillar of the AWS Well-Architected Framework does this design
support?

 Reliability
Security Resilience
Operational Excellence
Score: 0.79
Single Choice
38)
Which of the following is not a valid option under BPA settings?
Block Public Access granted through new ACLs. Block all public access.
39)
 Comments: The Operational Excellence pillar includes the ability to
support development and run workloads effectively,
 Comments: The Operational Excellence pillar includes the ability to
support development and run workloads effectively,
 Comments: The Operational Excellence pillar includes the ability to
support development and run workloads effectively,
  You are a cloud security engineer and have been tasked with ensuring that confidential data is not accessible publicly. To ensure compliance with this mandate, you are interested in turning on Amazon S3 Block Public Access
(BPA) feature.
  Block all access point policies.
 Comments: There is no BPA setting to limit access point policies that
do not result in public access.
   Block public and cross-account access to buckets and objects
through any public bucket or access point policies.
Score: 0.79
Multiple Choice
 
  A solutions architect needs to capture IP traffic logs going in and out of the network interfaces of the Amazon EC2 instances inside of an Amazon VPC. The records need to capture network internet protocol (IP) traffic flow transmitted by a 5-tuple. This information must be publishable in Amazon
CloudWatch Logs.
 What service function would you use to cover all the subnets that belong to
the same VPC?
VPC Reachability Analyzer
VPC Flow Logs
VPC IP Address Manager (IPAM) Network Access Analyzer
Score: 0.79
Single Choice
40)
Which AWS managed service will meet the companies requirements? Amazon Monitron
 Comments: VPC Reachability Analyzer is used to perform
connectivity testing between a source resource and a destination resource in a VPC and is not used to get network traffic logs. Find more here: https://docs.aws.amazon.com/vpc/latest/reachability/what-
is-reachability-analyzer.html
 Comments: VPC Flow Logs is a feature that enables to capture
information about the IP traffic going to and from network interfaces in a VPC. Find more here: https://docs.aws.amazon.com/vpc/latest/
userguide/flow-logs.html
  Your company has an on-premises contact center.Your CTO is looking to
migrate to the cloud to reduce operational workloads and costs.
   Amazon Connect
 Comments: Amazon Connect is an easy-to-use omnichannel cloud
contact center that helps you provide superior customer service at a

   Amazon Chime
41)
 Alexa for business
 Score: 0.79
Multiple Choice
 Your company has a private Amazon VPC in their AWS account that cannot be connected to the internet due to data sensitivity concerns. A solutions architect needs a way to interactively troubleshoot an Amazon
EC2 Instance running in this VPC.
 What should the solutions architect do in order to gain access to the Amazon EC2 instance, without provisioning any type of internet
connectivity? (Select TWO)
 Create Amazon VPC Interface Endpoints for EC2, EC2Messages,
and a VPC Gateway Endpoint for S3.
 Create an SSH key pair, use the SSH key pair to SSH into the AWS
EC2 instance from AWS SSM Session Manager.
 Attach an AWS IAM Instance Profile with the necessary permissions
for AWS SSM Session Manager to the Amazon EC2 instance. Use
AWS SSM Session Manager to access the Amazon EC2 Instance.
Comments: An IAM instance profile with the proper permissions are
needed in order to effectively use AWS SSM Session Manager.
  Create an SSH key pair, use the key pair to SSH into the Amazon
EC2 instance from their workstation.
 Create Amazon VPC Interface Endpoints for SSM, SSMMessages,
and EC2Messages.
Comments: The SSM, SSMMessages, and EC2Messages VPC
Endpoints are needed for SSM Session manager to work without
internet access.
 Score: 0.79
lower cost

  Single Choice
42)
 Your team is deploying a new solution on Amazon ECS. Since your team is new to the cloud, your director wants you to use AWS provided
permissions to ensure reusability and automatic updates.
 Which type of AWS provided permission policy should you use to enable principals to create, manage, and describe Amazon EC2 Auto Scaling
resources?
 Custom policy Multi-factor authentication
   Managed policy
Comments: A managed policy is provided by AWS and can be
attached to multiple principal entities like groups and roles for
reusability. It will also receive updates from AWS automatically.
 Inline policy
 Score: 0.79
Multiple Choice
43)
MySQL
MariaDB PostgreSQL
 Which open source databases are compatible with Amazon Aurora?
(Select TWO)
 Comments: Amazon Aurora (Aurora) is a fully managed relational
database engine that's compatible with MySQL and PostgreSQL. https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/
CHAP_AuroraOverview.html
 Comments: Amazon Aurora (Aurora) is a fully managed relational
database engine that's compatible with MySQL and PostgreSQL.

  https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/
CHAP_AuroraOverview.html
SQL Server Redis
Score: 0.79
Single Choice
44)
  As an AWS solutions architect, you review this AWS CLI command line
used to create a PostgreSQL-compatible Amazon RDS database cluster:
 aws rds create-db-cluster \
 --db-cluster-identifier sample-pg-cluster \
 --engine aurora-postgresql \
 --master-username master \
 --master-user-password secret99 \
 --db-subnet-group-name default \
 --vpc-security-group-ids sg-0b9130572daf3dc16
 You notice that a retention period for the automated backup was not set.
1
 What retention period, in days, will be used by this PostgreSQL-compatible
Amazon RDS database cluster?
 Comments: "If you don't set the backup retention period, the default
backup retention period is one day if you create the DB instance
using the Amazon RDS API or the AWS CLI."
 References:
 Backup retention period
 create-db-cluster examples
 How do I retain the automated snapshots of my Amazon RDS DB
instance for a longer period?
35

 0 7
45)
How can you achieve this requirement? (Select TWO) Move the data to Amazon S3 Glacier.
Turn on versioning in the Amazon S3 bucket.
Enable Amazon S3 default encryption.
Configure MFA (multi-factor authentication) delete.
 Score: 0.79
Multiple Choice
 You are a solutions architect at your company where you save backup data in Amazon S3. An employee inadvertently deleted a backup. You want to ensure that if data is deleted again, you should be able to retrieve the data
and also ensure the data must not be inadvertently deleted in the future.
 Comments: Versioning feature can be used to preserve, retrieve, and
restore every version of every object stored in your buckets.
 Comments: When working with S3 Versioning in Amazon S3 buckets,
you can optionally add another layer of security by configuring a bucket to enable MFA (multi-factor authentication) delete. When you do this, the bucket owner must include two forms of authentication in any request to delete a version or change the versioning state of the
bucket.
Use presigned URL to protect the bucket from deletion.
Score: 0.79
Multiple Choice
46)
You have created an Amazon RDS instance.
   How can you retrieve an endpoint of the newly created instance? (Select
TWO)

   AWS CLI
Comments: Once your database instance is available, you can
retrieve its endpoint via the database instance description in the AWS Management Console, DescribeDBInstances API or describe-db-
instances command.
 Amazon RDS Parameter groups.
Log into Amazon RDS instance.
    AWS Management Console
Comments: Once your database instance is available, you can
retrieve its endpoint via the database instance description in the AWS Management Console, DescribeDBInstances API or describe-db-
instances command.
Score: 0.79
Multiple Choice
 47)
You must create a AWS Lambda function to retrieve the database
instance end point.
 A business wants to run many scheduled and event-driven workloads. The solution can take an average runtime of 30 minutes. The business wants AWS to manage the instances provisioned for these large processing
workloads.
 Which of the following services are suitable for this use case? (Select
TWO)
Amazon EventBridge AWS Fargate
AWS Lambda
 Comments: https://docs.aws.amazon.com/prescriptive-guidance/
latest/patterns/run-event-driven-and-scheduled-workloads-at-scale-
with-aws-fargate.html

 Amazon EKS Distro AWS EC2
Score: 0.40
Multiple Choice
48)
  Your CEO decided to migrate your data center to AWS. You are engaged as the AWS migration specialist to create a business case and decide to
use AWS Migration Evaluator.
 Which of the following are included in the business case report? (Select
THREE)
 An executive summary of the savings across a combination of
scenarios applied to different workloads.
Comments: Migration Evaluator Business Case (https://
aws.amazon.com/migration-evaluator/features/)
  Recommend AWS services required for your target architecture.
Provide configuration data about your on-premises servers.
 Recommendation for the customer on next steps for a successful
migration.
Comments: Migration Evaluator Business Case (https://
aws.amazon.com/migration-evaluator/features/)
   Recommendation on how to automatically converting your source
servers from physical, virtual, or cloud infrastructure to run natively on
AWS
 A breakdown of what went into the on-premises costs.
 Score: 0.53
Single Choice
49)
Your company is looking to migrate its data-heavy, flagship video

  processing application to AWS.The application runs across multiple Linux servers on-premises. The application requires a high performance file
system, as the instances need to share the data at a very fast rate.
Which recommendation best meets the requirements?
 Host your application on Amazon S3. Use Amazon EFS for file
system storage.
 Host your application on multiple Amazon EC2 Linux instances. Use
Amazon FSx for Windows File Server for file system storage.
 Host your application on multiple Amazon EC2 Linux instances. Use
Amazon FSx for Lustre for file system storage.
Comments: The business requires a Linux environment. FSx for
Lustre will provide the high-performance required for video
processing workloads
  Host your application on Amazon S3 and utilize S3 for file system
storage.
Score: 0.79
Multiple Choice
50)
  Your company uses an Amazon EC2 instance in a public subnet to host a web application. The Amazon EC2 instance uses a default security group. The network ACL is configured to block all traffic to the instance. You must allow incoming traffic on port 443 to access the application from any
source.
 Which combination of steps will accomplish this requirement? (Select
TWO)
 In the security group, add a rule to allow TCP connections on port
443 from the source 0.0.0.0/0
Comments: Security groups are stateful, so if you allow traffic in, then
the security group automatically allows that traffic back out. So you
only need a rule for incoming traffic from port 443.
 
  In the security group, add a rule to allow TCP connections on port
443 to destination 0.0.0.0/0
 In the network ACL, add a rule to allow outbound TCP traffic on port
1024 - 65535 to destination 0.0.0.0/0
 In the network ACL, add a rule to allow inbound TCP traffic on port
443 from source 0.0.0.0/0 and outbound traffic on port 1024-65535 to
the destination 0.0.0.0/0
Comments: Network ACLs are stateless, so you need to add rules for
both inbound and outbound traffic. This configuration for your network ACLS should allow both inbound and outbound traffic to the port that the application is listed on but also to allow outbound traffic from the
ephemeral ports.
  In the network ACL add rules to allow both inbound and outbound
TCP connection on port 443 from source 0.0.0.0/0 and destination
0.0.0.0/0
Score: 0.79
 BACK TO RESULTS
Solutions Architect Knowledge Badge Assessment
ID: E-VX2O25
1 / 3 lessons completed
How would you rate this course?
 
 5
Solutions Architect Knowledge Badge Assessment
Test
Learning Plan and Badge Feedback Survey
Report Assessment Errors & Missing Badge Lesson
Course Description
  This assessment validates your comprehension of the Solutions Architect Knowledge Badge Readiness Path. The assessment questions are based on the courses in this learning path. Take all of the courses and then verify your knowledge. Already have some knowledge on Architecting? Go directly to the assessment, test your knowledge. The score report will identify your areas of strength and direct you to the courses where you can
improve any knowledge gaps.
 You can earn the Architecting Knowledge badge with a score of 80% or
better. Badges are issued by Credly within 5-7 business days.
 Don’t worry if you didn’t achieve 80% or better. You can re-take the assessment after a 24-hour wait period. Use your score report to identify the courses where you can improve any knowledge gaps, then take the assessment again. Use this assessment as a method to continue building your knowledge. Assessment questions are randomized on each attempt
which allows you to get more questions.

  Learning Plan
 Solutions Architect - Knowledge Badge Readiness Path
  2% progress
 4h 40m / 58h 48m

   Support | Legal | Privacy | Cookie Policy ©2023, Amazon Web
Services, Inc. or its affiliates. All rights reserved.
 