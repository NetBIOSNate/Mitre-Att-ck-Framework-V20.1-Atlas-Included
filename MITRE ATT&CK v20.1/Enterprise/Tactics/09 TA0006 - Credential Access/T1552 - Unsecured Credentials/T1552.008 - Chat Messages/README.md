# T1552.008 - Chat Messages

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may directly collect unsecured credentials stored or passed through user communication services. Credentials may be sent and stored in user chat communication applications such as email, chat services like Slack or Teams, collaboration tools like Jira or Trello, and any other services that support user communication. Users may share various forms of credentials (such as usernames and passwords, API keys, or authentication tokens) on private or public corporate internal communications channels.

Rather than accessing the stored chat logs (i.e., [Credentials In Files](https://attack.mitre.org/techniques/T1552/001)), adversaries may directly access credentials within these services on the user endpoint, through servers hosting the services, or through administrator portals for cloud hosted services. Adversaries may also compromise integration tools like Slack Workflows to automatically search through messages to extract user credentials. These credentials may then be abused to perform follow-on activities such as lateral movement or privilege escalation.(Citation: Slack Security Risks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/008)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Detection strategies

- [DET0111 - Detect Unsecured Credentials Shared in Chat Messages](../../../../Defenses/Detection%20Strategies/DET0111%20-%20Detect%20Unsecured%20Credentials%20Shared%20in%20Chat%20Messages.md)

## Procedure examples

- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has targeted various collaboration tools like Slack, Teams, JIRA, Confluence, and others to hunt for exposed credentials to support privilege escalation and lateral movement.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Preemptively search through communication services to find shared unsecured credentials. Searching for common patterns like "<code>password is </code>", “<code>password=</code>” and take actions to reduce exposure when found.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Ensure that developers and system administrators are aware of the risk associated with sharing unsecured passwords across communication services.

## Sources

- [Slack Security Risks](https://www.nightfall.ai/blog/saas-slack-security-risks-2020)
