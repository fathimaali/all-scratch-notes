[[Peering.]] 

![[Pasted image 20230519205446.png]]

![[Pasted image 20230519205543.png]]

![[Pasted image 20230519205643.png]]

Once VPC Peering connection is established between VPC A and VPC B

we need to edit the Route Tables 
		VPC A's Public route table - add route to direct VPC B's CIDR to be routed into VPC Peering Connection from drop down
		VPC B's public Route tabel - add route to direct VPC A's CIDR to be routed into VPC Peering connection from drop down 
		