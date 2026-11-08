# T1204.004 - Malicious Copy and Paste

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1204 - User Execution](../README.md)

An adversary may rely upon a user copying and pasting code in order to gain execution. Users may be subjected to social engineering to get them to copy and paste code directly into a [Command and Scripting Interpreter](https://attack.mitre.org/techniques/T1059). One such strategy is "ClickFix," in which adversaries present users with seemingly helpful solutions—such as prompts to fix errors or complete CAPTCHAs—that instead instruct the user to copy and paste malicious code.

Malicious websites, such as those used in [Drive-by Compromise](https://attack.mitre.org/techniques/T1189), may present fake error messages or CAPTCHA prompts that instruct users to open a terminal or the Windows Run Dialog box and execute an arbitrary command. These commands may be obfuscated using encoding or other techniques to conceal malicious intent. Once executed, the adversary will typically be able to establish a foothold on the victim's machine.(Citation: CloudSEK Lumma Stealer 2024)(Citation: Sekoia ClickFake 2025)(Citation: Reliaquest CAPTCHA 2024)(Citation: AhnLab LummaC2 2025)

Adversaries may also leverage phishing emails for this purpose. When a user attempts to open an attachment, they may be presented with a fake error and offered a malicious command to paste as a solution, consistent with the "ClickFix" strategy.(Citation: Proofpoint ClickFix 2024)(Citation: AhnLab Malicioys Copy Paste 2024)

Tricking a user into executing a command themselves may help to bypass email filtering, browser sandboxing, or other mitigations designed to protect users against malicious downloaded files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1204/004)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has leveraged ClickFix type tactics enticing victims to copy and paste malicious code.(Citation: Sentinel One Contagious Interview ClickFix September 2025)(Citation: Sekoia ClickFake 2025)(Citation: Validin Contagious Interview North Korea ClickFix January 2025) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/) · [Sekoia ClickFake 2025](https://blog.sekoia.io/clickfake-interview-campaign-by-lazarus/) · [Validin Contagious Interview North Korea ClickFix January 2025](https://www.validin.com/blog/inoculating_contagious_interview_with_validin/)
- [S1229 - Havoc](../../../../Threat%20Intelligence/Software/Malware/S1229%20-%20Havoc.md) — The [Havoc](https://attack.mitre.org/software/S1229) infection chain has been initiated via ClickFix lures in phishing emails.(Citation: Fortinet Havoc MAR 2025) [Fortinet Havoc MAR 2025](https://www.fortinet.com/blog/threat-research/havoc-sharepoint-with-microsoft-graph-api-turns-into-fud-c2)
- [S9044 - Kali365](../../../../Threat%20Intelligence/Software/Malware/S9044%20-%20Kali365.md) — [Kali365](https://attack.mitre.org/software/S9044) has dynamically generated legitimate device codes that displays on the victims screen alongside instructions to copy and paste the device code to initiate and complete a successful authentication process.(Citation: Artic Wolf Labs Kali365 Device Code April 2026)(Citation: Artic Wolf Kali365 Device Code OAuth June 2026)(Citation: FBI IC3 Alert I-052126 Kali365 May 2026)(Citation: Huntress Kali365 Device Code June 2026)(Citation: SpyCloud Kali365 June 2026) [Artic Wolf Labs Kali365 Device Code April 2026](https://arcticwolf.com/resources/blog/token-bingo-dont-let-your-code-be-the-winner/) · [Artic Wolf Kali365 Device Code OAuth June 2026](https://arcticwolf.com/resources/blog/kali365-expands-into-aws-microsoft-okta-xerox-max-messenger/) · [FBI IC3 Alert I-052126 Kali365 May 2026](https://www.ic3.gov/PSA/2026/PSA260521) · [Huntress Kali365 Device Code June 2026](https://www.huntress.com/blog/kali365-device-code-phishing-kit) · [SpyCloud Kali365 June 2026](https://spycloud.com/blog/kali365-anatomy-of-a-microsoft365-phishing-as-a-service-kit/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has leveraged ClickFix type tactics enticing victims to copy and paste malicious code.(Citation: NaumaanProofpoint_GlobalClickFix_April2025) [NaumaanProofpoint_GlobalClickFix_April2025](https://www.proofpoint.com/us/blog/threat-insight/around-world-90-days-state-sponsored-actors-try-clickfix)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has leveraged ClickFix type tactics enticing victims to copy and paste malicious PowerShell code.(Citation: NaumaanProofpoint_GlobalClickFix_April2025) [NaumaanProofpoint_GlobalClickFix_April2025](https://www.proofpoint.com/us/blog/threat-insight/around-world-90-days-state-sponsored-actors-try-clickfix)
- [S9050 - Vidar](../../../../Threat%20Intelligence/Software/Malware/S9050%20-%20Vidar.md) — [Vidar](https://attack.mitre.org/software/S9050) has used fake CAPTCHAs to deliver and execute itself to victims.(Citation: CyberAus_Vidar_May2026) [CyberAus_Vidar_May2026](https://www.cyber.gov.au/about-us/view-all-content/alerts-and-advisories/clickfix-distributing-vidar-stealer-via-wordpress-targeting-australian-infrastructure)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control where appropriate. PowerShell Constrained Language mode can be used to restrict access to sensitive or otherwise dangerous language elements such as those used to execute arbitrary Windows APIs or files (e.g., `Add-Type`).(Citation: Microsoft PowerShell CLM) [Microsoft PowerShell CLM](https://devblogs.microsoft.com/powershell/powershell-constrained-language-mode/)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — If a link is being requested by a user, network intrusion prevention systems and systems designed to scan and remove malicious downloads can be used to block activity.
- [M1021 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — If a link is being requested by a user, block unknown or unused files in transit by default that should not be downloaded or by policy from suspicious sites as a best practice to prevent some vectors, such as `.scr`, `.exe`, `.pif`, `.cpl`, etc.

## Detection strategies

- [DET0340 - User Execution – Malicious Copy & Paste (browser/email → shell with obfuscated one-liner) – T1204.004](../../../../Defenses/Detection%20Strategies/DET0340%20-%20User%20Execution%20%E2%80%93%20Malicious%20Copy%20%26%20Paste%20%28browser%20-%20email%20%E2%86%92%20shell%20with%20obfuscated%20one.md)

## Sources

- [AhnLab Malicioys Copy Paste 2024](https://asec.ahnlab.com/en/73952/)
- [AhnLab LummaC2 2025](https://asec.ahnlab.com/en/85699/)
- [Reliaquest CAPTCHA 2024](https://www.reliaquest.com/blog/using-captcha-for-compromise/)
- [Sekoia ClickFake 2025](https://blog.sekoia.io/clickfake-interview-campaign-by-lazarus/)
- [CloudSEK Lumma Stealer 2024](https://www.cloudsek.com/blog/unmasking-the-danger-lumma-stealer-malware-exploits-fake-captcha-pages)
- [Proofpoint ClickFix 2024](https://www.proofpoint.com/us/blog/threat-insight/security-brief-clickfix-social-engineering-technique-floods-threat-landscape)
