# T1681 - Search Threat Vendor Data

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Threat actors may seek information/indicators from closed or open threat intelligence sources gathered about their own campaigns, as well as those conducted by other adversaries that may align with their target industries, capabilities/objectives, or other operational concerns. These reports may include descriptions of behavior, detailed breakdowns of attacks, atomic indicators such as malware hashes or IP addresses, timelines of a group’s activity, and more. Adversaries may change their behavior when planning their future operations. 

Adversaries have been observed replacing atomic indicators mentioned in blog posts in under a week.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023) Adversaries have also been seen searching for their own domain names in threat vendor data and then taking them down, likely to avoid seizure or further investigation.(Citation: Sentinel One Contagious Interview ClickFix September 2025)

This technique is distinct from [Threat Intel Vendors](https://attack.mitre.org/techniques/T1597/001) in that it describes threat actors performing reconnaissance on their own activity, not in search of victim information.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1681)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has registered accounts with Threat Intelligence vendor services to check for reporting associated with their infrastructure and to evaluate new potential infrastructure.(Citation: Sentinel One Contagious Interview ClickFix September 2025) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/)
- [G1048 - UNC3886](../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has replaced indicators mentioned in open-source threat intelligence publications at times under a week after their release.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023) [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)

## Detection strategies

- [DET0866 - Detection of Search Threat Vendor Data](../../../Defenses/Detection%20Strategies/DET0866%20-%20Detection%20of%20Search%20Threat%20Vendor%20Data.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on designing defenses that are not reliant on atomic indicators.

## Sources

- [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/)
- [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)
