[[KMS and CloudHSM]] 

Customer Master Key -> is now called KMS Key

region : scope

![[Pasted image 20230518104916.png]]

KMS Key Types : 

Symmetric:
Asymmetric:

![[Pasted image 20230518105147.png]]

Other Types : [[Customer Master Keys. CMK]]  -> revise 

Customer Managed KMS Key : 
		not free, $1/month
		automatic key rotation : needs to be enabled - automatic every 1 year
Customer Managed Imported Key : 
		not free, $1/month 
		must be a symmetric key 
		automatic key rotation : no automation, needs to be manually done using
			alias
AWS Managed KMS Key : 
		free
		aws/service-name, eg. aws/rds
		automatic key rotation : automatic every 1 year
AWS Owned KMS Key :
		free
		SSE-S3, SSE-SQS, SSE-DDB(default key)
		automatic key rotation : cannot enable or disable this

we pay for API calls to KMS ($0.04 / 10,000 calls)





```ccard
type: folder_brief_live
```
 
