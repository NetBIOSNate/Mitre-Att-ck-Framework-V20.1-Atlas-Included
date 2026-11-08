# G1015 - Scattered Spider

[Mobile](../../README.md) / [Groups](README.md)

[Scattered Spider](https://attack.mitre.org/groups/G1015) is a native English-speaking cybercriminal group active since at least 2022. (Citation: CrowdStrike Scattered Spider Profile) (Citation: MSTIC Octo Tempest Operations October 2023) The group initially targeted customer relationship management (CRM) providers, business process outsourcing (BPO) firms, and telecommunications and technology companies before expanding in 2023 to gaming, hospitality, retail, managed service provider (MSP), manufacturing, and financial sectors. (Citation: MSTIC Octo Tempest Operations October 2023)
[Scattered Spider](https://attack.mitre.org/groups/G1015) relies heavily on social engineering, including impersonating IT and help-desk staff, to gain initial access, bypass multi-factor authentication (MFA), and compromise enterprise networks. The group has adapted its tooling to evade endpoint detection and response (EDR) defenses and used ransomware for financial gain. (Citation: CISA Scattered Spider Advisory November 2023) (Citation: CrowdStrike Scattered Spider BYOVD January 2023) (Citation: Crowdstrike TELCO BPO Campaign December 2022)
[Scattered Spider](https://attack.mitre.org/groups/G1015) had expanded into hybrid cloud and identity environments, using help-desk impersonation and MFA bypass to obtain administrator access in Okta, AWS, and Office 365. (Citation: Mandiant UNC3944 May 2025)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1015)

## Aliases

- Roasted 0ktapus
- Octo Tempest
- Storm-0875
- UNC3944

## Techniques used

- [T1660 - Phishing](../../Tactics/01%20TA0027%20-%20Initial%20Access/T1660%20-%20Phishing/README.md)
- [T1451 - SIM Card Swap](../../Tactics/01%20TA0027%20-%20Initial%20Access/T1451%20-%20SIM%20Card%20Swap/README.md)

## Sources

- [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [CrowdStrike Scattered Spider BYOVD January 2023](https://www.crowdstrike.com/blog/scattered-spider-attempts-to-avoid-detection-with-bring-your-own-vulnerable-driver-tactic/)
- [CrowdStrike Scattered Spider Profile](https://www.crowdstrike.com/adversaries/scattered-spider/)
- [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [Mandiant UNC3944 May 2025](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations)
- [Microsoft Threat Actor Naming July 2023](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide)
- [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
