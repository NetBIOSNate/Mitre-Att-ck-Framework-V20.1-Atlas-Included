# T1684 - Social Engineering

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may use social engineering techniques to influence users to take actions that result in unauthorized access, approval of changes, disclosure of sensitive information, or execution of adversary-supplied instructions (i.e., introduction of malicious payloads or software), while minimizing technical indicators. 

Adversaries may leverage trust-building methods across multiple channels (e.g., executive, vendor, or help desk scenarios, including AI-enabled voice interactions) to prompt user-authorized actions such as password resets, MFA changes, financial approvals, or the disclosure of sensitive information. Adversaries may also leverage common business communications and workflows such as email, collaboration platforms, voice communications, recruiting processes, help desk interactions, and SaaS consent mechanisms to make malicious requests appear routine and legitimate.(Citation: Proofpoint TA427 April 2024)(Citation: SE SentinelOne 2)(Citation: SE - Hackers Target Workday)

Additionally, adversaries have persuaded victims to take actions through references of current events, harnessing relevant themes to the work role or the organizations mission. For example, adversaries may use scare tactics (i.e., threaten repercussions for non-compliance) or otherwise incite victims’ emotions in order to generate a sense of urgency to take action.(Citation: SE Proofpoint)(Citation: SE SentinelOne)

This technique may include common social engineering patterns such as [Phishing](https://attack.mitre.org/techniques/T1566) and [Spearphishing Voice](https://attack.mitre.org/techniques/T1566/004), often supported by convincing and targeted narratives.(Citation: SE SentinelOne 2)(Citation: Fortinet Trends 25-26)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1684)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1684.002 - Email Spoofing](T1684.002%20-%20Email%20Spoofing/README.md)
- [T1684.001 - Impersonation](T1684.001%20-%20Impersonation/README.md)

## Mitigations

- [M1036 - Account Use Policies](../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Adds verification for helpdesk resets, approvals, and app consents commonly targeted by impersonation.(Citation: SE SentinelOne 2)(Citation: SE - Hackers Target Workday) [SE - Hackers Target Workday](https://www.cybersecuritydive.com/news/hackers-target-workday-in-social-engineering-attack/758095/#:~:text=Researchers%20cite%20increasing%20evidence%20of,told%20Cybersecurity%20Dive%20via%20email.) · [SE SentinelOne 2](https://www.sentinelone.com/cybersecurity-101/threat-intelligence/types-of-social-engineering-attacks/)
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Enables correlation of email/identity/SaaS/endpoint activity that appears legitimate.(Citation: Proofpoint TA427 April 2024)(Citation: Unit 42 Global Incident Response Report 2026) [Proofpoint TA427 April 2024](https://www.proofpoint.com/us/blog/threat-insight/social-engineering-dmarc-abuse-ta427s-art-information-gathering) · [Unit 42 Global Incident Response Report 2026](https://www.paloaltonetworks.com/resources/research/unit-42-incident-response-report#:~:text=The%20Browser%20Attack%20Surface:%20Attacks%20at%20the%20Human%20Interface&text=The%20site%20used%20social-engineering,deployment%20and%20broader%20operational%20disruption)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Reduces success of phishing/vishing/impersonation and modern “human interface” lures.(Citation: SE SentinelOne 2)(Citation: Sophos User Interaction)(Citation: Unit 42 Global Incident Response Report 2026) [Sophos User Interaction](https://www.sophos.com/en-us/blog/evil-evolution-clickfix-and-macos-infostealers) · [Unit 42 Global Incident Response Report 2026](https://www.paloaltonetworks.com/resources/research/unit-42-incident-response-report#:~:text=The%20Browser%20Attack%20Surface:%20Attacks%20at%20the%20Human%20Interface&text=The%20site%20used%20social-engineering,deployment%20and%20broader%20operational%20disruption) · [SE SentinelOne 2](https://www.sentinelone.com/cybersecurity-101/threat-intelligence/types-of-social-engineering-attacks/)

## Procedure examples

- [G1057 - ShinyHunters](../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used social engineering to demand payment from victims.(Citation: FBI_SHLMS_May2026) [FBI_SHLMS_May2026](https://www.ic3.gov/PSA/2026/PSA260515)

## Detection strategies

- [DET0899 - Detect Social Engineering](../../../Defenses/Detection%20Strategies/DET0899%20-%20Detect%20Social%20Engineering.md)

## Sources

- [SE - Hackers Target Workday](https://www.cybersecuritydive.com/news/hackers-target-workday-in-social-engineering-attack/758095/#:~:text=Researchers%20cite%20increasing%20evidence%20of,told%20Cybersecurity%20Dive%20via%20email.)
- [Fortinet Trends 25-26](https://www.fortinet.com/uk/resources/cyberglossary/recent-cyber-attacks)
- [Proofpoint TA427 April 2024](https://www.proofpoint.com/us/blog/threat-insight/social-engineering-dmarc-abuse-ta427s-art-information-gathering)
- [SE Proofpoint](https://www.proofpoint.com/us/threat-reference/social-engineering)
- [SE SentinelOne](https://www.sentinelone.com/blog/social-engineering-attacks-how-to-recognize-and-resist-the-bait/)
- [SE SentinelOne 2](https://www.sentinelone.com/cybersecurity-101/threat-intelligence/types-of-social-engineering-attacks/)
