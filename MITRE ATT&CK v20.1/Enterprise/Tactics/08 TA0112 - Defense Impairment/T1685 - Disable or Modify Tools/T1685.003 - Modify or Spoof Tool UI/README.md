# T1685.003 - Modify or Spoof Tool UI

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

Adversaries may spoof or manipulate security tool user interfaces (UIs) to falsely indicate tools are functioning normally and delay detection and response. 

Adversaries may present misleading or falsified security tool interfaces (UIs) that display normal or healthy status indicators, even when underlying security tools have been disabled, degraded, or otherwise tampered with. Security tools typically provide visibility into system health, alerting, and operational status; by misrepresenting this information, adversaries can undermine defender trust in these signals and obscure the true security posture of the system. 

This behavior is often used in conjunction with efforts to disable or modify tools, where adversaries first impair the functionality of defenses (e.g., EDR, logging agents) and then replace or mimic their interfaces to conceal the loss of visibility. By maintaining the appearance of normal operations, such as showing active protection, successful updates, or absence of threats, adversaries can delay investigation and response, enabling continued malicious activity. 

For example, adversaries may display a fake Windows Security interface or system tray icon indicating a “protected” or “healthy” state after disabling Windows Defender or related services.(Citation: BlackBasta)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/003)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has displayed a fake “system update complete” dialog to the user following successful deployment of malicious payloads.(Citation: Microsoft Sapphire Sleet APR 2026) [Microsoft Sapphire Sleet APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/16/dissecting-sapphire-sleets-macos-intrusion-from-lure-to-compromise/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has prompted victims with fake warnings and error messages to appear as legitimate failures to reduce user suspicion.(Citation: CheckPoint_NimbusManticore_May2026)(Citation: CheckPoint_NimbusManticoreEurope_Sept2025)(Citation: Mandiant_UNC1549_Feb2024) [CheckPoint_NimbusManticoreEurope_Sept2025](https://research.checkpoint.com/2025/nimbus-manticore-deploys-new-malware-targeting-europe/) · [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/) · [Mandiant_UNC1549_Feb2024](https://cloud.google.com/blog/topics/threat-intelligence/suspected-iranian-unc1549-targets-israel-middle-east)
- [S9014 - PHASEJAM](../../../../Threat%20Intelligence/Software/Malware/S9014%20-%20PHASEJAM.md) — [PHASEJAM](https://attack.mitre.org/software/S9014) has prevented legitimate Ivanti Connect Secure system upgrades by intercepting the upgrade command and rendering fake HTML upgrade progress bar through a function called `processUpgradeDisplay()` which allowed the compromised device to remain under the control of the adversary.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)

## Detection strategies

- [DET0311 - Detection for Spoofing Tool UI across OS Platforms](../../../../Defenses/Detection%20Strategies/DET0311%20-%20Detection%20for%20Spoofing%20Tool%20UI%20across%20OS%20Platforms.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application controls to mitigate installation and use of payloads that may be utilized to spoof security alerting.

## Sources

- [BlackBasta](https://www.sentinelone.com/labs/black-basta-ransomware-attacks-deploy-custom-edr-evasion-tools-tied-to-fin7-threat-actor/)
