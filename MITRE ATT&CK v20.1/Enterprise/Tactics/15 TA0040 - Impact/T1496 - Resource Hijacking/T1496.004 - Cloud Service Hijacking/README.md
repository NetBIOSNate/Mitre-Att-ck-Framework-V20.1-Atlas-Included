# T1496.004 - Cloud Service Hijacking

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1496 - Resource Hijacking](../README.md)

Adversaries may leverage compromised software-as-a-service (SaaS) applications to complete resource-intensive tasks, which may impact hosted service availability. 

For example, adversaries may leverage email and messaging services, such as AWS Simple Email Service (SES), AWS Simple Notification Service (SNS), SendGrid, and Twilio, in order to send large quantities of spam / [Phishing](https://attack.mitre.org/techniques/T1566) emails and SMS messages.(Citation: Invictus IR DangerDev 2024)(Citation: Permiso SES Abuse 2023)(Citation: SentinelLabs SNS Sender 2024) Alternatively, they may engage in LLMJacking by leveraging reverse proxies to hijack the power of cloud-hosted AI models.(Citation: Sysdig LLMJacking 2024)(Citation: Lacework LLMJacking 2024)

In some cases, adversaries may leverage services that the victim is already using. In others, particularly when the service is part of a larger cloud platform, they may first enable the service.(Citation: Sysdig LLMJacking 2024) Leveraging SaaS applications may cause the victim to incur significant financial costs, use up service quotas, and otherwise impact availability.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1496/004)

**Tactics**  [Impact](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Detection strategies

- [DET0147 - Detection Strategy for Cloud Service Hijacking via SaaS Abuse](../../../../Defenses/Detection%20Strategies/DET0147%20-%20Detection%20Strategy%20for%20Cloud%20Service%20Hijacking%20via%20SaaS%20Abuse.md)

## Sources

- [SentinelLabs SNS Sender 2024](https://www.sentinelone.com/labs/sns-sender-active-campaigns-unleash-messaging-spam-through-the-cloud/)
- [Invictus IR DangerDev 2024](https://www.invictus-ir.com/news/the-curious-case-of-dangerdev-protonmail-me)
- [Lacework LLMJacking 2024](https://www.lacework.com/blog/detecting-ai-resource-hijacking-with-composite-alerts)
- [Sysdig LLMJacking 2024](https://sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)
- [Permiso SES Abuse 2023](https://permiso.io/blog/s/aws-ses-pionage-detecting-ses-abuse/)
