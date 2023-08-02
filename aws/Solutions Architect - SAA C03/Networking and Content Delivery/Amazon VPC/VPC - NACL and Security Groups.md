NACL - Network Access Control List 
		stateless
		subnet level firewall 
		a subnet can have only ONE NACL, new subnets are assigned default NACL
		different subnets can use same NACL
		NACL Rules : 
				numbered from 1-32766
				1 highest priority/precedence
				first rule match will drive the decision
				* (asterisk) rule, denies by default if no rule match 
				recommended practise to add rules in increments of 100, so adding 
					or moving around rules in between them is easier (its like MMRUN step numbers)
				newly created NACL will deny everything.
				USE CASE : block IP address at the subnet level
Security Group
		stateful

Incoming Request : describing stateful vs stateless
		![[Pasted image 20230519201327.png]]
Outgoing Request : describing stateful vs stateless
		![[Pasted image 20230519201410.png]]


Where are NACLs in the VPC diagram 
		![[Pasted image 20230519201847.png]]
	
Default NACL : 
		allow everything in and everything out
		if this is associated with a subnet, then that subnet would have all in and 
			out
			![[Pasted image 20230519202223.png]]
		

Ephemeral Ports
		![[Pasted image 20230519203948.png]]

		![[Pasted image 20230519204122.png]]

![[Pasted image 20230519204350.png]]

[[Network Security in VPC.]]

![[Pasted image 20230519204453.png]]



