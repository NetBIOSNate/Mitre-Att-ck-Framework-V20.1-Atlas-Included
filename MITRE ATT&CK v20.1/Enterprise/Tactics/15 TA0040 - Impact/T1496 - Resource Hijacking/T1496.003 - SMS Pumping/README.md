# T1496.003 - SMS Pumping

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1496 - Resource Hijacking](../README.md)

Adversaries may leverage messaging services for SMS pumping, which may impact system and/or hosted service availability.(Citation: Twilio SMS Pumping) SMS pumping is a type of telecommunications fraud whereby a threat actor first obtains a set of phone numbers from a telecommunications provider, then leverages a victim’s messaging infrastructure to send large amounts of SMS messages to numbers in that set. By generating SMS traffic to their phone number set, a threat actor may earn payments from the telecommunications provider.(Citation: Twilio SMS Pumping Fraud)

Threat actors often use publicly available web forms, such as one-time password (OTP) or account verification fields, in order to generate SMS traffic. These fields may leverage services such as Twilio, AWS SNS, and Amazon Cognito in the background.(Citation: Twilio SMS Pumping)(Citation: AWS RE:Inforce Threat Detection 2024) In response to the large quantity of requests, SMS costs may increase and communication channels may become overwhelmed.(Citation: Twilio SMS Pumping)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1496/003)

**Tactics**  [Impact](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Consider implementing CAPTCHA protection on forms that send messages via SMS.

## Detection strategies

- [DET0156 - Detection Strategy for Resource Hijacking: SMS Pumping via SaaS Application Logs](../../../../Defenses/Detection%20Strategies/DET0156%20-%20Detection%20Strategy%20for%20Resource%20Hijacking%20-%20SMS%20Pumping%20via%20SaaS%20Application%20Logs.md)

## Sources

- [AWS RE:Inforce Threat Detection 2024](https://reinforce.awsevents.com/content/dam/reinforce/2024/slides/TDR432_New-tactics-and-techniques-for-proactive-threat-detection.pdf)
- [Twilio SMS Pumping](https://www.twilio.com/en-us/blog/sms-pumping-fraud-solutions)
- [Twilio SMS Pumping Fraud](https://www.twilio.com/docs/glossary/what-is-sms-pumping-fraud)
