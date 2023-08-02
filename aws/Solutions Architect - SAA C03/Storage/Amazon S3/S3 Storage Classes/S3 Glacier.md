[[Amazon S3 Glacier]]

ENCRYPTION IS ENABLED BY DEFAULT 

Amazon S3 Glacier is a low-cost, long-term storage service designed for data archiving and backup. It provides three different storage classes, each with a different cost and retrieval time. Here are the details of each storage class:

1. S3 Glacier Instant Retrieval : 

	S3 Glacier Instant Retrieval delivers the lowest cost storage, up to 68% lower cost (than S3 Standard-Infrequent Access), for long-lived data that is accessed once per quarter and requires **millisecond** **retrieval**. It is designed for **rarely** **accessed** **data** that **still** **needs** **immediate** **access** in performance-sensitive use cases like image hosting, online file-sharing applications, medical imaging and health records, news media assets, and satellite and aerial imaging. S3 Glacier Instant Retrieval offers the high durability, high throughput, and similar low latency of S3 Standard-IA, with a lower per-GB storage price and slightly higher per-GB retrieval price. S3 Glacier Instant Retrieval is designed for 99.999999999% (11 9s) of data durability and 99.9% availability by redundantly storing data across multiple physically separated AWS Availability Zones in a given year.
	![[Pasted image 20230505103526.png]]

2. S3 Glacier Flexible Retrieval:
	
	S3 Glacier Flexible Retrieval delivers low-cost storage, up to 10% lower cost (than S3 Glacier Instant Retrieval), for archive data that is accessed **1-2 times per year** and is **retrieved** **asynchronously**. S3 Glacier Flexible Retrieval (formerly S3 Glacier) is the ideal storage class for archive data that **does not require immediate access but needs the flexibility to retrieve large sets of data at no cost, such as backup or disaster recovery use cases.** S3 Glacier Flexible Retrieval delivers the most flexible retrieval options that balance cost with access times ranging from minutes to hours and with free bulk retrievals. It is an ideal solution for backup, disaster recovery, offsite data storage needs, and for when some data needs to occasionally retrieved in minutes, and you don’t want to worry about costs. S3 Glacier Flexible Retrieval is designed for 99.999999999% (11 9s) of data durability and 99.99% availability by redundantly storing data across multiple physically separated AWS Availability Zones in a given year.

	Retrieval modes : Expited 1-5 mins, Standard 3-5 hours, Bulk : 5-12 hours
	![[Pasted image 20230505103840.png]]

3. S3 Glacier Deep Archive : 
	
	S3 Glacier Deep Archivedelivers the lowest cost storage, up to 75% lower cost (than S3 Glacier Flexible Retrieval), for **long-lived archive data that is accessed less than once per year and is retrieved asynchronously.** At just $0.00099 per GB-month (or $1 per TB-month), S3 Glacier Deep Archive offers the **lowest** **cost** **storage** in the cloud, at prices significantly lower than storing and maintaining data in on-premises tape or archiving data off-site. S3 Glacier Deep Archive is a cost-effective and easy-to-manage alternative to tape. It is designed for customers — particularly those in the financial services, healthcare, media and entertainment and public sector — that retain data sets for 7-10 years or longer to meet customer needs and regulatory compliance requirements. S3 Glacier Deep Archive is designed for 99.999999999% (11 9s) of data durability and 99.99% availability by redundantly storing data across multiple physically separated AWS Availability Zones in a given year.

	Retrieval modes : Standard - within 12 hours, Bulk - within 48 hours 

	![[Pasted image 20230505104119.png]]

