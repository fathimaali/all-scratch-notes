[[Solutions Architect - SAA C03/Serverless/AWS Lambda/AWS Lambda|AWS Lambda]], SNS and SQS

1. SQS and Lambda : 
		have lambda function poll for messages from SQS queue
		if issue is found with a message, put it back in the queue and try again
		may cause infinite loop of retrying, polling, putting it back
		so to overcome, use a Dead Letter Queue DLQ for messages with issues, which is setup at the SQS side
		![[Pasted image 20230522115210.png]]
2. SQS FIFO and Lambda : 
		message processing in order 
		Lambda polls for messages from the SQS queue
		if issue is found, the message cannot be put back as the order needs to be maintained, so there is a retry blockage
		to overcome this, use a DLQ, setup at the SQS side
		![[Pasted image 20230522115330.png]]
3. SNS and Lambda : 
		no polling as this is SNS
		the message is sent async to Lambda
		if lambda unable to process the message i.e. issue found, there is internal retry unlike putting it back like SQS
		if internal retry fails for a finite number of times, send it to a DLQ, at lambda level or to a DLQ
		![[Pasted image 20230522115604.png]]
4. Fan Out Pattern : deliver to multiple SQS
		deliver data to multiple SQS
		1. not too reliable : this is a non fan out pattern 
		application failed to send message somewhere, diff SQS queues will have different messages. 
		![[Pasted image 20230522115756.png]]
	2. Reliable : fan out pattern 
		![[Pasted image 20230522115818.png]]
5. S3 Event Notifications
		specific event notifications from S3
		S3:ObjectCreated, S3:ObjectRemoved, S3:ObjectRestore, S3:Replication...  
		Object name filtering possible ( * .jpg)  
		• Use case: generate thumbnails of images uploaded to S3  
		• Can create as many “S3 events” as desired  
		• S3 event notifications typically deliver events in seconds but can sometimes take a minute or longer
		![[Pasted image 20230522120355.png]]
6. S3 Event Notifications with Amazon EventBridge
		Advanced filtering options with JSON rules (metadata, object size, name...)  
		• Multiple Destinations – ex Step Functions, Kinesis Streams / Firehose...  
		• EventBridge Capabilities – Archive, Replay Events, Reliable delivery
		![[Pasted image 20230522120457.png]]
7. Amazon EventBridge - Intercept API Calls
		use and read CloudTrail logs to custom find out events 
		eg. deletion of table etc
		![[Pasted image 20230522120558.png]]
8. External Events capturing - API Gateway 
		![[Pasted image 20230522120649.png]]
	