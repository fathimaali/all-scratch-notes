[[AWS ALB - Application Load Balancer]]   

![[Pasted image 20230427171129.png]]

![[Pasted image 20230427171245.png]]

example: 
path:
		![[Pasted image 20230427171333.png]]
query string/parameter routing : 
		![[Pasted image 20230427171554.png]]
	
Target Groups : 

![[Pasted image 20230427171430.png]]

![[Pasted image 20230427171646.png]]

Hands on : 

tighten security : in my EC2 instance security group, inbound rule to only allow traffic coming in from the load balancer security group.

More inbound rules and routing rules can be applied on the ALB level using rules that can be applied on the ALB listener. 


![[Pasted image 20230427200357.png]]

![[Pasted image 20230427200415.png]]