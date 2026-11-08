# T1685.002 - Disable or Modify Cloud Log

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

An adversary may disable or modify cloud logging capabilities and integrations to limit what data is collected on their activities and avoid detection. Cloud environments allow for collection and analysis of audit and application logs that provide insight into what activities a user does within the environment. If an adversary has sufficient permissions, they can disable or modify logging to avoid detection of their activities. 

For example, in AWS an adversary may disable CloudWatch/CloudTrail integrations prior to conducting further malicious activity. They may alternatively tamper with logging functionality, for example, by removing any associated SNS topics, disabling multi-region logging, or disabling settings that validate and/or encrypt log files.(Citation: AWS Cloud Trail)(Citation: Pacu Detection Disruption Module) In Office 365, an adversary may disable logging on mail collection activities for specific users by using the Set-MailboxAuditBypassAssociation cmdlet, by disabling M365 Advanced Auditing for the user, or by downgrading the user’s license from an Enterprise E5 to an Enterprise E3 license.(Citation: Dark Reading)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/002)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [SaaS](../../../../Platforms/SaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has disabled Purview Audit on targeted accounts prior to stealing emails from Microsoft 365 tenants.(Citation: Mandiant APT29 Microsoft 365 2022) [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft)
- [S1091 - Pacu](../../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can disable or otherwise restrict various AWS logging services, such as AWS CloudTrail and VPC flow logs.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)

## Mitigations

- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Configure default account policy to enable logging. Manage policies to ensure only necessary users have permissions to make changes to logging policies.

## Detection strategies

- [DET0289 - Detection Strategy for Disable or Modify Cloud Log](../../../../Defenses/Detection%20Strategies/DET0289%20-%20Detection%20Strategy%20for%20Disable%20or%20Modify%20Cloud%20Log.md)

## Sources

- [AWS Cloud Trail](https://docs.aws.amazon.com/cli/latest/reference/cloudtrail/update-trail.html)
- [Dark Reading](https://www.darkreading.com/threat-intelligence/incident-responders-explore-microsoft-365-attacks-in-the-wild)
- [Pacu Detection Disruption Module](https://github.com/RhinoSecurityLabs/pacu/blob/master/pacu/modules/detection__disruption/main.py)
