## Groups

Put users into group and assign [[IAM Policies]] to the groups.

Similiar to AS400 user groups. 

## Users

![[Pasted image 20230330124024.png]]

Every physical user would have a user ID to login to the console. 
The one that owns the AWS account would have a root user ID.
A user can be part of several groups or belong to no group at all. 

Permissions can be assigned to a user :
Inheritance from [[IAM Users and Groups]] or 
Inline permisssion, attached directly to the user. 

Access Key for each user can be generated from the console. 
The [[Security]] of the user can be protected in two ways. : Password policy, MFA.

The user access can be viewed through [[IAM Security Tools]] : IAM Credentials Report, IAM Access Advisor. 


![[Pasted image 20230403204908.png]]

