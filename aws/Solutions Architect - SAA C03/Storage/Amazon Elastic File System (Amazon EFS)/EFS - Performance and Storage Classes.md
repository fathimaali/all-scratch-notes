Performance : 

![[Pasted image 20230427155216.png]]

Storage Classes

![[Pasted image 20230427155400.png]]

![[Pasted image 20230427155536.png]]

Security groups for EFS : 

https://docs.aws.amazon.com/efs/latest/ug/accessing-fs-create-security-groups.html

CAN BE AUTO CREATED WHILE LAUNCHING AN INSTANCE AS WELL. the two security groups needed, i.e. one for the EFS and another for the EC2 instance, both of these would be autocreated. 

Both an Amazon EC2 instance and a mount target have associated security groups. These security groups act as a virtual firewall that controls the traffic between them. If you don't provide a security group when creating a mount target, Amazon EFS associates the default security group of the VPC with it.

Regardless, to enable traffic between an EC2 instance and a mount target (and thus the file system), you must configure the following rules in these security groups:

-   The security groups that you associate with a mount target must allow inbound access for the TCP protocol on the NFS port from all EC2 instances on which you want to mount the file system.
    
-   Each EC2 instance that mounts the file system must have a security group that allows outbound access to the mount target on the NFS port.
    
## Creating security groups by using the AWS Management Console

You can use the AWS Management Console to create security groups in your VPC. To connect your Amazon EFS file system to your Amazon EC2 instance, you must create two security groups: one for your Amazon EC2 instance and another for your Amazon EFS mount target.

1.  Create two security groups in your VPC. For instructions, see [Creating a Security Group](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html#CreatingSecurityGroups) in the _Amazon VPC User Guide_.
    
2.  In the VPC console, verify the default rules for these security groups. Both security groups should have only an outbound rule that allows traffic to leave.
    
3.  You must authorize additional access to the security groups as follows:
    
    1.  Add a rule to the EC2 security group to allow SSH access to the instance on port 22 as shown following. This is useful if you're planning on using an SSH client like PuTTY to connect to and administer your EC2 instance through a terminal interface. Optionally, you can restrict the **Source** address.
        
    2.  Add a rule to the mount target security group to allow inbound access from the EC2 security group on TCP port 2049. The security group in the **Source** column is the security group associated with the EC2 instance.
		- Note
		       You don't need to add an outbound rule because the default outbound rule allows all traffic to leave. (If you remove the default outbound rule, you must add an outbound rule to open a TCP connection on the NFS port, and identify the mount target security group as the destination.)
    
4. Verify that both security groups now authorize inbound and outbound access as described in this section.
