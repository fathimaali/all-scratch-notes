formerly known as CloudWatch Events. 

https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-what-is.html 

can be used for : 
	Scheduling CRON jobs, eg. do something in a periodic interval.  EventBridgeScheduler.
	Reacting event : react to another event. 

![[Pasted image 20230516114257.png]]


![[Pasted image 20230331123117.png]]

Three types of Event Bus
	AWS services - Default Event Bus
	AWS SaaS External partners / systems - Partner Event Bus
	Custom Apps - Custom Event Bus

Schema Registry - model event schema
Archive the Event Bus and Replaying the events also possible. 

Create Rule to schedule jobs, React to any event.

