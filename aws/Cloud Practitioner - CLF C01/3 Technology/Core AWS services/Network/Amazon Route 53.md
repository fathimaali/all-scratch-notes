AWS' DNS service

https://aws.amazon.com/route53/ 

![[Pasted image 20230330160609.png]]

The Simple Routing Policy : the only policy with no Health Checks.  
Weighted Routing Policy 
Latency Routed Policy 
Failover Routing Policy 

![[Pasted image 20230330160908.png]]

![[Pasted image 20230330161006.png]]

## How it works

Amazon Route 53 is a highly available and scalable [Domain Name System (DNS)](https://aws.amazon.com/route53/what-is-dns/) web service. Route 53 connects user requests to internet applications running on AWS or on-premises.

![Diagram that shows how Amazon Route 53 connects end users to internet applications. Described at the link "Enlarge and read image description."](https://d1.awsstatic.com/Route53/product-page-diagram_Amazon-Route-53_HIW%402x.4c2af00405a0825f83fca113352b480b19d9210e.png)

## Use cases

### Manage network traffic globally

Create, visualize, and scale complex routing relationships between records and policies with easy-to-use global DNS features.

### Build highly available applications

Set routing policies to pre-determine and automate responses in case of failure, like redirecting traffic to alternative Availability Zones or Regions.

### Set up private DNS

Assign and access custom domain names in your Amazon Virtual Private Cloud (VPC). Use internal AWS resources and servers without exposing DNS data to the public Internet.