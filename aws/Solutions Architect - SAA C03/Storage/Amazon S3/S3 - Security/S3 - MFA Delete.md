![[Pasted image 20230505123855.png]]

the enable option for MFA Delete is currently not possible from AWS Console, need to do it AWS CLI

on IAM however, we already needed to have added an MFA mechanism for this to work.

need to do these : 

### generate root access keys
aws configure --profile root-mfa-delete-demo

### enable mfa delete
aws s3api put-bucket-versioning --bucket mfa-demo-stephane --versioning-configuration Status=Enabled,MFADelete=Enabled --mfa "arn-of-mfa-device mfa-code" --profile root-mfa-delete-demo

### disable mfa delete
aws s3api put-bucket-versioning --bucket mfa-demo-stephane --versioning-configuration Status=Enabled,MFADelete=Disabled --mfa "arn-of-mfa-device mfa-code" --profile root-mfa-delete-demo

### delete the root credentials in the IAM console!!!