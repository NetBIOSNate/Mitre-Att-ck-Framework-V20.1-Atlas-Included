# T1204 - User Execution

[Enterprise](../../../README.md) / [Execution](../README.md)

An adversary may rely upon specific actions by a user in order to gain execution. Users may be subjected to social engineering to get them to execute malicious code by, for example, opening a malicious document file or link. These user actions will typically be observed as follow-on behavior from forms of [Phishing](https://attack.mitre.org/techniques/T1566).

While [User Execution](https://attack.mitre.org/techniques/T1204) frequently occurs shortly after Initial Access it may occur at other phases of an intrusion, such as when an adversary places a file in a shared directory or on a user's desktop hoping that a user will click on it. This activity may also be seen shortly after [Internal Spearphishing](https://attack.mitre.org/techniques/T1534).

Adversaries may also deceive users into performing actions such as:

* Enabling [Remote Access Tools](https://attack.mitre.org/techniques/T1219), allowing direct control of the system to the adversary
* Running malicious JavaScript in their browser, allowing adversaries to [Steal Web Session Cookie](https://attack.mitre.org/techniques/T1539)s(Citation: Talos Roblox Scam 2023)(Citation: Krebs Discord Bookmarks 2023)
* Downloading and executing malware for [User Execution](https://attack.mitre.org/techniques/T1204)
* Coerceing users to copy, paste, and execute malicious code manually(Citation: Reliaquest-execution)(Citation: proofpoint-selfpwn)

For example, tech support scams can be facilitated through [Phishing](https://attack.mitre.org/techniques/T1566), vishing, or various forms of user interaction. Adversaries can use a combination of these methods, such as spoofing and promoting toll-free numbers or call centers that are used to direct victims to malicious websites, to deliver and execute payloads containing malware or [Remote Access Tools](https://attack.mitre.org/techniques/T1219).(Citation: Telephone Attack Delivery)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1204)

**Tactics**  [Execution](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [IaaS](../../../Platforms/IaaS.md), [Containers](../../../Platforms/Containers.md)

## Sub-techniques

- [T1204.004 - Malicious Copy and Paste](T1204.004%20-%20Malicious%20Copy%20and%20Paste/README.md)
- [T1204.002 - Malicious File](T1204.002%20-%20Malicious%20File/README.md)
- [T1204.003 - Malicious Image](T1204.003%20-%20Malicious%20Image/README.md)
- [T1204.005 - Malicious Library](T1204.005%20-%20Malicious%20Library/README.md)
- [T1204.001 - Malicious Link](T1204.001%20-%20Malicious%20Link/README.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent executable files from running unless they meet a prevalence, age, or trusted list criteria and to prevent Office applications from creating potentially malicious executable content by blocking malicious code from being written to disk. Note: cloud-delivered protection must be enabled to use certain rules. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Application control may be able to prevent the running of executables masquerading as other files.
- [M1033 - Limit Software Installation](../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Where possible, consider requiring developers to pull from internal repositories containing verified and approved packages rather than from external ones.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — If a link is being visited by a user, network intrusion prevention systems and systems designed to scan and remove malicious downloads can be used to block activity.
- [M1021 - Restrict Web-Based Content](../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — If a link is being visited by a user, block unknown or unused files in transit by default that should not be downloaded or by policy from suspicious sites as a best practice to prevent some vectors, such as .scr, .exe, .pif, .cpl, etc. Some download scanning devices can open and analyze compressed and encrypted formats, such as zip and rar that may be used to conceal malicious files.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Use user training as a way to bring awareness to common phishing and spearphishing techniques and how to raise suspicion for potentially malicious events.

## Procedure examples

- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has recruited target organization employees or contractors who provide credentials and approve an associated MFA prompt, or install remote management software onto a corporate workstation, allowing [LAPSUS$](https://attack.mitre.org/groups/G1004) to take control of an authenticated system.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [S1213 - Lumma Stealer](../../../Threat%20Intelligence/Software/Malware/S1213%20-%20Lumma%20Stealer.md) — [Lumma Stealer](https://attack.mitre.org/software/S1213) has been distributed through a fake CAPTCHA that presents instructions to the victim to open Windows Run window (“Windows Button + R”) and paste clipboard contents (“CTRL + V”) and press “Enter” to execute a Base64-encoded PowerShell.(Citation: Qualys LummaStealer 2024)(Citation: Cybereason LumaStealer Undated)(Citation: Netskope LummaStealer 2025) [Cybereason LumaStealer Undated](https://www.cybereason.com/blog/threat-analysis-rise-of-lummastealer) · [Netskope LummaStealer 2025](https://www.netskope.com/blog/lumma-stealer-fake-captchas-new-techniques-to-evade-detection) · [Qualys LummaStealer 2024](https://blog.qualys.com/vulnerabilities-threat-research/2024/10/20/unmasking-lumma-stealer-analyzing-deceptive-tactics-with-fake-captcha)
- [S1130 - Raspberry Robin](../../../Threat%20Intelligence/Software/Malware/S1130%20-%20Raspberry%20Robin.md) — [Raspberry Robin](https://attack.mitre.org/software/S1130) execution can rely on users directly interacting with malicious LNK files.(Citation: Microsoft RaspberryRobin 2022) [Microsoft RaspberryRobin 2022](https://www.microsoft.com/en-us/security/blog/2022/10/27/raspberry-robin-worm-part-of-larger-ecosystem-facilitating-pre-ransomware-activity/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has impersonated organization IT and helpdesk staff to instruct victims to execute commercial remote access tools to gain initial access.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [C0037 - Water Curupira Pikabot Distribution](../../../Threat%20Intelligence/Campaigns/C0037%20-%20Water%20Curupira%20Pikabot%20Distribution.md) — [Water Curupira Pikabot Distribution](https://attack.mitre.org/campaigns/C0037) requires users to interact with malicious attachments in order to start [Pikabot](https://attack.mitre.org/software/S1145) installation.(Citation: TrendMicro Pikabot 2024) [TrendMicro Pikabot 2024](https://www.trendmicro.com/en_us/research/24/a/a-look-into-pikabot-spam-wave-campaign.html)

## Detection strategies

- [DET0478 - User Execution – multi-surface behavior chain (documents/links → helper/unpacker → LOLBIN/child → egress)](../../../Defenses/Detection%20Strategies/DET0478%20-%20User%20Execution%20%E2%80%93%20multi-surface%20behavior%20chain%20%28documents%20-%20links%20%E2%86%92%20helper%20-%20unpacker.md)

## Sources

- [Krebs Discord Bookmarks 2023](https://krebsonsecurity.com/2023/05/discord-admins-hacked-by-malicious-bookmarks/)
- [Reliaquest-execution](https://www.reliaquest.com/blog/new-execution-technique-in-clearfake-campaign/)
- [Telephone Attack Delivery](https://www.proofpoint.com/us/blog/threat-insight/caught-beneath-landline-411-telephone-oriented-attack-delivery)
- [Talos Roblox Scam 2023](https://blog.talosintelligence.com/roblox-scam-overview/)
- [proofpoint-selfpwn](https://www.proofpoint.com/us/blog/threat-insight/clipboard-compromise-powershell-self-pwn)
