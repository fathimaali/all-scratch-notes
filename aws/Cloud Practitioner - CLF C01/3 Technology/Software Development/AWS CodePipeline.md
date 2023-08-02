AWS version of a CI/CD

build - test - deploy 

![[Pasted image 20230330144758.png]]

## How it works

AWS CodePipeline is a fully managed continuous delivery service that helps you automate your release pipelines for fast and reliable application and infrastructure updates.

![Diagram of how AWS CodePipeline automates the build, test, and deploy phases of your release process every time there is a code change, based on the release model you define.](https://d1.awsstatic.com/products/codepipeline/Product-Page-Diagram_AWS-CodePipeline.4a1bea38d3c8d3b2c1384dd0a7d2a858f4350471.jpg)

## Use cases

### Define your pipeline structure

Update existing pipelines and provide templates for creating new pipelines with a declarative JSON document.

### Receive notifications for events

Monitor events that impact your pipelines with Amazon Simple Notification Service (SNS), which provides a status message and link to the source of the event.

### Control and grant access

Manage who can change and control your release workflow with AWS Identity and Access Management (IAM).

### Integrate your own custom systems

Register a custom action and hook servers into your pipeline by integrating the CodePipeline open source agent with your servers.