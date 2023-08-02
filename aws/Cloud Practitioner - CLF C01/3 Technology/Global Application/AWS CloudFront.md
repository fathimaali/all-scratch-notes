Content Delivery Network : 

cache data in Edge Locations. 

You can create and manage CloudFront Distributions, they use Origin Access Control for Security. 

You can use AWS WAF web access control lists (web ACLs) to help minimize the effects of a distributed denial of service (DDoS) attack. For additional protection against DDoS attacks, AWS also provides AWS Shield Standard and AWS Shield Advanced.

![[Pasted image 20230330161730.png]]

![[Pasted image 20230330161815.png]]

![[Pasted image 20230505163235.png]]

S3:
![[Pasted image 20230330161928.png]]

[[AWS CloudFront]] vs [[S3 Cross Region Replication]]

![[Pasted image 20230330162030.png]]

Create a CloudFront for demo : S3 as origin 

S3 bucket as origin, select any bucket. 
Although the objects in the bucket are not public, CloudFront can be enabled to make it accessbile. 

![[Pasted image 20230330162539.png]]

AN S3 bucket policy is necessary. This one is auto generated at CloudFront when you select Origin Access Control 

{
        "Version": "2008-10-17",
        "Id": "PolicyForCloudFrontPrivateContent",
        "Statement": [
            {
                "Sid": "AllowCloudFrontServicePrincipal",
                "Effect": "Allow",
                "Principal": {
                    "Service": "cloudfront.amazonaws.com"
                },
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::hafilaalis-bucket-3/*",
                "Condition": {
                    "StringEquals": {
                      "AWS:SourceArn": "arn:aws:cloudfront::639941298503:distribution/E2QRMWSHXPINRW"
                    }
                }
            }
        ]
      }



## How it works

Amazon CloudFront is a content delivery network (CDN) service built for high performance, security, and developer convenience.

[![](https://d1.awsstatic.com/products/cloudfront/product-page-diagram_CloudFront_HIW.475cd71e52ebbb9acbe55fd1b242c75ebb619a2e.png)](https://aws.amazon.com/cloudfront/#) 
## Use cases

### Deliver fast, secure websites

  
Reach viewers across the globe in milliseconds with built-in data compression, edge compute capabilities, and field-level encryption.  

### Accelerate dynamic content delivery and APIs

Optimize dynamic web content delivery with the purpose-built and feature-rich AWS global network infrastructure supporting edge termination and WebSockets.  

### Stream live and on-demand video

  
Start streams quickly, play them with consistency, and deliver high-quality video to any device with AWS Media Service and AWS Elemental integration.  

### Distribute patches and updates

  
Scale automatically to deliver software, game patches, and IoT over-the-air (OTA) updates at scale with high transfer rates.

