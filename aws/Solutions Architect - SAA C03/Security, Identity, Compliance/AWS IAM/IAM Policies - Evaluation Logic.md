![[Pasted image 20230517165245.png]]
https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html


-   By default, all requests are implicitly denied with the exception of the AWS account root user, which has full access.
    
-   An explicit allow in an identity-based or resource-based policy overrides this default.
    
-   If a permissions boundary, Organizations SCP, or session policy is present, it might override the allow with an implicit deny.
    
-   An explicit deny in any policy overrides any allows.
