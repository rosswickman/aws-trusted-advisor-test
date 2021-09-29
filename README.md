# aws-trusted-advisor-test
Just testing something with AWS Trusted Advisor

These access tokens won't work.
Just seeing if I can get alarms to trigger for `Exposed Access Keys` Trusted Advisor Check

## Key Info

Use this:

Access key ID - `AKIAXSWPYG26Q46DMVV6`

With this:

Secret access key - `+s32O7HQyZkkXN9Pe/ukI3vRNEChDXR3LPBTVTx2`

## Result

Received two emails from AWS in less than 5 Minutes (14:32CDT) of the [README.md](README.md) in this project being commited (14:27CDT).

### Email 1

![email1](images/Email1.png)

### Email 2

![email2](images/Email2.png)

### Permissions Policy Attachment

**Update 1** - Later noticed that my user had applied to it an AWS Managed Policy `AWSCompromisedKeyQuarantineV2` which had the attached deny permissions in the [AttahcedPolicy.json](resources/AttachedPolicy.json)

![AttachedPolicy](images/AttachedPolicy.png)

## Remediation

In order to send notifications of `Exposed Access Keys` to more than one individual or the account root email in question you can create CloudWatch Alarms to trigger desired actions.

I've created a template [ta-alarms.template.yml](resources/ta-alarms.template.yml) for very basic setup that requires and SNS Topic with some subscription.

> **Important** This level of `Trusted Advisor` _check_ requires your account be on the _Business_ Support Tier or higher.

![aws_support_plans](images/AWS_Support_Plans.png)

### Compliance Notification

**Update 2** - After deleting the Credentails but leaving my `trusted-advisor-test` IAM User in place, I was notified and _thanked_ by AWS for removing the credentials from the user account. 

![Email3](images/Email3.png)

**Update 3** - The following the initial event, AWS sent another email confirming I completed the required steps to fix the problem as well as provided additional resources for review.

![Email4](images/AWS_Followup.png)

## Successful Notification & Configuration (28Sept21)

**Update 4** - After getting to test in an account with `Enterprise` Support and other CloudWatch Alarms configured, there was a successful notificaiton for the CloudWatch Alarm created for the Trusted Advisor Exposed IAM Access Keys.

### Initial CloudWatch Alarms

![Triggered_Alarms](images/Triggered_Alarm.png)

### Initial CloudWatch Alarms

![CW_Alarms](images/Initial_CW_Alarms.png)

### Trusted Advisor AWS Console

![Trusted_Advisor](images/Trusted_Advisor.png)

### CIS IAM Key Created Alarm Email

![Email5](images/Email-Alarm_CIS.png)

### Explosed Access Keys Alarm Email

![Email6](images/Email-Alarm_Exposed_Keys.png)

### CIS IAM Key Created OK Email

![Email7](images/Email-OK_CIS_Check.png)

### Exposed Key Created OK Email

![Email8](images/Email-OK_IAM_Key_Created.png)


## Conclusion

Testing completed for this process and implementation 29-Sept-21
