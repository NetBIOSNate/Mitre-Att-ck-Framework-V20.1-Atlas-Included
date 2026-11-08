# T1070.007 - Clear Network Connection History and Configurations

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1070 - Indicator Removal](../README.md)

Adversaries may clear or remove evidence of malicious network connections in order to clean up traces of their operations. Configuration settings as well as various artifacts that highlight connection history may be created on a system and/or in application logs from behaviors that require network connections, such as [Remote Services](https://attack.mitre.org/techniques/T1021) or [External Remote Services](https://attack.mitre.org/techniques/T1133). Defenders may use these artifacts to monitor or otherwise analyze network connections created by adversaries.

Network connection history may be stored in various locations. For example, RDP connection history may be stored in Windows Registry values under:

* <code>HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Default</code>(Citation: Microsoft RDP Removal)
* <code>HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Servers</code>(Citation: Microsoft RDP Removal)

Windows may also store information about recent RDP connections in files such as <code>C:\Users\\%username%\Documents\Default.rdp</code> and `C:\Users\%username%\AppData\Local\Microsoft\Terminal
Server Client\Cache\`.(Citation: Moran RDPieces) Similarly, macOS and Linux hosts may store information highlighting connection history in system logs (such as those stored in `/Library/Logs` and/or `/var/log/`).(Citation: Apple Culprit Access)(Citation: FreeDesktop Journal)(Citation: Apple Unified Log Analysis Remote Login and Screen Sharing)

Malicious network connections may also require changes to third-party applications or network configuration settings, such as [Disable or Modify System Firewall](https://attack.mitre.org/techniques/T1686) or tampering to enable [Proxy](https://attack.mitre.org/techniques/T1090). Adversaries may delete or modify this data to conceal indicators and/or impede defensive analysis.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1070/007)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has cleared RDP connection history registry keys to include `HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Default` and ` HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client\Servers`.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [C0056 - RedPenguin](../../../../Threat%20Intelligence/Campaigns/C0056%20-%20RedPenguin.md) — During [RedPenguin](https://attack.mitre.org/campaigns/C0056), [UNC3886](https://attack.mitre.org/groups/G1048) used an implant to delete logs associated with unauthorized access to targeted Junos OS devices.(Citation: Juniper RedPenguin MAR 2025) [Juniper RedPenguin MAR 2025](https://supportportal.juniper.net/sfc/servlet.shepherd/document/download/069Dp00000FzdmIIAR?operationContext=S1)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has reverted or modified network configuration files to remove traces of activity.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [S0559 - SUNBURST](../../../../Threat%20Intelligence/Software/Malware/S0559%20-%20SUNBURST.md) — [SUNBURST](https://attack.mitre.org/software/S0559) also removed the firewall rules it created during execution.(Citation: Microsoft Deep Dive Solorigate January 2021) [Microsoft Deep Dive Solorigate January 2021](https://www.microsoft.com/security/blog/2021/01/20/deep-dive-into-the-solorigate-second-stage-activation-from-sunburst-to-teardrop-and-raindrop/)
- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has removed RDP Logs by leveraging the command `del /f /q %SystemRoot%\System32\LogFiles\RDP*\*\*.*`.(Citation: MSTI_GentelmenRansomware_May2026)(Citation: TrendAI_TheGentlemen_Sept2025)(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/) · [MSTI_GentelmenRansomware_May2026](https://www.microsoft.com/en-us/security/blog/2026/05/28/the-gentlemen-ransomware-dissecting-a-self-propagating-go-encryptor/) · [TrendAI_TheGentlemen_Sept2025](https://www.trendaisecurity.com/en-us/resources-insights/trendai-security-blog/unmasking-the-gentlemen-ransomware)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has cleared specific events that contained the threat actor’s IP address from multiple log sources.(Citation: Mandiant Fortinet Zero Day) [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has inspected server logs to remove their IPs.(Citation: Secureworks BRONZE SILHOUETTE May 2023) [Secureworks BRONZE SILHOUETTE May 2023](https://web.archive.org/web/20230601025540/https://www.secureworks.com/blog/chinese-cyberespionage-group-bronze-silhouette-targets-us-government-and-defense-organizations)

## Detection strategies

- [DET0049 - Behavioral Detection of Network History and Configuration Tampering](../../../../Defenses/Detection%20Strategies/DET0049%20-%20Behavioral%20Detection%20of%20Network%20History%20and%20Configuration%20Tampering.md)

## Mitigations

- [M1029 - Remote Data Storage](../../../../Defenses/Mitigations/M1029%20-%20Remote%20Data%20Storage.md) — Automatically forward events to a log server or data repository to prevent conditions in which the adversary can locate and manipulate data on the local system. When possible, minimize time delay on event reporting to avoid prolonged storage on the local system.
- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Protect generated event files and logs that are stored locally with proper permissions and authentication and limit opportunities for adversaries to increase privileges by preventing Privilege Escalation opportunities.

## Sources

- [FreeDesktop Journal](https://www.freedesktop.org/software/systemd/man/systemd-journald.service.html)
- [Microsoft RDP Removal](https://docs.microsoft.com/troubleshoot/windows-server/remote/remove-entries-from-remote-desktop-connection-computer)
- [Moran RDPieces](https://www.osdfcon.org/presentations/2020/Brian-Moran_Putting-Together-the-RDPieces.pdf)
- [Apple Culprit Access](https://discussions.apple.com/thread/3991574)
- [Apple Unified Log Analysis Remote Login and Screen Sharing](https://sarah-edwards-xzkc.squarespace.com/blog/2020/4/30/analysis-of-apple-unified-logs-quarantine-edition-entry-6-working-from-home-remote-logins)
