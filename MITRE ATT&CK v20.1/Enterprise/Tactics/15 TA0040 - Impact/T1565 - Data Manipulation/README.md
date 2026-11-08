# T1565 - Data Manipulation

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may insert, delete, or manipulate data in order to influence external outcomes or hide activity, thus threatening the integrity of the data.(Citation: Sygnia Elephant Beetle Jan 2022) By manipulating data, adversaries may attempt to affect a business process, organizational understanding, or decision making.

The type of modification and the impact it will have depends on the target application and process as well as the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system that would typically be gained through a prolonged information gathering campaign in order to have the desired impact.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1565)

**Tactics**  [Impact](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1565.003 - Runtime Data Manipulation](T1565.003%20-%20Runtime%20Data%20Manipulation/README.md)
- [T1565.001 - Stored Data Manipulation](T1565.001%20-%20Stored%20Data%20Manipulation/README.md)
- [T1565.002 - Transmitted Data Manipulation](T1565.002%20-%20Transmitted%20Data%20Manipulation/README.md)

## Procedure examples

- [G1016 - FIN13](../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has injected fraudulent transactions into compromised networks that mimic legitimate behavior to siphon off incremental amounts of money.(Citation: Sygnia Elephant Beetle Jan 2022) [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
- [S9014 - PHASEJAM](../../../Threat%20Intelligence/Software/Malware/S9014%20-%20PHASEJAM.md) — [PHASEJAM](https://attack.mitre.org/software/S9014) has blocked legitimate upgrades of Ivanti Connect Secure systems and falsely indicates a successful upgrade while operating on an older version.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Consider encrypting important information to reduce an adversary’s ability to perform tailored data modifications.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Identify critical business and system processes that may be targeted by adversaries and work to isolate and secure those systems against unauthorized access and tampering.
- [M1029 - Remote Data Storage](../../../Defenses/Mitigations/M1029%20-%20Remote%20Data%20Storage.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and manipulate backups. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure least privilege principles are applied to important information resources to reduce exposure to data manipulation risk.

## Detection strategies

- [DET0059 - Detection Strategy for Data Manipulation](../../../Defenses/Detection%20Strategies/DET0059%20-%20Detection%20Strategy%20for%20Data%20Manipulation.md)

## Sources

- [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
