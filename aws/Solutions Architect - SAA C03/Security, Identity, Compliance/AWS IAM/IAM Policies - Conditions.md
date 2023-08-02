[[IAM Policies]] 

IAM Conditions
		aws:SourceIP
			allow single or block of IP addresses - IpAddress
			restrict single or block of IP addresses - NotIpAddress					
		aws:RequestedRegion : restrict access based on region 
		aws:CurrentTime : restrict access based on time
		aws:MulltiFactorAuthPresent : restrict access based on if MFA enabled or not
		aws:UserAgent : restrict access based on user agent string of requester browser
		aws:SecureTransport : restrict based on if HTTPS or not
		aws:PrincipalType : restrict based on IAM Principal
		ec2:ResourceTag : restrict based on Tags on resources for EC2
		s3:ListBucket
		s3:GetObject
		s3:PutObject
		s3:DeleteObject
		