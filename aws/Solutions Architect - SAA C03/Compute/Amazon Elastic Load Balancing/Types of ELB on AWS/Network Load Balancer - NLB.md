Layer 4 balancer

 ![[Pasted image 20230427200940.png]]
 ![[Pasted image 20230427201024.png]]

target groups : 

![[Pasted image 20230427201200.png]]

no specific security group or rules list for NLB into EC2

Only Network Load Balancer provides both static DNS name and static IP. While, Application Load Balancer provides a static DNS name but it does NOT provide a static IP. The reason being that AWS wants your Elastic Load Balancer to be accessible using a static endpoint, even if the underlying infrastructure that AWS manages changes.