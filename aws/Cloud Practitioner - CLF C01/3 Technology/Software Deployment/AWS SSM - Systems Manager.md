https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html

## Systems Manager capabilities

Systems Manager groups capabilities into the following categories. Choose the tabs under each category to learn more about each capability.

**Topics**

-   [Application management](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#systems-manager-application-management)
-   [Change management](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#capabilities-actions-and-change)
-   [Node management](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#capabilities-instances-and-nodes)
-   [Operations management](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#capabilities-operations-management)
-   [Quick Setup](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#capabilities-quick-setup)
-   [Shared resources](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html#capabilities-shared)



![[Pasted image 20230330150258.png]]

![[Pasted image 20230330150354.png]]

**SSM - Session Manager**

allows you to start a secure shell on EC2 instances and On Premise ones. 

![[Pasted image 20230330150520.png]]


to setup a SSM, EC2 instance needs to have the IAM role with permission AmazonSSMManagedInstanceCore, security group should not allow port 22 meaning no SSH access. 


**FLEET MANAGER :** 

Can help list down things under your fleet. 








