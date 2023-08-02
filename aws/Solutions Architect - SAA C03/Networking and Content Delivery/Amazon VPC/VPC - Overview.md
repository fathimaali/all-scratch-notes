max 5 VPC per region
max 5 CIDR per VPC
min and max CIDR allowed : /28 - 16 IPs, /16 - 65536 IPs
VPC is private, so only private IPv$ range are allowed 
		10.0.0.0 - 10.0.0.255 (10.0.0.0/8)
		172.16.0.0 - 172.31.255.255 (172.16.0.0/12)
		192.168.0.0 - 192.168.255.255 (192.168.0.0/16)

make sure the VPC CIDRs are not overlapping with other networks or your VPCs

![[Pasted image 20230519135621.png]]
![[Pasted image 20230520122445.png]]

![[Pasted image 20230520122547.png]]

![[Pasted image 20230520122649.png]]

