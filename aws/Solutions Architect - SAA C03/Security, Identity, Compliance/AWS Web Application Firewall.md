[[AWS WAF - Web Application Firewall]] 

![[Pasted image 20230518130850.png]]

Web ACL : 

![[Pasted image 20230518143528.png]]

Use-case:
		fixed IP
				NLB has fixed IP, but WAF does not support NLB
				ALB has fixed IP, and WAF supports ALB
				so how to use WAF + ALB to get fixed IP
						Global Accelerator
						![[Pasted image 20230518143716.png]]
		