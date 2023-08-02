https://aws.amazon.com/cloudformation/

CloudFormation cannot help with moving **data** and applications from one Region into another Region.

![[Pasted image 20230404130840.png]]

![[Pasted image 20230404130857.png]]
![[Pasted image 20230404130911.png]]
![[Pasted image 20230404130925.png]]


Infrastructure as a Code (IaaC)

Code your AWS infrastrusture into a YAML file, then can choose this template while creating your AWS CloudFormation Stack.

This can create you AWS infrastructure without having to use the console or any other method, just  creating a template or uploading an existing template, would create the entire AWS stack for you. 

Can also update the stack template once it has been uploaded and resources created. 

update template would simply Modify existing resources as necessary and add new resources based on the updated template file used. 

One template be used across Regions, Accounts. 

## How it works

AWS CloudFormation lets you model, provision, and manage AWS and third-party resources by treating infrastructure as code.

![](https://d1.awsstatic.com/Products/product-name/diagrams/product-page-diagram_CloudFormation.ad3a4c93b4fdd3366da3da0de4fb084d89a5d761.png)

## Use cases

### Manage infrastructure with DevOps

Automate, test, and deploy infrastructure templates with continuous integration and delivery (CI/CD) automations.  

### Scale production stacks

  
Run anything from a single Amazon Elastic Compute Cloud (EC2) instance to a complex multi-region application.  

### Share best practices

  
Define an Amazon Virtual Private Cloud (VPC) subnet or provisioning services like AWS OpsWorks or Amazon Elastic Container Service (ECS) with ease.