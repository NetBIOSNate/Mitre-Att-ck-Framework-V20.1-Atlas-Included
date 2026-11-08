# T1564 - Hide Artifacts

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may attempt to hide artifacts associated with their behaviors to evade detection. Operating systems may have features to hide various artifacts, such as important system files and administrative task execution, to avoid disrupting user work environments and prevent users from changing files or features on the system. Adversaries may abuse these features to hide artifacts such as files, directories, user accounts, or other system activity to evade detection.(Citation: Sofacy Komplex Trojan)(Citation: Cybereason OSX Pirrit)(Citation: MalwareBytes ADS July 2015)

Adversaries may also attempt to hide artifacts associated with malicious behavior by creating computing regions that are isolated from common security instrumentation, such as through the use of virtualization technology.(Citation: Sophos Ragnar May 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564)

**Tactics**  [Stealth](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1564.013 - Bind Mounts](T1564.013%20-%20Bind%20Mounts/README.md)
- [T1564.008 - Email Hiding Rules](T1564.008%20-%20Email%20Hiding%20Rules/README.md)
- [T1564.014 - Extended Attributes](T1564.014%20-%20Extended%20Attributes/README.md)
- [T1564.012 - File/Path Exclusions](T1564.012%20-%20File%20-%20Path%20Exclusions/README.md)
- [T1564.005 - Hidden File System](T1564.005%20-%20Hidden%20File%20System/README.md)
- [T1564.001 - Hidden Files and Directories](T1564.001%20-%20Hidden%20Files%20and%20Directories/README.md)
- [T1564.002 - Hidden Users](T1564.002%20-%20Hidden%20Users/README.md)
- [T1564.003 - Hidden Window](T1564.003%20-%20Hidden%20Window/README.md)
- [T1564.011 - Ignore Process Interrupts](T1564.011%20-%20Ignore%20Process%20Interrupts/README.md)
- [T1564.004 - NTFS File Attributes](T1564.004%20-%20NTFS%20File%20Attributes/README.md)
- [T1564.010 - Process Argument Spoofing](T1564.010%20-%20Process%20Argument%20Spoofing/README.md)
- [T1564.009 - Resource Forking](T1564.009%20-%20Resource%20Forking/README.md)
- [T1564.006 - Run Virtual Instance](T1564.006%20-%20Run%20Virtual%20Instance/README.md)
- [T1564.007 - VBA Stomping](T1564.007%20-%20VBA%20Stomping/README.md)

## Procedure examples

- [S0482 - Bundlore](../../../Threat%20Intelligence/Software/Malware/S0482%20-%20Bundlore.md) — [Bundlore](https://attack.mitre.org/software/S0482) uses the <code>mktemp</code> utility to make unique file and directory names for payloads, such as <code>TMP_DIR=`mktemp -d -t x</code>.(Citation: 20 macOS Common Tools and Techniques) [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
- [S1066 - DarkTortilla](../../../Threat%20Intelligence/Software/Malware/S1066%20-%20DarkTortilla.md) — [DarkTortilla](https://attack.mitre.org/software/S1066) has used `%HiddenReg%` and `%HiddenKey%` as part of its persistence via the Windows registry.(Citation: Secureworks DarkTortilla Aug 2022) [Secureworks DarkTortilla Aug 2022](https://www.secureworks.com/research/darktortilla-malware-analysis)
- [S9025 - NOOPLDR](../../../Threat%20Intelligence/Software/Malware/S9025%20-%20NOOPLDR.md) — [NOOPLDR](https://attack.mitre.org/software/S9025) can hide services used to aid execution.(Citation: JPCERT MirrorFace JUL 2024) [JPCERT MirrorFace JUL 2024](https://blogs.jpcert.or.jp/en/2024/07/mirrorface-attack-against-japanese-organisations.html)
- [S0402 - OSX/Shlayer](../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — [OSX/Shlayer](https://attack.mitre.org/software/S0402) has used the <code>mktemp</code> utility to make random and unique filenames for payloads, such as <code>export tmpDir="$(mktemp -d /tmp/XXXXXXXXXXXX)"</code> or <code>mktemp -t Installer</code>.(Citation: sentinelone shlayer to zshlayer)(Citation: 20 macOS Common Tools and Techniques)(Citation: Shlayer jamf gatekeeper bypass 2021) [Shlayer jamf gatekeeper bypass 2021](https://www.jamf.com/blog/shlayer-malware-abusing-gatekeeper-bypass-on-macos/) · [sentinelone shlayer to zshlayer](https://www.sentinelone.com/blog/coming-out-of-your-shell-from-shlayer-to-zshlayer/) · [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
- [S0332 - Remcos](../../../Threat%20Intelligence/Software/Tools/S0332%20-%20Remcos.md) — [Remcos](https://attack.mitre.org/software/S0332) can modify file attributes to hide the file.(Citation: Fortinet Remcos Campaign NOV 2024) [Fortinet Remcos Campaign NOV 2024](https://www.fortinet.com/blog/threat-research/new-campaign-uses-remcos-rat-to-exploit-victims)
- [S1011 - Tarrask](../../../Threat%20Intelligence/Software/Malware/S1011%20-%20Tarrask.md) — [Tarrask](https://attack.mitre.org/software/S1011) is able to create “hidden” scheduled tasks by deleting the Security Descriptor (`SD`) registry value.(Citation: Tarrask scheduled task) [Tarrask scheduled task](https://www.microsoft.com/security/blog/2022/04/12/tarrask-malware-uses-scheduled-tasks-for-defense-evasion/)
- [S0670 - WarzoneRAT](../../../Threat%20Intelligence/Software/Malware/S0670%20-%20WarzoneRAT.md) — [WarzoneRAT](https://attack.mitre.org/software/S0670) can masquerade the Process Environment Block on a compromised host to hide its attempts to elevate privileges through `IFileOperation`.(Citation: Check Point Warzone Feb 2020) [Check Point Warzone Feb 2020](https://research.checkpoint.com/2020/warzone-behind-the-enemy-lines/)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Review and audit file/folder exclusions, and limit scope of exclusions to only what is required where possible.(Citation: Microsoft File Folder Exclusions) [Microsoft File Folder Exclusions](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/configure-contextual-file-folder-exclusions-microsoft-defender-antivirus)
- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers should consider limiting the requirements for custom or otherwise difficult to manage file/folder exclusions. Where possible, install applications to trusted system folder paths that are already protected by restricted file and directory permissions.
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically audit virtual machines for abnormalities.
- [M1033 - Limit Software Installation](../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Restrict the installation of software that may be abused to create hidden desktops, such as hVNC, to user groups that require it.

## Detection strategies

- [DET0502 - Detection Strategy for Hidden Artifacts Across Platforms](../../../Defenses/Detection%20Strategies/DET0502%20-%20Detection%20Strategy%20for%20Hidden%20Artifacts%20Across%20Platforms.md)

## Sources

- [Cybereason OSX Pirrit](https://cdn2.hubspot.net/hubfs/3354902/Content%20PDFs/Cybereason-Lab-Analysis-OSX-Pirrit-4-6-16.pdf)
- [MalwareBytes ADS July 2015](https://blog.malwarebytes.com/101/2015/07/introduction-to-alternate-data-streams/)
- [Sofacy Komplex Trojan](https://researchcenter.paloaltonetworks.com/2016/09/unit42-sofacys-komplex-os-x-trojan/)
- [Sophos Ragnar May 2020](https://news.sophos.com/en-us/2020/05/21/ragnar-locker-ransomware-deploys-virtual-machine-to-dodge-security/)
