# T1654 - Log Enumeration

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may enumerate system and service logs to find useful data. These logs may highlight various types of valuable insights for an adversary, such as user authentication records ([Account Discovery](https://attack.mitre.org/techniques/T1087)), security or vulnerable software ([Software Discovery](https://attack.mitre.org/techniques/T1518)), or hosts within a compromised network ([Remote System Discovery](https://attack.mitre.org/techniques/T1018)).

Host binaries may be leveraged to collect system logs. Examples include using `wevtutil.exe` or [PowerShell](https://attack.mitre.org/techniques/T1059/001) on Windows to access and/or export security event information.(Citation: WithSecure Lazarus-NoPineapple Threat Intel Report 2023)(Citation: Cadet Blizzard emerges as novel threat actor) In cloud environments, adversaries may leverage utilities such as the Azure VM Agent’s `CollectGuestLogs.exe` to collect security logs from cloud hosted infrastructure.(Citation: SIM Swapping and Abuse of the Microsoft Azure Serial Console)

Adversaries may also target centralized logging infrastructure such as SIEMs. Logs may also be bulk exported and sent to adversary-controlled infrastructure for offline analysis.

In addition to gaining a better understanding of the environment, adversaries may also monitor logs in real time to track incident response procedures. This may allow them to adjust their techniques in order to maintain persistence or evade defenses.(Citation: Permiso GUI-Vil 2023)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1654)

**Tactics**  [Discovery](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S1194 - Akira _v2](../../../Threat%20Intelligence/Software/Malware/S1194%20-%20Akira%20_v2.md) — [Akira _v2](https://attack.mitre.org/software/S1194) can enumerate the trace, debug, error, info, and warning logs on targeted systems.(Citation: Cisco Akira Ransomware OCT 2024)(Citation: Palo Alto Howling Scorpius DEC 2024) [Cisco Akira Ransomware OCT 2024](https://blog.talosintelligence.com/akira-ransomware-continues-to-evolve/) · [Palo Alto Howling Scorpius DEC 2024](https://unit42.paloaltonetworks.com/threat-assessment-howling-scorpius-akira-ransomware/)
- [G1023 - APT5](../../../Threat%20Intelligence/Groups/G1023%20-%20APT5.md) — [APT5](https://attack.mitre.org/groups/G1023) has used the BLOODMINE utility to parse and extract information from Pulse Secure Connect logs.(Citation: Mandiant Pulse Secure Update May 2021) [Mandiant Pulse Secure Update May 2021](https://www.mandiant.com/resources/blog/updates-on-chinese-apt-compromising-pulse-secure-vpn-devices)
- [G0143 - Aquatic Panda](../../../Threat%20Intelligence/Groups/G0143%20-%20Aquatic%20Panda.md) — [Aquatic Panda](https://attack.mitre.org/groups/G0143) enumerated logs related to authentication in Linux environments prior to deleting selective entries for defense evasion purposes.(Citation: Crowdstrike HuntReport 2022) [Crowdstrike HuntReport 2022](https://go.crowdstrike.com/rs/281-OBQ-266/images/2022OverWatchThreatHuntingReport.pdf)
- [S1246 - BeaverTail](../../../Threat%20Intelligence/Software/Malware/S1246%20-%20BeaverTail.md) — [BeaverTail](https://attack.mitre.org/software/S1246) has identified .ldb and .log files stored in browser extension directories for collection and exfiltration.(Citation: ESET Contagious Interview BeaverTail InvisibleFerret February 2025) [ESET Contagious Interview BeaverTail InvisibleFerret February 2025](https://www.welivesecurity.com/en/eset-research/deceptivedevelopment-targets-freelance-developers/)
- [S1159 - DUSTTRAP](../../../Threat%20Intelligence/Software/Malware/S1159%20-%20DUSTTRAP.md) — [DUSTTRAP](https://attack.mitre.org/software/S1159) can identify infected system log information.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [G1003 - Ember Bear](../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) has enumerated SECURITY and SYSTEM log files during intrusions.(Citation: CISA GRU29155 2024) [CISA GRU29155 2024](https://www.cisa.gov/sites/default/files/2024-09/aa24-249a-russian-military-cyber-actors-target-us-and-global-critical-infrastructure.pdf)
- [S1191 - Megazord](../../../Threat%20Intelligence/Software/Malware/S1191%20-%20Megazord.md) — [Megazord](https://attack.mitre.org/software/S1191) has the ability to print the trace, debug, error, info, and warning logs.(Citation: Palo Alto Howling Scorpius DEC 2024) [Palo Alto Howling Scorpius DEC 2024](https://unit42.paloaltonetworks.com/threat-assessment-howling-scorpius-akira-ransomware/)
- [G0129 - Mustang Panda](../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used [Wevtutil](https://attack.mitre.org/software/S0645) to gather Windows Security Event Logs.(Citation: Palo Alto Unit42 STATELY TAURUS TONESHELL September 2023) [Palo Alto Unit42 STATELY TAURUS TONESHELL September 2023](https://unit42.paloaltonetworks.com/stately-taurus-attacks-se-asian-government/)
- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can collect CloudTrail event histories and CloudWatch logs.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used `wevtutil.exe` and the PowerShell command `Get-EventLog security` to enumerate Windows logs to search for successful logons.(Citation: Joint Cybersecurity Advisory Volt Typhoon June 2023)(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf) · [Joint Cybersecurity Advisory Volt Typhoon June 2023](https://media.defense.gov/2023/May/24/2003229517/-1/-1/0/CSA_Living_off_the_Land.PDF)

## Mitigations

- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit the ability to access and export sensitive logs to privileged accounts where possible.

## Detection strategies

- [DET0255 - Detection Strategy for Log Enumeration](../../../Defenses/Detection%20Strategies/DET0255%20-%20Detection%20Strategy%20for%20Log%20Enumeration.md)

## Sources

- [Permiso GUI-Vil 2023](https://permiso.io/blog/s/unmasking-guivil-new-cloud-threat-actor/)
- [SIM Swapping and Abuse of the Microsoft Azure Serial Console](https://www.mandiant.com/resources/blog/sim-swapping-abuse-azure-serial)
- [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [WithSecure Lazarus-NoPineapple Threat Intel Report 2023](https://labs.withsecure.com/content/dam/labs/docs/WithSecure-Lazarus-No-Pineapple-Threat-Intelligence-Report-2023.pdf)
