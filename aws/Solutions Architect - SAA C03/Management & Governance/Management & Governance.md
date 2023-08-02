
CloudWatch, CloudTrail, and AWS Config are all monitoring and logging services provided by Amazon Web Services (AWS), but they serve different purposes.

CloudWatch is a monitoring service that collects and tracks metrics, logs, and events from AWS resources, applications, and services in real-time. It provides a unified view of metrics and logs from different AWS resources, allowing you to monitor and troubleshoot your AWS environment, as well as set alarms and notifications based on metric values. CloudWatch is primarily used for operational and performance monitoring of your AWS resources.

CloudTrail, on the other hand, is a logging service that records API calls and events for AWS resources in your account. It provides a history of activity for your AWS account, including who made the request, when the request was made, and what resources were affected. CloudTrail is primarily used for security and compliance monitoring, as it helps you track changes made to your AWS environment and identify potential security threats.

AWS Config, meanwhile, is a configuration management service that provides a detailed inventory of your AWS resources, their configurations, and their relationships to each other. It continuously monitors and records changes to your AWS resources and their configurations, and provides a detailed history of those changes. AWS Config is primarily used for compliance auditing and change management, as it helps you ensure that your AWS environment is compliant with regulatory requirements and industry best practices.

Some key differences between CloudWatch, CloudTrail, and AWS Config are:

1. Purpose: CloudWatch is used for operational and performance monitoring, CloudTrail is used for security and compliance monitoring, and AWS Config is used for configuration management and compliance auditing.

2. Data collected: CloudWatch collects metrics, logs, and events from AWS resources, CloudTrail records API calls and events made in your AWS account, and AWS Config collects and records detailed configuration data and resource relationships.

3. Retention: CloudWatch metrics and logs are retained for a certain period of time, while CloudTrail logs can be retained indefinitely and AWS Config configuration data is retained for 7 years.

4. Integration: CloudWatch integrates with other AWS services for monitoring and alerting, CloudTrail integrates with other security and compliance services such as AWS Security Hub and AWS Config integrates with AWS Config Rules and AWS Config Conformance Packs.

Overall, CloudWatch, CloudTrail, and AWS Config are all important services for monitoring and logging in AWS environments, but they serve different purposes and are used for different types of monitoring and management.

 
```ccard
type: folder_brief_live
```
 
![[Pasted image 20230516123739.png]]

example ELB: 

![[Pasted image 20230516123816.png]]



