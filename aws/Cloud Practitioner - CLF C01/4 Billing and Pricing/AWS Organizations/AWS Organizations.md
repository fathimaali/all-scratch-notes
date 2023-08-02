https://docs.aws.amazon.com/controltower/latest/userguide/organizations.html

	Global Service

![[Pasted image 20230403170212.png]]
![[Pasted image 20230403170304.png]]
![[Pasted image 20230403170327.png]]AWS Organizations is an account management service that lets you consolidate multiple AWS accounts into an organization that you create and centrally manage. 
With Organizations, you can create member accounts and invite existing accounts to join your organization. 
You can organize those accounts into groups and attach policy-based controls. For more information, see _[AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)_.

In AWS Control Tower, Organizations helps centrally manage billing; control access, compliance, and security; and share resources across your member AWS accounts. Accounts are grouped into logical groups, called organizational units (OUs). For more information on Organizations, see _[AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)_.

AWS Control Tower uses the following OUs:

-   **Root** – The parent container for all accounts and all other OUs in your landing zone.
    
-   **Security** – This OU contains the log archive account, the audit account, and the resources they own.
    
-   **Sandbox** – This OU is created when you set up your landing zone. It and other child OUs in your landing zone contain your member accounts. These are the accounts that your end users access to perform work on AWS resources.

