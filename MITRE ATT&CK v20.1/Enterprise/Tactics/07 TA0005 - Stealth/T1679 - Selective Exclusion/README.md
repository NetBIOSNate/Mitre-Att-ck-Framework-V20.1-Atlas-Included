# T1679 - Selective Exclusion

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may intentionally exclude certain files, folders, directories, file types, or system components from encryption or tampering during a ransomware or malicious payload execution. Some file extensions that adversaries may avoid encrypting include `.dll`, `.exe`, and `.lnk`.(Citation: Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024)  

Adversaries may perform this behavior to avoid alerting users, to evade detection by security tools and analysts, or, in the case of ransomware, to ensure that the system remains operational enough to deliver the ransom notice. 

Exclusions may target files and components whose corruption would cause instability, break core services, or immediately expose the attack. By carefully avoiding these areas, adversaries maintain system responsiveness while minimizing indicators that could trigger alarms or otherwise inhibit achieving their goals.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1679)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S9038 - DynoWiper](../../../Threat%20Intelligence/Software/Malware/S9038%20-%20DynoWiper.md) — [DynoWiper](https://attack.mitre.org/software/S9038) has recursively enumerated directories with the exception of the following: System32, Windows, Program Files, Program Files(x86), Temp, Recycle.Bin, $Recycle.Bin, Boot, PerfLogs, AppData, Documents and Settings.(Citation: CERT Polska)(Citation: ESET DynoWiper Update JAN 2026) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf) · [ESET DynoWiper Update JAN 2026](https://www.welivesecurity.com/en/eset-research/dynowiper-update-technical-analysis-attribution/)
- [S1247 - Embargo](../../../Threat%20Intelligence/Software/Malware/S1247%20-%20Embargo.md) — [Embargo](https://attack.mitre.org/software/S1247) has avoided encrypting specific files and directories by leveraging a regular expression within the ransomware binary.(Citation: Cyble Embargo Ransomware May 2024) [Cyble Embargo Ransomware May 2024](https://cyble.com/blog/the-rust-revolution-new-embargo-ransomware-steps-in/)
- [S1245 - InvisibleFerret](../../../Threat%20Intelligence/Software/Malware/S1245%20-%20InvisibleFerret.md) — [InvisibleFerret](https://attack.mitre.org/software/S1245) has the capability to scan for file names, file extensions, and avoids pre-designated path names and file types.(Citation: Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024)(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023) [Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.esentire.com/blog/bored-beavertail-invisibleferret-yacht-club-a-lazarus-lure-pt-2) · [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/)
- [S9039 - LazyWiper](../../../Threat%20Intelligence/Software/Malware/S9039%20-%20LazyWiper.md) — [LazyWiper](https://attack.mitre.org/software/S9039) can enumerate the hostname of the system to determine if it is a domain controller and exclude it from being wiped if so.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S1244 - Medusa Ransomware](../../../Threat%20Intelligence/Software/Malware/S1244%20-%20Medusa%20Ransomware.md) — [Medusa Ransomware](https://attack.mitre.org/software/S1244) has avoided specified files, file extensions and folders to ensure successful execution of the payload and continued operations of the impacted device.(Citation: Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024)(Citation: Broadcom Medusa Ransomware Medusa Group March 2025)(Citation: Security Scorecard Medusa Ransomware January 2024) [Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024](https://unit42.paloaltonetworks.com/medusa-ransomware-escalation-new-leak-site/) · [Broadcom Medusa Ransomware Medusa Group March 2025](https://www.security.com/threat-intelligence/medusa-ransomware-attacks) · [Security Scorecard Medusa Ransomware January 2024](https://securityscorecard.com/wp-content/uploads/2024/01/deep-dive-into-medusa-ransomware.pdf)
- [S9030 - SameCoin](../../../Threat%20Intelligence/Software/Malware/S9030%20-%20SameCoin.md) — [SameCoin](https://attack.mitre.org/software/S9030) can avoid overwriting file names that contain “desktop.ini” and “conf.conf." (Citation: Check Point Wirte NOV 2024) [Check Point Wirte NOV 2024](https://research.checkpoint.com/2024/hamas-affiliated-threat-actor-expands-to-disruptive-activity/)
- [S9051 - The Gentlemen Ransomware](../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has excluded the `C:\` volume from scanning to reduce its likelihood of being detected during the encryption process using the PowerShell cmdlet `Add-MpPreference – ExclusionPath C:\ -Force`.(Citation: MSTI_GentelmenRansomware_May2026) [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has also excluded encryption of specified file names, and file extensions, to include those associated with critical system functionality.(Citation: MSTI_GentelmenRansomware_May2026)(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/) · [MSTI_GentelmenRansomware_May2026](https://www.microsoft.com/en-us/security/blog/2026/05/28/the-gentlemen-ransomware-dissecting-a-self-propagating-go-encryptor/)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has avoided interacting with specific directories in order to reduce the likelihood of detection.(Citation: FBI IC3 Flash VOID MANTICORE Handala Hack March 2026) [FBI IC3 Flash VOID MANTICORE Handala Hack March 2026](https://www.ic3.gov/CSA/2026/260320.pdf)

## Detection strategies

- [DET0897 - Detection of Selective Exclusion](../../../Defenses/Detection%20Strategies/DET0897%20-%20Detection%20of%20Selective%20Exclusion.md)

## Sources

- [Palo Alto Unit 42 Medusa Group Medusa Ransomware January 2024](https://unit42.paloaltonetworks.com/medusa-ransomware-escalation-new-leak-site/)
