developer centric view of deploying an application on AWS.

![[Pasted image 20230404131038.png]]

![[Pasted image 20230404131054.png]]
![[Pasted image 20230404131118.png]]
![[Pasted image 20230404131135.png]]

Platform as a Service (PaaS)

managed service
	Instance config, OS 
	deployment strategies 
	capacity provisioning
	load balancing 
	auto scaling group
	application health monitoring 

3 arch models:
	single instance deployment 
	LB + ASG : web apps 
	ASG : non web apps

suppports many platforms/languages 
programming languages, docker

Health Monitoring : also pushes metrics to [[Amazon CloudWatch]].

can launch an app 
	this will read your code, go to cloudformation, create the AWS infrastructure.
this same app can be updated 

