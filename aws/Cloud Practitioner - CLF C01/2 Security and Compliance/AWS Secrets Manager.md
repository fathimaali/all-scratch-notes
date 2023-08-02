https://aws.amazon.com/secrets-manager/


![[Pasted image 20230331165308.png]]

Centrally manage the lifecycle of secrets


	Securely encrypt and centrally audit secrets such as database credentials and API keys.

	Manage access to secrets using fine-grained AWS Identity and Access Management (IAM) and resource-based policies.

	Rotate secrets automatically to meet your security and compliance requirements.

	Replicate secrets to support disaster recovery scenarios and multi-region applications.

## How it works

AWS Secrets Manager helps you manage, retrieve, and rotate database credentials, API keys, and other secrets throughout their lifecycles.

![Diagram showing how AWS Secrets Manager integrates with other AWS services to securely store, access, rotate, and monitor the use of your secrets.](https://d1.awsstatic.com/diagrams/Secrets-HIW.e84b6533ffb6bd688dad66cfca36622c2fa7c984.png)


## Use cases

### Store secrets securely

	Centrally store and manage credentials, API keys, and other secrets.

### Manage access with fine-grained policies

	Use AWS Identity and Access Management (IAM) permissions policies to manage access to your secrets.
	
### Automate secrets rotation

	Rotate secrets on demand or on a schedule, without redeploying or disrupting active applications.

### Audit and monitor secrets usage

		Integrate secrets with AWS logging, monitoring, and notification services.