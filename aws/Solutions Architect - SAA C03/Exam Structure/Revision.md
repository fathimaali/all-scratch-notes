## IAM : [[AWS IAM]]  

			Identity and Access Management 
					Components: 
						Users
						Groups
						Policies
						Roles
						least privilige - only give what is needed
						IAM MFA 
							virtual MFA - apps
							physical MFA - U2F key 
							hardware MFA 
						Password Policies							
						setup Access Keys for AWS CLI and SDK
						Security Tools : 
							IAM Credentials Report
							IAM Access Advisor
							IAM Access Analyzer
## EC2 : [[Solutions Architect - SAA C03/Compute/Amazon EC2/Amazon EC2|Amazon EC2]] 
			EC2 - IaaS
			User Data - bootstrap
			Instance Types : 
					General Purpose
					Compute Optimized
					Memory Optimized
					Storage Optimized
					Accelerated Computing 
					Instance Features
					Measuring Instance Performance 
			Instance Types Purchasing Options : 
					On Demand Instance : pay by use
							highest cost, but no upfront payment
							short and uniterrupted workloads 
							no long term commitment 
					Reserved Instance : 1 -3 yrs
							72% discount
							may reserve based on attributes : instance type, region, tenancy, OS
							payment options : 
								all upfront : cheapest
								partial upfront
								no upfront
							types:
								reserved
								convertible reserved instance :66% discount
					Savings Plan : commit to an amount of usage
							72% discount
								commit to certain type or amount of usage 
								if used beyond plan, it is billed as On Demand price		
					Spot : 
							90% discount
							batch jobs
							jobs that can be interrupted
							dont run critical jobs here
							short bursts of workload
					Dedicated Host : entire physical server, decide instance placement etc
							types : 
									on demand
									reserved
							Bring your license
							most expensive option							
					Dedicated Instance :
							 instances run on hardware dedicated to you
							 may share hardware with other instances in the same account
							 no control over instance placement etc
					Capacity Reservations : reserve capacity in an AZ for a duration
							no time commitment
							no discount
							charged based on On demand pricing
							short uninterrupted workloads		
			Security Groups
			Classic ports
					22 - SSH
					21 - FTP
					22 - SFTP
					80 - HTTP
					443 - HTTPS
					2049 - NFS
					3389 - RDP
					PostgresSQL : 5432
					MySQL : 3306
					Oracle RDS : 1521
					MSSQL Server : 1433
					MariaDB : 3306
					Aurora : 5432 - postgres
					Aurora : 3306 - MySQL
			SSH 
					using CloudShell
					EC2 Instance Connect
					SSH putty
			Spot Instances
					Spot Instance Requests: 
							define your max spot price
							if instance price < max spot price -- keep that instance
							if instance price > max price -- drop that instance - stop/terminate
								within grace period of 2 mins
							Types : 
									Persistent : valid from to valid until
									One time
							can cancel spot requests that are active, disabled or open.
							when you want to remove the spot request - do this first and then 
								manually need to terminate the instances
			Spot Fleet : 
					a fleet of spot instances or on demand instances
					strategies to launch a pool of instances : 
							lowestPrice : cost optimization, short workload
							diversified : high availability, long workload
							capacityOptimized : best capacity 
							priceCapacityOptimized : lowest price, but best capacity
			Placement Groups
					control over how EC2 instances would be placed inside AWS infrastructure
					Strategies : 
							cluster - cluster into a low latency 
								same rack 
								same AZ
								10GBps netwrok - high speed
								low latency 
								low availability because its in single AZ
								extreme low latency + extremely high bandwidth 
							spread - spread instances across hardware
								max 7 instances
								critical apps
								reduced risk when compared to cluster
								multiple AZ - high availability 
							partition - spreads across many partitions within an AZ
								100s of EC2 instances
								each partition belongs in a single AZ
								upto 7 partitions per AZ
								multi AZ - same region
			Elastic Network Interface (ENI): 
					component of AWS that represents a logical network card
					can have 1 primary IPv4
					1 secondary IPv4
					can have one or more Security Group
					can create ENI independently and attach them later to EC2
					bound to specifiic AZ
			EC2 Hibernate
					in memory state is preserved
						instance boot is faster
						RAM is written to the EBS volume
						root EBS volume must be encrypted
					use case 
						fast boot up time 
						long running process that can resume from where it was left off
						saving the RAM state
			Amazon Machine Image (AMI):
					customization of an ec2 instance and make an image out of it
					build ami
					use that built ami to launch EC2 instances - boot time reduced
					can be copied across regions
					there is a marketplae where you can buy and sell AMI
					there are also public AMI - provided by aws
			EC2 Instance Store
					high performance - better I/O
					hardware disk attached to an EC2
					EC2 when terminated - Instance Store is lost
					only suitable for short term storage
					risk of data loss when EC2 fails
					
## Cost Management 
			AWS Budget
## Storage
			EBS
						elastic block store
						allows instance to persist data even after the instance is terminated
						can only be mounted to one instance at a time
						specific AZ
						more like network USB disk 
						free tier 30GB of free EBS storage or Gen purpose SSD month
						need to provision capacity in advance - size in GB or IOPS
						'delete on termination' means delete when EC2 instance is terminated
						Snapshots : 
									backup at any point in time
									can copy between AZ and regions
									Archive Tier : 
											75% cheaper
											24 to 72 hours restoring from archive
									Recycle Bin : 
											can set the retention policy 
									Fast snapshot restore : 
											force full initialization of snapshot- no latency first use
						Volume Types : 
								gp2/gp3 : SSD
										general purpose ssd that balance price and performance 
										varitey of workloads
										can be used an boot volumes
										gp3:
												Size: 1GiB to 16TiB
												throughput: 125 MiB/s to 1000 MiB/s 
												IOPS : baseline 3000 IOPS to 16000 IOPS
												can independently increase or decrease this
										gp2: ld version
												size: upto 5334 GB
												throughput : 
												IOPS : bursts of 3000 IOPS, max is 16000 IOPS
												size of volume and IOPS are linked, we max at 5334 GB 
													 @ max IOPS
								io1/io2 : SSD
										highest performance ssd
										mission critical low latency
										high throughput workloads
										can be used an boot volumes
										when apps need more than 16000 IOPS
										great for databases (consistent)
										supports EBS multi attach
										io1/io2: 
											max IOPS : 64000 for nitro EC2, 32000 for others
											size: 4GiB - 16TiB
											io2 is more durable for same price as io1
										io2 Block Express:
											sub milli second latency 
											max PIOPS: 256,000
								st1 : HDD
										low cost HDD 
										throughput intensive workloads
										can NOT be used an boot volumes
								sc1 : HDD
										lowest cost HDD for less frequently access workloads
										can NOT be used an boot volumes
						EBS Multi Attach 
								attach same EBS volume to multiple Ec2 in the same AZ
								each instance has read and write access to the EBS volume attached
								higher applicaton availability
								each volume can be attached to upto 16 instances at a time
								applications must manage concurrent Read and Writes
						EBS Encryption
								data at rest and in transit to the volume is encrypted if enabled
								all snapshots are encrypted
								all volumes created from the snapshot are encrypted
								encryption decryption is transparent
								keys from KMS are used AES 256
			EFS:
						managed NFS used by many EC2 at once
						multi AZ
						highly available, scalable, expensive
						uses NFSv4.1 protocol
						can use security group to control access to EFS
						compatible with Linux based AMI (not windows)
						encryption at rest
						POSIX file system - standard API
						no capacity planning
						would have security group attached to EFS, that would let inbound 
						traffic from the security group of the EC2 instance
						scale :
								1000s of concurrent NFS clients, 10GB/s + throughput
								grow upto petabyte 
						Modes : --> set at EFS creation time
								performance mode :
										general purpose:  default - latency sensitive use cases
										MAX I/O: higher latency, throughput, highly parallel
								throughput mode : 
										bursting : higher throughput
										provisioned : set throughput regardless of storage
										elastic : auto scale throughput up or down -for unpredictable
						Storage Classes : 
								storage tier : works with lifecycle policies
										standard : frequently accessed files
										infrequent access EFS IA : cost to retrieve
												infrequently accessed files
												lower price to store
								availability and durability: 
										standard : multi AZ
										one zone : one AZ
												if couple with IA, one zone IA - 90% cost savings
## Elastic Load Balancing (ELB)
			Scalability : 
					scale up 
					scale down
					scale in 
					scale out					
			Availability :
			single point of access
			health checks : 
					use port and route to check health, response != 200, then unhealthy
			balance load of a set of EC2 instances
			Types: 
					Application Load Balancer ALB : 
							Layer 7
							HTTP, HTTPS, WebSocket
							support Routing Tables: can send to diff target group based on rules
									based on path
									based on hostnae
									based on querystring
					Network Load Balancer NLB : 
							Layer 4
							TCP, TLS, UDP
							really high performance
							ONLY ONE static IP for an AZ
							not free tier
							health checks support : TCP, HTTP, HTTPS
					Gateway Load Balancer GwLB :
							inspect network traffic before it reaches the application
							Target group would be : 3rd party security virtual appliances
							Layer 3
							IP
							GENEVE protocl on port 6081
			Security : 
					Security Group can be attached to ELB.
			Target Group : 
					group of resources 
					could be a group of any of the foll:
							EC2 instances
							ECS tasks
							lambda functions
							IP addresses
			We get a fixed hostname for an ALB
			Header of client IP address : 
					X Forwarded For : true IP of client is in header
					X Forwarded Port
					X Forwaded Proto
			Sticky Sessions : 
					session affinity
					make sure a client is redirected to the same instance that they previously spoke to
					a Cookie is used for enabling the stickiness
							Cookie Types :
									application-based cookie: 
											custom cookie: 
													generated by target
													entirely custom
													each target group has a diff cookie 
													dont use : 
															AWSALB, AWSALBAPP, AWSALBTG
											application cookie:
													generated by ELB
													cookie name used is AWSALBAPP
									duration based cookie : 
											generated by ELB
											cookie name is AWSALB, AWSELB
			Cross-Zone Load Balancing: 
					load balancing between multiple AZs.
					eg. requests from a single client sending it to two ELB in two AZs,
						 would be load balanced if enabled. 
					Types: 
							ALB: 
									enabled by default
									can be disabled at TG level
									no charges for inter AZ data
							NLB: 
									disabled by default
									charged $ for inter AZ data if you enable
							CLB:
									disabled by default
									no charge for inter AZ data
			SSL/TLS certificates :
					SSL - secure sockets layer
					TLS - transport layer security 
				   ACM - Amazon Certificate Manager
							helps you generate, manage, provision SSL, 
							   TLS certs for use with your apps
							either you can use ACM to provision and manage a 
							   cert (amazon will then use a Certificate Authority CA) or you can
							   import third party issued cert into ACM
					SNI - server name indication
							helps you use multiple SSL/TLS certificate hosted on the same 
								server, the problem this solves is that earlier one server could 
								only have one SSL/TLS cert and that made hosting diff apps on the 
								same server pretty impossible.
							SNI - expects a server name sent on the request, that it can then 
								use to resolve the app and provide the SSL/TLS cert correctly
							SNI works only with NLB, ALB
					ELB - Connection Draining
							aka de-registratoin delay 
							time to complete 'in flight' requests while the instance is in the 
								process of being marked unhealthy or is being de-registered
							stop sending new requests while connection draining is active
							ranges between 1 to 3600 seconds
## Auto Scaling Group (ASG)
		scale out or scale in our EC2 instances based on demand 
		minimum, maximum, desired capacity - number of EC2 instances to work with 
		auto register new EC2 instances into an ELB
		health checks - re-creates new EC2 instances when one becomes unhealthy 
		Free service - only pay for what is created
		When we create an ASG we need the following : 
				Min size, Max size, desired capacity
				Launch Template : 
						info about what kind of instances need to be created when scaling out
								AMI + instance type 
								OS 
								EC2 user data
								EBS volumes
								security groups 
								SSH key pair 
								IAM roles
								network + subnet info 
								ELB info, target group
				Scaling Policies : 
						scale in policies 
						scale out policies 
						both can be setup usiing cloudwatch alarms -> using metrics eg. 
							CPU usage etc
						Types : 
								target track scaling : 
										can make it work by having it maintain a target 
											eg. keep CPU utilization at 40% 
								simple/step scaling :
										works based on metrics from cloudwatch, scale in or out
								scheduled actions : 
										we know the scale in and out in advance so can schedule it
								predictive scaling : 
										ML powered - gives insights on how to scale 
						good metrics for scaling : 
								CPU utlization 
								RequestCountPerTarget
								Average network in/out
						Scaling Cooldown : 
								time taken for the ASG to cool down after a scaling activity
								during this time no new instances would be launched or terminated
								metrics are stabilizing 
								default time 300 seconds
				Health Check rules : 
						either ASG can read from the EC2 instances
						or can rely on ELB to gie me health check info
## Amazon RDS
		RDS : relational database service
		managed service
		create relational DBs on AWS that would then be manageed by AWS
				Postgres, MySQL, MariaDB, Oracle, Microsoft SQL, Aurora
		cannot SSH into an RDS instance
		storage is backed by EBS volumes (gp2/io1)
		templates for creation: 
				prod
				test
				free tier
		storage autoscaling : 
				helps increase storage 
				maximum storage threshold can be set 
				great for unpredictable workload
				auto modify storage when : 
						free space is < 10% of total space
						low storage lasts 5 mins 
						6 hours have passed since last modification
		Read replica : 
				read scalability 
				upto 15 read replica
				async replicaion -- eventually consistent
				within AZ, cross AZ or cross region
				replicas can be promoted to a DB
				use case: 
						reporting data
						analytics of data
						use cases that only need SELECT
				network cost : 
						read replica same region (cross or one AZ) -- free
						read replica cross region - $$
		Multi AZ : 
				disaster recovery 
				sync replication 
				one DNS name 
				auto failover to the DB instance standby in the other AZ
					in case of disaster.
				standby is just for standby - no read or write can be done to it
				convert single AZ to multi AZ is just one setting change away 
		RDS Custom : 
				for two DB types : Oracle, Microsoft SQL Server
				Custom gives access to underlying DB, OS so we can 
						configure settings 
						install patches 
						enable natve features 
						access underlying EC2 instance 
						SSH access 
						SSM access 
		BackUp : 
				automated backup
						daily full backup of DB
						transaction logs are backed up every 5 mins 
						PITR -> even as of 5 mins ago
						auto backup retention - 1-35 days
						set retention to 0 to disable auto backup
				manual backup
						manually triggered ; adhoc
						retention is based on choice, for however long you need
				when you wanna stop an RDS DB, instead of stopping it and still paying for 
					underlying storage cost, its more cost effective to backup and then 
					restore backup when needed.
		Restore: 
				restoring a backup creates a new DB
				can also be restored from S3 - on premise DB mySQL support		
## Amazon Aurora
		proprietary tech from AWS
		compatible with postgres or mySQL
		5x better than MySQL, 3x better than postgres
		upto 15 read replicas - auto scaling based on read load
		one master to take all the write, and upto 15 read replicas
				failover one read replica as master
				failover is instantaneus in Aurora - high availability - < 30 seconds
		multi-master : 
				can be enabled when we want immediate failover for writer.
				every node does read and write 
		storage - grows automatically : upto 128GB, increment of 10GB
		Endpoints:
				writer endpoint - pointed to master, during failover, this is pointed
					elsewhere
				reader endpoint - connection load balancing for reads - auto scaled
				custom endpoint - use different types of scaled in or out read replica for 
					different purposes
		also has self healing - auto detect issue and rectify them
		read scaling &	high availability : 
				6 copies of data across 3 AZ
						4/6 copies are for writes
						3/6 copies are for reads
				storage is striped across 100s of volumes
		backup and recovery with PITR - Backtrack 
		Authentication - can use password or IAM auth
		Global Tables / Global Database : 
				single DB auto replicated in mutliple AWS region. 
				cross region replication < 1 sec replication 
				1 primary region
				upto 5 secondary regions 
				replication lag is < 1 second
				low latency access to data from anywhere 
				enables writes
				upto 16 read replicas per region
		Serverless : 
				automated DB instantiation 
				no cppacity planning 
				pay per second
		Machine Learning : 
				supports ML integrations 
				sagemaker - any ML model
				comprehend - analysis
				use case : 
						fraud detection
						ads target
						sentiment analysis
						product recommendations
		BackUps : 
				automated: 
						cannot be disabled
						retention -> 1-35 days 
						PITR in that timeframe
				manual DB snapshots : 
						manually triggered ; adhoc
						retention - however long we need
		Restore: 
				restoring a backup creates a new DB
				can also be restored from S3 - on premise DB mySQL support
		Database Cloning : 
				create new Aurora DB cluster from an existing one
				faster than snapshot and restore
				uses Copy-On-Write protocol
				very fast and cost effective	
## Security for RDS and Aurora : 
		Security: 
				at-rest encryption: 
						encryoted on the volumes
						master and read replica - encryption enabled at launch time
						if master not encrypted, read replicas canNOT be encrypted
						to encrypt an unencrypted DB, take snapshot and restore as encrypted
				in-flight encryption: 
						TLS root cert - must be used by default - client side
		IAM authentication: 
				IAM roles to connect to DB 
		Security Groups : 
				allow/block ports
		SSH Access : 
				not available except for RDS Custom
		Audit Logs : 
				can be enabled to go to CloudWatch Logs for long retention
## RDS PROXY : 
				fully managed databse proxy for RDS
				allows to pool and share connection to RDS DB
				reduces load on RDS DB
				improves efficiency 
				reduces stress on RDS resources 
				serverless
				autoscaling 
				high availability 
				reduces failover time by 66%
				supports RDS
				enforce IAM authentication - store credentials in AWS Secret Manager
				NEVER publicly accessible - only from VPC
## Elasticache : 
		managed Redis or Memcached
		reduces load off DBs for a read intensive workload
		applications become stateless
		AWS cares of OS maintenance, patching, optimization, setup, config, 
			monitoring, failure recovery, backup
		involves heavy application code changes
		architecture fundamentals : 
				cache hit : 
						when the cache seems to have the info needed just pass to who is trying
							to read
				cache miss : 
						when the cache does not seem to have the info needed, just query DB and 
							cache that for future use
				cache invalidation : 
						to renew
		stateless : 
				session data stored in cache 
		REDIS : 
				multi AZ with auto failover
				persistent
				read replicas for read scaling and HA
				high durability with AOF (Append Ony File)
						AOF log file - contains every write operation
						can be replayed to create exact DB state even if there is power outage
				backup and restore available.
				supports sets and sorted sets
		MEMCACHED : 
				sharding of data - multi node - partioning 
				simpler design - higher performance
				no HA
				non persisent
				no backup and restore
				multi threaded architecture
		Security : 
				IAM authentication for Redis
				IAM policies on Elasticache are used for AWS API level security
		Redis AUTH
				set a password/token when creating a redis cluster 
				extra level of security on top of security group
				SSL in-flight encryption
		Patterns for Elasticache: 
				LazyLoading : cache hit and cache miss concept
				WriteThrough: instant cache, no stale data
				SessionStore: store temp data in cache
		Use case : 
				gaming leaderboard 
				redis sorted set : uniqueness and element ordering
## DNS 
		verbose hostname -> IPS address
		Domain Registrar : Amazon, Route 53, GoDaddy
				manages the reservation and registration of domain names
		Domain Registry : 
		Domain Registrant : 
		Terminologies : 
				DNS records :
						A : 
								address record IPv4
								map domain name to IPv4 address
						AAAA : 
								IPv6 address
								map domain name to IPv6 address
						CNAME : 
								canonical name 
								create alias or a canonical name for a domain. 
								map domain name to domain name.
						MX :
								mail exchange
						TXT :
								addition of arbitrary text into a domain name
								used for description of domain 
						NS :
								name server
								indicate which server is responsible for providing DNS 
									info
						SRV : service
						PTR : ponter record, reverse DNS lookup
				zone file: 
						contains DNS records
				name server : 
						resolves DNS queries
				Top level domain TLD :
						.com, .us, .in
				second level domain SLD :
						google.com, amazon.in
## Route 53
		highly scalable
		highly available
		authoratitive DNS
				means customer can update DNS records
		also is a Domain Registrar
		health check of resources 