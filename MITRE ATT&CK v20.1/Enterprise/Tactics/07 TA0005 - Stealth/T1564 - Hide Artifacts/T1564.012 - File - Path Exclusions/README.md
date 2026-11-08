# T1564.012 - File/Path Exclusions

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may attempt to hide their file-based artifacts by writing them to specific folders or file names excluded from antivirus (AV) scanning and other defensive capabilities. AV and other file-based scanners often include exclusions to optimize performance as well as ease installation and legitimate use of applications. These exclusions may be contextual (e.g., scans are only initiated in response to specific triggering events/alerts), but are also often hardcoded strings referencing specific folders and/or files assumed to be trusted and legitimate.(Citation: Microsoft File Folder Exclusions)

Adversaries may abuse these exclusions to hide their file-based artifacts. For example, rather than  tampering with tool settings to add a new exclusion (i.e., [Disable or Modify Tools](https://attack.mitre.org/techniques/T1685)), adversaries may drop their file-based payloads in default or otherwise well-known exclusions. Adversaries may also use [Security Software Discovery](https://attack.mitre.org/techniques/T1518/001) and other [Discovery](https://attack.mitre.org/tactics/TA0007)/[Reconnaissance](https://attack.mitre.org/tactics/TA0043) activities to both discover and verify existing exclusions in a victim environment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/012)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0051 - Detection Strategy for File/Path Exclusions](../../../../Defenses/Detection%20Strategies/DET0051%20-%20Detection%20Strategy%20for%20File%20-%20Path%20Exclusions.md)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Review and audit file/folder exclusions, and limit scope of exclusions to only what is required where possible.(Citation: Microsoft File Folder Exclusions) [Microsoft File Folder Exclusions](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/configure-contextual-file-folder-exclusions-microsoft-defender-antivirus)
- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers should consider limiting the requirements for custom or otherwise difficult to manage file/folder exclusions. Where possible, install applications to trusted system folder paths that are already protected by restricted file and directory permissions.

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has added Microsoft Defender exclusions to include `C:\Windows\System32` to suppress detection of dropped tooling.(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has modified anti-virus settings to add its own executable to the exclusion list of the endpoint detection solution using the PowerShell command `Add-MpPreference -ExclusionProcess <malware path> -force`.(Citation: MSTI_GentelmenRansomware_May2026)(Citation: TrendAI_TheGentlemen_Sept2025)(Citation: CheckPointResearch_TheGentlemen_April2026)(Citation: CarveyODonnellWelchHuntress_TheGentlemen_May2026) [CarveyODonnellWelchHuntress_TheGentlemen_May2026](https://www.huntress.com/blog/the-gentlemen-ransomware-defense-evasion-ttps) · [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/) · [MSTI_GentelmenRansomware_May2026](https://www.microsoft.com/en-us/security/blog/2026/05/28/the-gentlemen-ransomware-dissecting-a-self-propagating-go-encryptor/) · [TrendAI_TheGentlemen_Sept2025](https://www.trendaisecurity.com/en-us/resources-insights/trendai-security-blog/unmasking-the-gentlemen-ransomware)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has placed [LunarWeb](https://attack.mitre.org/software/S1141) install files into directories that are excluded from scanning.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)

## Sources

- [Microsoft File Folder Exclusions](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/configure-contextual-file-folder-exclusions-microsoft-defender-antivirus)
