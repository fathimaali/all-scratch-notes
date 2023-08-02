![[Pasted image 20230403221744.png]]

An AMI includes the following:

One or more EBS snapshots, or, for instance-store-backed AMIs, a template for the root volume of the instance (for example, an operating system, an application server, and applications).

Launch permissions that control which AWS accounts can use the AMI to launch instances.

A block device mapping that specifies the volumes to attach to the instance when it's launched.

The following diagram summarizes the AMI lifecycle: ![](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/ami_lifecycle.png) vi

AMIs are built for a specific AWS Region, they're unique for each AWS Region. You can't launch an EC2 instance using an AMI in another AWS Region, but you can copy the AMI to the target AWS Region and then use it to create your EC2 instances.

![[Pasted image 20230403221801.png]]
