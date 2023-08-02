1. Simple
		1. first line of defense is NACL on subnet of VPC : set deny rules to deny IP
		2. security group of EC2 : set allow rules to authorize only a set of IPs (deny rules are not configurable)
		3. optional firewall software can be run on EC2 -- CPU cost 
		![[Pasted image 20230522125542.png]]
	
2. with ALB
	1. connection termination : because the client to VPC connection is terminated and a new connection is made from ALB to EC2
	2. NACL - filter out IPs, at subnet level of VPC
	3. configure security group at ALB : allow clients range of IPs
	4. configure EC2 to only allow traffic from ALB's security group
		![[Pasted image 20230522125730.png]]
3. with NLB
		1. does not do connection termination : the connection just passes through to the client to the NLB to the EC2
		2. NACL : filter out IPs,
		3. no security group for NLB 
		4. security group for EC2 : only line of defence is NACL, so EC2 instance effectively is able to know the client's IP
		![[Pasted image 20230522130004.png]]
4. ALB + WAF
		1. WAF : more expensive : but helps perform some complex filtering 
		2. service installed on the ALB, not a service BETWEEN client and ALB
		![[Pasted image 20230522130128.png]]
5. ALB, CloudFront WAF
	1. CloudFront - service BETWEEN client and ALB
	2. CloudFront sits outside our VPC
	3. as such our ALB would need to allow all CloudFront public IP
	4. ALB does not see any client IP
	5. NACL is not helpful as we dont see client IP
	6. to block a client IP, we need to rely on CloudFront restriction policies
	7. also can use WAF - IP address filtering - can be installed on CloudFront
		![[Pasted image 20230522130143.png]]