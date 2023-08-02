flexible application that **cannot** be interrupted, no long term reservation or upfront payment needed --> On-Demand
flexible application that CAN be interrupted and most cost effective --> Spot Instance

identify all EC2 instances utilization without any manual configurations --> 
	[[Cloud Practitioner - CLF C01/3 Technology/Technology Support/AWS Trusted Advisor]] -- lets you see EC2 utilization along with provide guidance for optimization
	[[Cloud Practitioner - CLF C01/4 Billing and Pricing/Billing Support & Tools/AWS Cost Explorer]] -- lets you see EC2 utilization along with forecast cost

Components of a [[Hybrid - Site to Site VPN, DX.]]
	Customer Gateway 
	Virtual Private Gateway 

List of Gateways and where they are used?
	Customer Gateway - In Site to Site VPN - customer side has this
	Virtual Private Gateway - In Site to Site VPN - AWS side has this 
	Internet Gateway - Used to connect multiple EC2 instances 
	NAT Gateway - Used by Private subnet to connect to the internet 
	Storage Gateway - used by on-premises applications to access virtually unlimited cloud storage 
	Transit Gateway - used to connect multiple VPCs  and or on-premise networks together
	[[Amazon API Gateway]] - makes external REST API calls look like AWS'
	
Go through this once : https://aws.amazon.com/premiumsupport/plans/

CloudFormation cannot move data into another region. 
We need to manually create the resources in another region and move application from one region into another. 

[[AWS CodeDeploy]] vs [[AWS CodePipeline]] 

AWS CodeDeploy is a service that automates code deployments to any instance, including Amazon EC2 instances and instances running on-premises. AWS CodeDeploy makes it easier for you to rapidly release new features, helps you avoid downtime during deployment, and handles the complexity of updating your applications. You can use AWS CodeDeploy to automate deployments, eliminating the need for error-prone manual operations, and the service scales with your infrastructure so you can easily deploy to one instance or thousands.

AWS CodePipeline is a continuous delivery service that enables you to model, visualize, and automate the steps required to release your software. With AWS CodePipeline, you model the full release process for building your code, deploying to pre-production environments, testing your application and releasing it to production.

[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/EBS - Elastic Block Storage/EC2 Instance Store]] -> caching 

[[Amazon Route 53]] - routing policy 
active passive -> Failover routing - based on health checks

[[S3 Storage Classes]] -> 
least availability -> One zone IA

[[RDS Read Replicas, Multi AZ]] 
read replica - scalability
multi AZ - availabilty 

[[Cloud Practitioner - CLF C01/2 Security and Compliance/Amazon GuardDuty]] --> threat detection

[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/EFS - Elastic File System/Amazon Elastic File System (Amazon EFS)]] -- EC2 instances can access files on an EFS file system across many Availability Zones, Regions and VPCs

[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Compute/EC2 - Elastic Compute Cloud/AMI - Amazon Machine Image]] -- You must use an AMI from the same region as that of the EC2 instance. The region of the AMI has no bearing on the performance of the EC2 instance
AMI provides the information required to launch an instance. You must specify an AMI when you launch an instance. You can launch multiple instances from a single AMI when you need multiple instances with the same configuration.

[[Cloud Practitioner - CLF C01/Shared Responsibility Model/Summary.]] 
OS patching and updates - customer responsibility

highly available 
[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/EFS - Elastic File System/Amazon Elastic File System (Amazon EFS)]]
[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Database/Amazon DynamoDB/Amazon DynamoDB]]

[[AWS Support Plans]]
general guidance - Developer
contextual guidance use-cases - Business
consultative guidance for your application - enterprise

[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/EFS - Elastic File System/Amazon Elastic File System (Amazon EFS)]]
Correct option: **Storing files in an accessible location to satisfy audit requirements** - The Standard–IA storage class reduces storage costs for files that are not accessed every day. It does this without sacrificing the high availability, high durability, elasticity, and POSIX file system access that Amazon EFS provides.
AWS recommends Standard-IA storage if you need your full dataset to be readily accessible and want to automatically save on storage costs for files that are less frequently accessed. Examples include keeping files accessible to satisfy audit requirements, performing historical analysis, or performing backup and recovery. Standard-IA storage is compatible with all Amazon EFS features, and is available in all AWS Regions where Amazon EFS is available.

[[Cloud Practitioner - CLF C01/3 Technology/Technology Support/AWS Personal Health Dashboard]]- 
AWS Health - Your Account Health Dashboard provides alerts and remediation guidance when AWS is experiencing events that may impact you.

[[Cloud Practitioner - CLF C01/4 Billing and Pricing/AWS Organizations/AWS Organizations]] 
Create separate AWS accounts for development and production environments to receive separate invoices"
Every AWS account provides its own invoice end of the month. You can get separate invoices for development and production environments by setting up separate AWS accounts for each environment.
You cannot create separate invoices based on tags.

[[Penetration Testing.]] vs [[Cloud Practitioner - CLF C01/2 Security and Compliance/Amazon Inspector]]
penetration testing client can carry out security assessments on their own without approvals
inspector is an automated security testing service

[[Security Group]] vs NACL 
A Security Group is stateful, that is, it automatically allows the return traffic
A NACL contains a numbered list of rules and evaluates these rules in the increasing order while deciding whether to allow the traffic

[[AWS Shield]] paid service for all support plans

[[Cloud Practitioner - CLF C01/4 Billing and Pricing/Monitoring/AWS Budget]] --> 3 types -> Usage, Cost, Reservation

[[Amazon CloudWatch]] -> logs can be centralized

[[AWS Lambda]] is billed like pay per call per duration 

Reserved Instance -> upto 72% cost savings

Regional Services 
Lamba
Rekognition 

Global Services 
IAM

[[IAM Policies]] mandatory elements of the JSON -> effect action

[[Amazon Elastic Block Storage (EBS)]] - 
Amazon EBS Snapshots are stored incrementally, which means you are billed only for the changed blocks stored - Amazon EBS Snapshots are a point in time copy of your block data. For the first snapshot of a volume, Amazon EBS saves a full copy of your data to Amazon S3. EBS Snapshots are stored incrementally, which means you are billed only for the changed blocks stored.

[[EFS IA - EFS Infrequent Access]] 
You will pay a fee each time you read from or write data stored on the EFS - Infrequent Access storage class - The Infrequent Access storage class is cost-optimized for files accessed less frequently. Data stored on the Infrequent Access storage class costs less than Standard and you will pay a fee each time you read from or write to a file.

DEFAULT DATA ENCRYPTION 
[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/S3 - Simple Storage Services/Amazon S3 Glacier]] 
[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/AWS Storage Gateway]]
[[Cloud Practitioner - CLF C01/3 Technology/Monitoring/AWS CloudTrail]] logs

Block level storage 
[[Amazon Elastic Block Storage (EBS)]]
[[Cloud Practitioner - CLF C01/3 Technology/Core AWS services/Storage/EBS - Elastic Block Storage/EC2 Instance Store]]

Amazon CloudWatch billing metric data is stored in which AWS Region?
US-East-1 N Virgina 

[[AWS Migration Evaluator]]

Migration Evaluator (Formerly TSO Logic) is a complimentary service to create data-driven business cases for AWS Cloud planning and migration.

Migration Evaluator quickly provides a business case to make sound AWS planning and migration decisions. With Migration Evaluator, your organization can build a data-driven business case for AWS, gets access to AWS expertise, visibility into the costs associated with multiple migration strategies, and insights on how reusing existing software licensing reduces costs further.

[[AWS ECS - Elastic Container Service]] 
A startup runs its proprietary application on docker containers. As a Cloud Practitioner, which AWS service would you recommend so that the startup can run containers and still have access to the underlying servers?

[[Cloud Practitioner - CLF C01/3 Technology/Containers/AWS Fargate]]
run container but no access to EC2
