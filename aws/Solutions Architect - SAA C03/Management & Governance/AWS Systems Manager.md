[[AWS SSM - Systems Manager]] 

[[SSM Parameter Store]] 

[[AWS SSM - Systems Manager]] 
1. Session Manager
		to setup a SSM, EC2 instance needs to have the IAM role with permission AmazonSSMManagedInstanceCore, security group should not allow port 22 meaning no SSH access. 		
		Fleet Manager : managed nodes, once we have an EC2 to be managed under SSM
		Session Manager : access SSH to managed EC2 instances
		![[Pasted image 20230522135921.png]]
2. Run Command
	 ![[Pasted image 20230522140543.png]]
3. Patch Manager
		![[Pasted image 20230522140754.png]]
4. Maintenance Windows : 
		![[Pasted image 20230522140829.png]]
5. Automation : 
		![[Pasted image 20230522140853.png]]

