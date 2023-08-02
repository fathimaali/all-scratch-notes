DMS – Database Migration Service  
		• Quickly and securely migrate databases to AWS, resilient, self healing  
		• The source database remains available during the migration  
		• Supports:  
				• Homogeneous migrations: ex Oracle to Oracle  
				• Heterogeneous migrations: ex Microsoft SQL Server to Aurora  
		• Continuous Data Replication using CDC - i.e. Change Data Capture (iseries analogy : journaling)
		• You must create an EC2 instance to perform the replication tasks
			
	![[Pasted image 20230522104547.png]]

## DMS Sources and Targets  

SOURCES:  
		• On-Premises and EC2 instances databases: Oracle, MS SQL Server,MySQL, MariaDB, PostgreSQL, MongoDB, SAP, DB2
		• Azure: Azure SQL Database  
		• Amazon RDS: all including Aurora  
		• Amazon S3  
		• DocumentDB  
TARGETS:  
		• On-Premises and EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, SAP  
		• Amazon RDS  
		• Redshift, DynamoDB, S3  
		• OpenSearch Service  
		• Kinesis Data Streams  
		• Apache Kafka  
		• DocumentDB & Amazon Neptune  
		• Redis & Babelfish


## AWS Schema Conversion Tool (SCT)
:
		• Convert your Database’s Schema from one engine to another  
		• Example OLTP: (SQL Server or Oracle) to MySQL, PostgreSQL, Aurora  
		• Example OLAP: (Teradata or Oracle) to Amazon Redshift  
		• Prefer compute-intensive instances to optimize data conversions  
		• You do not need to use SCT if you are migrating the same DB engine  
				• Ex: On-Premise PostgreSQL => RDS PostgreSQL  
				• The DB engine is still PostgreSQL (RDS is the platform)
		![[Pasted image 20230522105404.png]]

## Continuous Replication - DMS
		![[Pasted image 20230522105723.png]]

## AWS DMS - Multi AZ Deployment 

When Multi-AZ Enabled, DMS provisions and maintains a synchronously stand replica in a different AZ.

Advantages:  
		• Provides Data Redundancy  
		• Eliminates I/O freezes  
		• Minimizes latency spikes

![[Pasted image 20230522105854.png]]

Hands On : DMS AWS service 
create replication instance
select instance class : dms.t2.micro
select other parameters, eg. replication engine version, multi az or not, allocated storage etc

once we have an ec2 replication instance

we create a database migration task 

task identifier (name)
select replication instance
select source endpoint - need to create seperately
select target endpoint - need to create seperately
select CDC settings 
create






	