https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html 

Parameter Store, a capability of AWS Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. 

## How can Parameter Store benefit my organization?

Parameter Store offers these benefits:

-   Use a secure, scalable, hosted secrets management service with no servers to manage.
-   Improve your security posture by separating your data from your code.
-   Store configuration data and encrypted strings in hierarchies and track versions.
-   Control and audit access at granular levels.
-   Store parameters reliably because Parameter Store is hosted in multiple Availability Zones in an AWS Region.
    

## Who should use Parameter Store?

-   Any AWS customer who wants to have a centralized way to manage configuration data.
-   Software developers who want to store different logins and reference streams.
-   Administrators who want to receive notifications when their secrets and passwords are or aren't changed.

## What are the features of Parameter Store?

-   **Change notification**
    
    You can configure change notifications and invoke automated actions for both parameters and parameter policies. For more information, see [Setting up notifications or trigger actions based on Parameter Store events](https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-paramstore-cwe.html).
    
-   **Organize parameters**
    
    You can tag your parameters individually to help you identify one or more parameters based on the tags you've assigned to them. For example, you can tag parameters for specific environments or departments. For more information, see [Tagging Systems Manager parameters](https://docs.aws.amazon.com/systems-manager/latest/userguide/tagging-parameters.html).
    
-   **Label versions**
    
    You can associate an alias for versions of your parameter by creating labels. Labels can help you remember the purpose of a parameter version when there are multiple versions.
    
-   **Data validation**
    
    You can create parameters that point to an Amazon Elastic Compute Cloud (Amazon EC2) instance and Parameter Store validates these parameters to make sure that it references expected resource type, that the resource exists, and that the customer has permission to use the resource. For example, you can create a parameter with Amazon Machine Image (AMI) ID as a value with `aws:ec2:image` data type, and Parameter Store performs an asynchronous validation operation to make sure that the parameter value meets the formatting requirements for an AMI ID, and that the specified AMI is available in your AWS account.
    
-   **Reference secrets**
    
    Parameter Store is integrated with AWS Secrets Manager so that you can retrieve Secrets Manager secrets when using other AWS services that already support references to Parameter Store parameters.
    
-   **Accessible from other AWS services**
    
    You can use Parameter Store parameters with other Systems Manager capabilities and AWS services to retrieve secrets and configuration data from a central store. Parameters work with Systems Manager capabilities such as Run Command, Automation, and State Manager, capabilities of AWS Systems Manager. You can also reference parameters in a number of other AWS services, including the following:
    
    -   Amazon Elastic Compute Cloud (Amazon EC2)
        
    -   Amazon Elastic Container Service (Amazon ECS)
        
    -   AWS Secrets Manager
        
    -   AWS Lambda
        
    -   AWS CloudFormation
        
    -   AWS CodeBuild
        
    -   AWS CodePipeline
        
    -   AWS CodeDeploy
        
    
-   **Integrate with other AWS services**
    
    Configure integration with the following AWS services for encryption, notification, monitoring, and auditing:
    
    -   AWS Key Management Service (AWS KMS)
        
    -   Amazon Simple Notification Service (Amazon SNS)
        
    -   Amazon CloudWatch: For more information, see [Configuring EventBridge rules for parameters and parameter policies](https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-paramstore-cwe.html#cwe-parameter-changes).
        
    -   Amazon EventBridge: For more information, see [Monitoring Systems Manager status changes using Amazon SNS notifications](https://docs.aws.amazon.com/systems-manager/latest/userguide/monitoring-sns-notifications.html) and [Reference: Amazon EventBridge event patterns and types for Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/reference-eventbridge-events.html).
        
    -   AWS CloudTrail: For more information, see [Logging AWS Systems Manager API calls with AWS CloudTrail](https://docs.aws.amazon.com/systems-manager/latest/userguide/monitoring-cloudtrail-logs.html).