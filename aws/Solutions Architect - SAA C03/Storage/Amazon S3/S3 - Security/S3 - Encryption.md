4 types for Data at Rest
	![[Pasted image 20230505113618.png]]

1. SSE S3: 
		![[Pasted image 20230505113808.png]]
		enabled by default 
		uses Advanced Encryption Standard (AES-256).
		encryption and decryption all handled at server side by AWS.
		
2. SSE KMS: : [[S3 - example (KMS)]] 
		![[Pasted image 20230505114609.png]]
		![[Pasted image 20230505114642.png]]

	encryption and decryption is done using the KMS keys, so if the bucket has all the objects encrypted using a KMS key, then the number of calls to AWS KMS is tremendously increased. 

1. SSE C: 
		![[Pasted image 20230505114805.png]]

	Encryption is done at the server side but with a client provided KEY, so if the decryption needs to happen, they would need to send the key over HTTPS.
	Not Supported by the AWS Console, only can use it by AWS CLI or AWS SDK.
	
1. CSE:
		![[Pasted image 20230505114914.png]]

encryption and decryption all is carried on at the client side, the keys are also obviously at the client side. 
all happens outside of AWS.

![[Pasted image 20230505121442.png]]



**Encryption for Data in Transit  :** 

SSL/TLS: 

![[Pasted image 20230505115552.png]]

![[Pasted image 20230505115634.png]]

