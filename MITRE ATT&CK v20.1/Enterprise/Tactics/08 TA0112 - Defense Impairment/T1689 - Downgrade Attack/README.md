# T1689 - Downgrade Attack

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may downgrade or use a version of system features that may be outdated, vulnerable, and/or does not support updated security controls. Downgrade attacks typically take advantage of a system’s backward compatibility to force it into less secure modes of operation.

Adversaries may downgrade and use various less-secure versions of features of a system, such as [Command and Scripting Interpreter](https://attack.mitre.org/techniques/T1059) or even network protocols that can be abused to enable [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) or [Network Sniffing](https://attack.mitre.org/techniques/T1040).(Citation: Praetorian TLS Downgrade Attack 2014) For example, [PowerShell](https://attack.mitre.org/techniques/T1059/001) versions 5+ includes Script Block Logging (SBL), which can record executed script content. However, adversaries may attempt to execute a previous version of PowerShell that does not support SBL with the intent to impair defenses while running malicious scripts that may have otherwise been detected.(Citation: CrowdStrike downgrade attack)(Citation: Google Cloud downgrade attack)(Citation: att_def_ps_logging)

Adversaries may similarly target network traffic to downgrade from an encrypted HTTPS connection to an unsecured HTTP connection that exposes network data in clear text.(Citation: Targeted SSL Stripping Attacks Are Real)(Citation: CrowdStrike Downgrade attack 2) On Windows systems, adversaries may downgrade the boot manager to a vulnerable version that bypasses Secure Boot, granting the ability to disable various operating system security mechanisms.(Citation: SafeBreach)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1689)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Procedure examples

- [S1180 - BlackByte Ransomware](../../../Threat%20Intelligence/Software/Malware/S1180%20-%20BlackByte%20Ransomware.md) — [BlackByte Ransomware](https://attack.mitre.org/software/S1180) enables SMBv1 during execution.(Citation: Trustwave BlackByte 2021) [Trustwave BlackByte 2021](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/blackbyte-ransomware-pt-1-in-depth-analysis/)
- [C0041 - FrostyGoop Incident](../../../Threat%20Intelligence/Campaigns/C0041%20-%20FrostyGoop%20Incident.md) — During [FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041), the adversary downgraded firmware on victim devices in order to impair visibility into the process environment.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S0692 - SILENTTRINITY](../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) can downgrade NTLM to capture NTLM hashes.(Citation: Github_SILENTTRINITY) [Github_SILENTTRINITY](https://github.com/byt3bl33d3r/SILENTTRINITY)
- [S9051 - The Gentlemen Ransomware](../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has used the following command to re-enable SMB1: `Enable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol -NoRestart`.(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider removing previous versions of tools that are unnecessary to the environment when possible.
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Consider implementing policies on internal web servers, such HTTP Strict Transport Security, that enforce the use of HTTPS/network traffic encryption to prevent insecure connections.(Citation: Chromium HSTS) [Chromium HSTS](https://www.chromium.org/hsts/)

## Detection strategies

- [DET0350 - Detecting Downgrade Attacks](../../../Defenses/Detection%20Strategies/DET0350%20-%20Detecting%20Downgrade%20Attacks.md)

## Sources

- [SafeBreach](https://www.safebreach.com/blog/downgrade-attacks-using-windows-updates/)
- [CrowdStrike Downgrade attack 2](https://www.crowdstrike.com/en-us/cybersecurity-101/cyberattacks/downgrade-attack/)
- [Targeted SSL Stripping Attacks Are Real](https://blog.checkpoint.com/research/targeted-ssl-stripping-attacks-are-real/amp/)
- [CrowdStrike downgrade attack](https://www.crowdstrike.com/en-us/blog/how-falcon-complete-stopped-a-big-game-hunting-ransomware-attack/)
- [att_def_ps_logging](https://nsfocusglobal.com/attack-and-defense-around-powershell-event-logging/)
- [Google Cloud downgrade attack](https://cloud.google.com/blog/topics/threat-intelligence/bring-your-own-land-novel-red-teaming-technique/)
- [Praetorian TLS Downgrade Attack 2014](https://www.praetorian.com/blog/man-in-the-middle-tls-ssl-protocol-downgrade-attack/)
