# T1566.004 - Spearphishing Voice

[Enterprise](../../../../README.md) / [Initial Access](../../README.md) / [T1566 - Phishing](../README.md)

Adversaries may use voice communications to ultimately gain access to victim systems. Spearphishing voice is a specific variant of spearphishing. It is different from other forms of spearphishing in that it employs the use of manipulating a user into providing access to systems through a phone call or other forms of voice communications. Spearphishing frequently involves social engineering techniques, such as posing as a trusted source (ex: [Impersonation](https://attack.mitre.org/techniques/T1684/001)) and/or creating a sense of urgency or alarm for the recipient.

All forms of phishing are electronically delivered social engineering. In this scenario, adversaries are not directly sending malware to a victim vice relying on [User Execution](https://attack.mitre.org/techniques/T1204) for delivery and execution. For example, victims may receive phishing messages that instruct them to call a phone number where they are directed to visit a malicious URL, download malware,(Citation: sygnia Luna Month)(Citation: CISA Remote Monitoring and Management Software) or install adversary-accessible remote management tools ([Remote Access Tools](https://attack.mitre.org/techniques/T1219)) onto their computer.(Citation: Unit42 Luna Moth)

Adversaries may also combine voice phishing with [Multi-Factor Authentication Request Generation](https://attack.mitre.org/techniques/T1621) in order to trick users into divulging MFA credentials or accepting authentication prompts.(Citation: Proofpoint Vishing)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1566/004)

**Tactics**  [Initial Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Mitigations

- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify and report social engineering techniques and spearphishing attempts, while also being suspicious of and verifying the identify of callers.(Citation: CISA Phishing) [CISA Phishing](https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks)

## Detection strategies

- [DET0245 - Detection Strategy for Spearphishing Voice across OS platforms](../../../../Defenses/Detection%20Strategies/DET0245%20-%20Detection%20Strategy%20for%20Spearphishing%20Voice%20across%20OS%20platforms.md)

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) impersonated legitimate IT personnel in phone calls to direct victims to download a remote monitoring and management (RMM) tool that would allow the adversary to remotely control their system.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1046 - Storm-1811](../../../../Threat%20Intelligence/Groups/G1046%20-%20Storm-1811.md) — [Storm-1811](https://attack.mitre.org/groups/G1046) has initiated voice calls with victims posing as IT support to prompt users to download and execute scripts and other tools for initial access.(Citation: Microsoft Storm-1811 2024)(Citation: rapid7-email-bombing)(Citation: RedCanary Storm-1811 2024) [Microsoft Storm-1811 2024](https://www.microsoft.com/en-us/security/blog/2024/05/15/threat-actors-misusing-quick-assist-in-social-engineering-attacks-leading-to-ransomware/) · [RedCanary Storm-1811 2024](https://redcanary.com/blog/threat-intelligence/storm-1811-black-basta/) · [rapid7-email-bombing](https://www.rapid7.com/blog/post/2024/05/10/ongoing-social-engineering-campaign-linked-to-black-basta-ransomware-operators)

## Sources

- [CISA Remote Monitoring and Management Software](https://www.cisa.gov/uscert/ncas/alerts/aa23-025a)
- [Unit42 Luna Moth](https://unit42.paloaltonetworks.com/luna-moth-callback-phishing/)
- [sygnia Luna Month](https://blog.sygnia.co/luna-moth-false-subscription-scams)
- [Proofpoint Vishing](https://www.proofpoint.com/us/threat-reference/vishing)
