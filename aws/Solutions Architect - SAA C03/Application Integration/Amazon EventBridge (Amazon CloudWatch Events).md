[[Cloud Practitioner - CLF C01/3 Technology/Monitoring/Amazon EventBridge (Amazon CloudWatch Events)]]  

Event Bus 
		default bus
		custom bus 
		event routing 
		event archive 
		cross account or cross region support
Events Archive 
SendBox : test events
Events Rules : rules to catch events from which arn 
Event Targets : where to send events notifications
Event Replays : can replay what was archived earlier
Events Schema Registry : A schema defines the structure and format of the data that is included in an event. supports mutile languages to help us edit
		schema validation : validate events against a schema
		schema discovery : discover schema for events 
		schema versioning : make changes without affecting existing events
		schema sharing : share with other AWS accounts
		schema evolution : evolve but still backward compatible

![[Pasted image 20230516114412.png]]

![[Pasted image 20230516114509.png]]

![[Pasted image 20230516114604.png]]

cross account events aggregatoin with resource-based policies
: enable events to be aggregated by just mentioning the ARN

![[Pasted image 20230516114650.png]]

