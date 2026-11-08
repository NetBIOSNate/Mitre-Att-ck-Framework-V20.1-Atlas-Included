# T1497.002 - User Activity Based Checks

[Enterprise](../../../../README.md) / [Discovery](../../README.md) / [T1497 - Virtualization/Sandbox Evasion](../README.md)

Adversaries may employ various user activity checks to detect and avoid virtualization and analysis environments. This may include changing behaviors based on the results of checks for the presence of artifacts indicative of a virtual machine environment (VME) or sandbox. If the adversary detects a VME, they may alter their malware to disengage from the victim or conceal the core functions of the implant. They may also search for VME artifacts before dropping secondary or additional payloads. Adversaries may use the information learned from [Virtualization/Sandbox Evasion](https://attack.mitre.org/techniques/T1497) during automated discovery to shape follow-on behaviors.(Citation: Deloitte Environment Awareness)

Adversaries may search for user activity on the host based on variables such as the speed/frequency of mouse movements and clicks(Citation: Sans Virtual Jan 2016) , browser history, cache, bookmarks, or number of files in common directories such as home or the desktop. Other methods may rely on specific user interaction with the system before the malicious code is activated, such as waiting for a document to close before activating a macro(Citation: Unit 42 Sofacy Nov 2018) or waiting for a user to double click on an embedded image to activate.(Citation: FireEye FIN7 April 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1497/002)

**Tactics**  [Stealth](../../../07%20TA0005%20-%20Stealth/README.md), [Discovery](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0420 - Detect User Activity Based Sandbox Evasion via Input & Artifact Probing](../../../../Defenses/Detection%20Strategies/DET0420%20-%20Detect%20User%20Activity%20Based%20Sandbox%20Evasion%20via%20Input%20%26%20Artifact%20Probing.md)

## Procedure examples

- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — The [Cobalt Strike](https://attack.mitre.org/software/S0154) loader can use the `MessageBoxA` API to prompt for user interaction as an anti-sandbox measure.(Citation: Cisco Talos Qilin Ransomware OCT 2025) [Cisco Talos Qilin Ransomware OCT 2025](https://blog.talosintelligence.com/uncovering-qilin-attack-methods-exposed-through-multiple-cases/)
- [G0012 - Darkhotel](../../../../Threat%20Intelligence/Groups/G0012%20-%20Darkhotel.md) — [Darkhotel](https://attack.mitre.org/groups/G0012) has used malware that repeatedly checks the mouse cursor position to determine if a real user is on the system.(Citation: Lastline DarkHotel Just In Time Decryption Nov 2015) [Lastline DarkHotel Just In Time Decryption Nov 2015](https://www.lastline.com/labsblog/defeating-darkhotel-just-in-time-decryption/)
- [G0046 - FIN7](../../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) used images embedded into document lures that only activate the payload when a user double clicks to avoid sandboxes.(Citation: FireEye FIN7 April 2017) [FireEye FIN7 April 2017](https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html)
- [S0439 - Okrum](../../../../Threat%20Intelligence/Software/Malware/S0439%20-%20Okrum.md) — [Okrum](https://attack.mitre.org/software/S0439) loader only executes the payload after the left mouse button has been pressed at least three times, in order to avoid being executed within virtualized or emulated environments.(Citation: ESET Okrum July 2019) [ESET Okrum July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/07/ESET_Okrum_and_Ketrican.pdf)
- [S9026 - ROAMINGHOUSE](../../../../Threat%20Intelligence/Software/Malware/S9026%20-%20ROAMINGHOUSE.md) — [ROAMINGHOUSE](https://attack.mitre.org/software/S9026) can check for specific mouse movements and user activity before initiating malicious activity.(Citation: Trend Micro Earth Kasha Anel NOV 2024) [Trend Micro Earth Kasha Anel NOV 2024](https://www.trendmicro.com/en_us/research/24/k/return-of-anel-in-the-recent-earth-kasha-spearphishing-campaign.html)
- [S0543 - Spark](../../../../Threat%20Intelligence/Software/Malware/S0543%20-%20Spark.md) — [Spark](https://attack.mitre.org/software/S0543) has used a splash screen to check whether an user actively clicks on the screen before running malicious code.(Citation: Unit42 Molerat Mar 2020) [Unit42 Molerat Mar 2020](https://unit42.paloaltonetworks.com/molerats-delivers-spark-backdoor/)
- [S1239 - TONESHELL](../../../../Threat%20Intelligence/Software/Malware/S1239%20-%20TONESHELL.md) — [TONESHELL](https://attack.mitre.org/software/S1239) has leveraged `GetForegroundWindow` to detect virtualization or sandboxes by calling the API twice and comparing each window handle.(Citation: 2022 November_TrendMicro_Earth Preta_Toneshell_Pubload) [2022 November_TrendMicro_Earth Preta_Toneshell_Pubload](https://www.trendmicro.com/en_us/research/22/k/earth-preta-spear-phishing-governments-worldwide.html)

## Sources

- [FireEye FIN7 April 2017](https://www.fireeye.com/blog/threat-research/2017/04/fin7-phishing-lnk.html)
- [Unit 42 Sofacy Nov 2018](https://unit42.paloaltonetworks.com/unit42-sofacy-continues-global-attacks-wheels-new-cannon-trojan/)
- [Sans Virtual Jan 2016](https://www.sans.org/reading-room/whitepapers/forensics/detecting-malware-sandbox-evasion-techniques-36667)
- [Deloitte Environment Awareness](https://drive.google.com/file/d/1t0jn3xr4ff2fR30oQAUn_RsWSnMpOAQc/edit)
