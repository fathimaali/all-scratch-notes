Backup  
		• EBS Snapshots, RDS automated backups / Snapshots, etc...  
		• Regular pushes to S3 / S3 IA / Glacier, Lifecycle Policy, Cross Region Replication  
		• From On-Premise: Snowball or Storage Gateway  
• High Availability  
		• Use Route53 to migrate DNS over from Region to Region  
		• RDS Multi-AZ, ElastiCache Multi-AZ, EFS, S3  
		• Network : Site to Site VPN as a recovery from Direct Connect  
• Replication  
		• RDS Replication (Cross Region), AWS Aurora + Global Databases  
		• Database replication from on-premises to RDS  
		• Storage Gateway  
• Automation  
		• CloudFormation / Elastic Beanstalk to re-create a whole new environment  
		• Recover / Reboot EC2 instances with CloudWatch if alarms fail  
		• AWS Lambda functions for customized automations  
• Chaos testing 
		• Netflix has a “simian-army” randomly terminating EC2