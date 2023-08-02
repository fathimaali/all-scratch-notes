log groups 

![[Pasted image 20230516111315.png]]

Here are some of the key features of Amazon CloudWatch Logs:

1.  Log collection: CloudWatch Logs allows you to collect log data from a variety of sources, including AWS services such as EC2, Lambda, and CloudTrail, as well as from on-premises servers and applications.
    
2.  Log storage: CloudWatch Logs stores log data in highly durable and scalable storage, making it easy to retrieve and analyze the data.
    
3.  Log analysis: CloudWatch Logs provides a variety of tools for analyzing log data, including search and filter capabilities, graphs and visualizations, and real-time monitoring.
    
4.  Log retention: CloudWatch Logs allows you to configure retention policies for your log data, so you can retain the data for as long as necessary for compliance or auditing purposes.
    
5.  Log access control: CloudWatch Logs provides fine-grained access control for log data, allowing you to restrict access to logs to only authorized users and roles.
    
6.  Log integration: CloudWatch Logs integrates with other AWS services such as CloudTrail, AWS Config, and AWS Lambda, as well as with third-party services and tools such as Splunk and Elasticsearch.


![[Pasted image 20230516111352.png]]

![[Pasted image 20230516111443.png]]

![[Pasted image 20230516111556.png]]

In Amazon CloudWatch, log subscription refers to the process of forwarding log data from one or more AWS resources to a CloudWatch Logs group in another AWS account or to an external destination such as Amazon Kinesis Data Firehose, Amazon Elasticsearch, or Amazon S3.

![[Pasted image 20230516111619.png]]

![[Pasted image 20230516111637.png]]

There are several different types of log subscription available in CloudWatch, including:

1.  Cross-account log subscription: This allows you to forward log data from one AWS account to a CloudWatch Logs group in another AWS account.
    
2.  CloudWatch Logs subscription filters: This allows you to filter log data based on specific patterns or keywords, and forward the filtered data to an external destination.
    
3.  AWS Lambda subscription: This allows you to use AWS Lambda functions to process and forward log data to an external destination.
    
4.  Kinesis Data Firehose subscription: This allows you to forward log data to Amazon Kinesis Data Firehose, which can then transform and load the data into other AWS services such as S3, Redshift, or Elasticsearch.