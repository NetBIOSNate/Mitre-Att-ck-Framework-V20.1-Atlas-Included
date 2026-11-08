# T1021.007 - Cloud Services

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1021 - Remote Services](../README.md)

Adversaries may log into accessible cloud services within a compromised environment using [Valid Accounts](https://attack.mitre.org/techniques/T1078) that are synchronized with or federated to on-premises user identities. The adversary may then perform management actions or access cloud-hosted resources as the logged-on user. 

Many enterprises federate centrally managed user identities to cloud services, allowing users to log in with their domain credentials in order to access the cloud control plane. Similarly, adversaries may connect to available cloud services through the web console or through the cloud command line interface (CLI) (e.g., [Cloud API](https://attack.mitre.org/techniques/T1059/009)), using commands such as <code>Connect-AZAccount</code> for Azure PowerShell, <code>Connect-MgGraph</code> for Microsoft Graph PowerShell, and <code>gcloud auth login</code> for the Google Cloud CLI.

In some cases, adversaries may be able to authenticate to these services via [Application Access Token](https://attack.mitre.org/techniques/T1550/001) instead of a username and password.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1021/007)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has leveraged compromised high-privileged on-premises accounts synced to Office 365 to move laterally into a cloud environment, including through the use of Azure AD PowerShell.(Citation: Mandiant Remediation and Hardening Strategies for Microsoft 365) [Mandiant Remediation and Hardening Strategies for Microsoft 365](https://www.mandiant.com/sites/default/files/2022-08/remediation-hardening-strategies-for-m365-defend-against-apt29-white-paper.pdf)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) used compromised Azure credentials for credential theft activity and lateral movement to on-premises systems.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has accessed and propagated to AWS EC2 instances via SSM Send-Command.(Citation: Phoenix TeamPCP 20 MAY 2026) [Phoenix TeamPCP 20 MAY 2026](https://phoenix.security/teampcp-github-breach-durabletask-pypi-supply-chain-wave-four-2026/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has also leveraged pre-existing AWS EC2 instances for lateral movement and data collection purposes.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has used compromised Entra Connect Sync Server to move laterally within the victim environment.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication on cloud services whenever possible.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the number of high-privileged domain and cloud accounts, and ensure that these are not used for day-to-day operations. Ensure that on-premises accounts do not have privileged cloud permissions and that isolated, cloud-only accounts are used for managing cloud environments.(Citation: Protecting Microsoft 365 From On-Premises Attacks) [Protecting Microsoft 365 From On-Premises Attacks](https://learn.microsoft.com/en-us/azure/active-directory/fundamentals/protect-m365-from-on-premises-attacks)

## Detection strategies

- [DET0008 - Behavioral Detection of Remote Cloud Logins via Valid Accounts](../../../../Defenses/Detection%20Strategies/DET0008%20-%20Behavioral%20Detection%20of%20Remote%20Cloud%20Logins%20via%20Valid%20Accounts.md)
