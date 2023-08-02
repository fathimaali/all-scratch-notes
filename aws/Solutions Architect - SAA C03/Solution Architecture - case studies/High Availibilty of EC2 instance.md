Solution architecture for it

1. Standby EC2 instance 
		1. failover automatically when something is wrong
		2. monitor for something wrong : cloudwatch events 
		3. setup cloudwatch alarms to monitor metrics
		4. trigger lambda function from the cloudwatch alarm, to do failover, i.e. attach elastic IP to standy EC2
		5. perform automated failover with this architecture
		![[Pasted image 20230522131855.png]]
	
2. with an ASG : 
		1. an ASG in two AZ for example 
		2. auto failover to create a new EC2 instance in new AZ when ASG detects one EC2 instance as unhealthy
		![[Pasted image 20230522132134.png]]
3. with an ASG + EBS
		1. if EC2 is stateful and has an EBS volume with it
		2. we know EBS volumes are locked to an AZ
		3. on ASG Terminate lifecycle, i.e. when an ASG terminates an EC2 instance when deemed unhealthy there is something called ASG Terminate hook that automatically takes snapshot of the EBS volume (+tags) 
		4. ASG Terminate hook can be configured to have this EBS volume to be created and attached to the new EC2 instance. this config sits at the ASG terminate Lauch Event
		![[Pasted image 20230522132511.png]]