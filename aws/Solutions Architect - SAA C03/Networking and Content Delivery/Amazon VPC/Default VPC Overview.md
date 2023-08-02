given by AWS when you start using the cloud, for new accounts

default VPC would have internet access

we get public and private DNS for our VPC

A few components : 
		VPC
				IPv4 - CIDR block 
				flow logs are not enabled
				no tags
		Subnets 
				one in each AZ
				each subnet has a CIDR
		Route table : helps traffic being routed in VPC
		Network ACL 
		Internet Gateway : gives internet access to EC2 instance
		