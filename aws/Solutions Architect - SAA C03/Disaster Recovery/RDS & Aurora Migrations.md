[[Solutions Architect - SAA C03/Database/Amazon RDS|Amazon RDS]] and [[Solutions Architect - SAA C03/Database/Amazon Aurora/Amazon Aurora|Amazon Aurora]]

## MySQL Migrations

**RDS MySQL to Aurora MySQL**  
		• Option 1: DB Snapshots from RDS MySQL restored as MySQL Aurora DB, potential downtime  
			![[Pasted image 20230522110717.png]] 
		• Option 2: Create an Aurora Read Replica from your RDS MySQL, and when the replication lag is 0, promote it as its own DB cluster (can take time and cost $)  
			![[Pasted image 20230522110738.png]]
**• External MySQL to Aurora MySQL**  
		• Option 1:  
				• Use Percona XtraBackup to create a file backup in Amazon S3  
				• Create an Aurora MySQL DB from Amazon S3  
					![[Pasted image 20230522110751.png]]
		• Option 2:  
				• Create an Aurora MySQL DB  
				• Use the mysqldump utility to migrate MySQL into Aurora (slower than S3 method)  
				![[Pasted image 20230522110805.png]]
**• Use DMS if both databases are up and running**

## PostgreSQL Migration

**RDS PostgreSQL to Aurora PostgreSQL**  
		• Option 1: DB Snapshots from RDS PostgreSQL restored as PostgreSQL Aurora DB  
		![[Pasted image 20230522111118.png]]
		• Option 2: Create an Aurora Read Replica from your RDS PostgreSQL, and when the replication lag is 0, promote it as its own DB cluster (can take time and cost $)  
		![[Pasted image 20230522111127.png]]
**• External PostgreSQL to Aurora PostgreSQL**  
		• Create a backup and put it in Amazon S3  
		• Import it using the aws_s3 Aurora extension  
		![[Pasted image 20230522111138.png]]
**• Use DMS if both databases are up and running**