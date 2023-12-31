https://aws.amazon.com/premiumsupport/technology/aws-health-dashboard/

The AWS Health Dashboard is the single place to learn about the availability and operations of AWS services. 
You can view the overall status of AWS services, and you can sign in to view personalized communications about your particular AWS account or organization. 
Your account view provides deeper visibility into resource issues, upcoming changes, and important notifications.

## Benefits

### Personalized view of service health

When you sign in to the AWS Health Dashboard, you have a personalized view of the AWS service status that powers your application. Use the AWS Health Dashboard to learn about specific operational issues that affect your account. For example, if you receive an event for a lost [Amazon Elastic Block Store (EBS)](https://aws.amazon.com/ebs/) volume associated with one of your [Amazon EC2](https://aws.amazon.com/ec2/) instances, you can quickly view how your resources are impacted, helping you to troubleshoot and remediate.  

### Proactive notifications

In addition to enabling emails to receive important Health events, you can configure [AWS Health Aware](https://aws.amazon.com/blogs/mt/aws-health-aware-customize-aws-health-alerts-for-organizational-and-personal-aws-accounts/) to receive information in your Slack channel or operational tooling. For example, if a maintenance event is scheduled for one of your [Amazon EC2](https://aws.amazon.com/ec2-sla/) instances, you can receive an alert with information in your preferred communication channel so you can actively address any issues for the upcoming change.  

### Detailed troubleshooting guidance

When you get a Health event, it includes remediation details and specific guidance so that you can take action for events that affect your resources. For example, if a hardware issue affects one of your [Amazon Elastic Block Store](https://aws.amazon.com/ebs/) (EBS) volumes, the alert includes a list of affected resources, and recommendations and help links to restore your volume from a snapshot. This helps you reduce the amount of time to resolve issues.  

### Integration and automation

You can use [Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html) to build custom rules and select targets, such as [AWS Lambda](https://aws.amazon.com/lambda/) functions, to define automated remediation actions for specific events. You can use the AWS Health API, the service that powers AWS Health Dashboard, to integrate health data and notifications with your existing in-house or third-party IT management tools. The AWS Health API is part of an AWS Business Support or AWS Enterprise Support plan.

### Fine-grained access control by using IAM

The AWS Health Dashboard supports access control so you can set up permissions based on event metadata. This enables you to grant or deny access to an [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/) user based on attributes, such as event types, specific services, or other role-based attributes. You can restrict access of sensitive events, such as security events, to only the users that need to see them.

### Aggregate health events across AWS Organizations

If you use [AWS Organizations](https://aws.amazon.com/organizations/), you can use AWS Health to [aggregate notifications](https://docs.aws.amazon.com/health/latest/ug/aggregate-events.html) from all accounts in your organization. This provides you a centralized and real-time view for all AWS Health events posted to individual accounts in your organization, including operational issues, scheduled maintenance, and account notifications.

![[Pasted image 20230331142233.png]]

![[Pasted image 20230331142343.png]]

![[Pasted image 20230331142407.png]]

