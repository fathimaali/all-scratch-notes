Application and Infrastructure Monitoring 

https://aws.amazon.com/cloudwatch/

You can use Amazon CloudWatch Logs to monitor, store, and access your log files from Amazon Elastic Compute Cloud (Amazon EC2) instances, AWS CloudTrail, Route 53, and other sources such as on-premises servers.

CloudWatch Logs enables you to centralize the logs from all of your systems, applications, and AWS services that you use, in a single, highly scalable service. You can then easily view them, search them for specific error codes or patterns, filter them based on specific fields, or archive them securely for future analysis.

Collect, access, and analyze your resource and application data using powerful visualization tools.

Improve operational performance using alarms and automated actions set to activate at predetermined thresholds.

Seamlessly integrate with more than 70 AWS services for simplified monitoring and scalability.

Troubleshoot operational problems with actionable insights derived from logs and metrics in your CloudWatch dashboards.

## How it works

Amazon CloudWatch collects and visualizes real-time logs, metrics, and event data in automated dashboards to streamline your infrastructure and application maintenance.

![Diagram of how Amazon CloudWatch helps users collect, monitor, and understand their use of AWS resources.](https://d1.awsstatic.com/reInvent/reinvent-2022/cloudwatch/Product-Page-Diagram_Amazon-CloudWatch.095eb618193be7422d2d34e3abd5fdf178b6c0e2.png)

## Use cases

### Monitor application performance

	Visualize performance data, create alarms, and correlate data to understand and resolve the root cause of performance issues in your AWS resources.

### Perform root cause analysis

	Analyze metrics, logs, logs analytics, and user requests to speed up debugging and reduce overall mean time to resolution.

### Optimize resources proactively

	Automate resource planning and lower costs by setting actions to occur when thresholds are met based on your specifications or machine learning models.
	
### Test website impacts

	Find out exactly when your website is impacted and for how long by viewing screenshots, logs, and web requests at any point in time.

Can be added to any metric of any service for which CloudWatch metrics data are collected. 

for eg. 

if we want to set up a cloudwatch alarm for an EC2 - CPUUtilization metric, we can set it up from the CloudWatch console, create a new SNS topic which will then publish the notification to email. 
	Or this one can be created from the EC2 console as well.

Other than sending notifications, alarms can be set to perform action on the issue at hand. 

	eg, reboot EC2, scale it up.




**LOGS :** 
collect log files.

what is log files?
	log of the actions performed.
	used for troubleshooting.

![[Pasted image 20230331115620.png]]

Example : EC2 instance logs. 
	logs here are not collected by default (unlike eg. metrics from EC2)
	need to setup a cloudwatch log agent from EC2 instance to send logs from EC2 instance to CloudWatch.
	needs to have correct IAM role and permissions to.
	Cloudwatch log agent can also be setup for ON PREMISE servers as well.

![[Pasted image 20230331122119.png]]



