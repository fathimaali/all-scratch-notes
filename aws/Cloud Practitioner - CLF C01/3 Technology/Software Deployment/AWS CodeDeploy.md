does not use Cloud Formation or other AWS infrastructure items for building and deploying code. 

![[Pasted image 20230404131208.png]]


works even on the On Premise servers as well as EC2. 

Would need to provision the EC2 instances before hand. 
 perfect for HYBRID models where companies can transition from on premise to AWS.

Automate code deployment to maintain application uptime

## How it works

AWS CodeDeploy is a fully managed deployment service that automates software deployments to various compute services, such as Amazon Elastic Compute Cloud (EC2), Amazon Elastic Container Service (ECS), AWS Lambda, and your on-premises servers. Use CodeDeploy to automate software deployments, eliminating the need for error-prone manual operations.

![Diagram shows how CodeDeploy automates code deployments for developers to securely and quickly develop new features.](https://d1.awsstatic.com/products/CodeDeploy/Product-Page-Diagram_AWS-CodeDeploy.13cf5eb5c113ea98cc659974b52896f8f0adfb43.png)

## Use cases

### Automate deployments to remove manual operations

Repeat an application deployment across different groups or instances using a file and command-based install model.

### Deploy to many hosts

Manage deployments to thousands of hosts with advanced monitoring and traffic shifting.

### Use advanced deployment techniques

Support multiple deployment types, including in-place, canary, and blue/green deployments.

### Monitor health and rollback

Configure alarms that will initiate rollbacks, and stop application deployments in progress.