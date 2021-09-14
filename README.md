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

##Update 3** - The following the initial event, AWS sent another email confirming I completed the required steps to fix the problem as well as provided additional resources for review.

![Email4](images/AWS_Followup.png)
