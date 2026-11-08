# T1567.004 - Exfiltration Over Webhook

[Enterprise](../../../../README.md) / [Exfiltration](../../README.md) / [T1567 - Exfiltration Over Web Service](../README.md)

Adversaries may exfiltrate data to a webhook endpoint rather than over their primary command and control channel. Webhooks are simple mechanisms for allowing a server to push data over HTTP/S to a client without the need for the client to continuously poll the server.(Citation: RedHat Webhooks) Many public and commercial services, such as Discord, Slack, and `webhook.site`, support the creation of webhook endpoints that can be used by other services, such as Github, Jira, or Trello.(Citation: Discord Intro to Webhooks) When changes happen in the linked services (such as pushing a repository update or modifying a ticket), these services will automatically post the data to the webhook endpoint for use by the consuming application. 

Adversaries may link an adversary-owned environment to a victim-owned SaaS service to achieve repeated [Automated Exfiltration](https://attack.mitre.org/techniques/T1020) of emails, chat messages, and other data.(Citation: Push Security SaaS Attacks Repository Webhooks) Alternatively, instead of linking the webhook endpoint to a service, an adversary can manually post staged data directly to the URL in order to exfiltrate it.(Citation: Microsoft SQL Server)

Access to webhook endpoints is often over HTTPS, which gives the adversary an additional level of protection. Exfiltration leveraging webhooks can also blend in with normal network traffic if the webhook endpoint points to a commonly used SaaS application or collaboration service.(Citation: CyberArk Labs Discord)(Citation: Talos Discord Webhook Abuse)(Citation: Checkmarx Webhooks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1567/004)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries leveraged an attacker-controlled Slack channel to exfiltrate data.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has exfiltrated repository secrets to `webhook[.]site`.(Citation: Wiz Shai-Hulud September 2025) [Wiz Shai-Hulud September 2025](https://www.wiz.io/blog/shai-hulud-npm-supply-chain-attack)

## Detection strategies

- [DET0153 - Detection Strategy for Exfiltration Over Webhook](../../../../Defenses/Detection%20Strategies/DET0153%20-%20Detection%20Strategy%20for%20Exfiltration%20Over%20Webhook.md)

## Mitigations

- [M1057 - Data Loss Prevention](../../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can be detect and block sensitive data being uploaded to web services via web browsers.

## Sources

- [Checkmarx Webhooks](https://medium.com/checkmarx-security/webhook-party-malicious-packages-caught-exfiltrating-data-via-legit-webhook-services-6e046b07d191)
- [CyberArk Labs Discord](https://www.cyberark.com/resources/threat-research-blog/the-not-so-secret-war-on-discord)
- [Discord Intro to Webhooks](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks)
- [Microsoft SQL Server](https://www.microsoft.com/security/blog/2023/10/03/defending-new-vectors-threat-actors-attempt-sql-server-to-cloud-lateral-movement/)
- [Talos Discord Webhook Abuse](https://blog.talosintelligence.com/collab-app-abuse/)
- [Push Security SaaS Attacks Repository Webhooks](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/webhooks/description.md)
- [RedHat Webhooks](https://www.redhat.com/en/topics/automation/what-is-a-webhook)
