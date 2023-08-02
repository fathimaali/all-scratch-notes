https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html

A tag is a label that you or AWS assigns to an AWS resource. Each tag consists of a _key_ and a _value_. For each resource, each tag key must be unique, and each tag key can have only one value. You can use tags to organize your resources, and cost allocation tags to track your AWS costs on a detailed level. After you activate cost allocation tags, AWS uses the cost allocation tags to organize your resource costs on your cost allocation report, to make it easier for you to categorize and track your AWS costs. AWS provides two types of cost allocation tags, an _AWS-generated tags_ and _user-defined tags_. AWS, or AWS Marketplace ISV defines, creates, and applies the AWS-generated tags for you, and you define, create, and apply user-defined tags. You must activate both types of tags separately before they can appear in Cost Explorer or on a cost allocation report.

The following diagram illustrates the concept. In the example, you've assigned and activated tags on two Amazon EC2 instances, one tag called Cost Center and another tag called Stack. Each of the tags has an associated value. You also activated the AWS-generated tags, `createdBy` before creating these resources. The `createdBy` tag tracks who created a resource. The user-defined tags use the `user` prefix, and the AWS-generated tag uses the `aws:` prefix.

![Example Keys](https://docs.aws.amazon.com/images/awsaccountbilling/latest/aboutv2/images/Tag_Example.png)


![[Pasted image 20230403175113.png]]

## Resource Groups and Tag Editor

![[Pasted image 20230403175153.png]]

