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

### Permissions Policy

**Update 1** - Later noticed that my user had applied to it an AWS Managed Policy `AWSCompromisedKeyQuarantineV2` which had the attached deny permissions in the [AttahcedPolicy](resources/AttachedPolicy.json)

![AttachedPolicy](images/AttachedPolicy.png)
