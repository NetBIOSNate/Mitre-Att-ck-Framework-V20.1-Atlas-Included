# T1623.001 - Unix Shell

[Mobile](../../../../README.md) / [Execution](../../README.md) / [T1623 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse Unix shell commands and scripts for execution. Unix shells are the underlying command prompts on Android and iOS devices. Unix shells can control every aspect of a system, with certain commands requiring elevated privileges that are only accessible if the device has been rooted or jailbroken. 

Unix shells also support scripts that enable sequential execution of commands as well as other typical programming operations such as conditionals and loops. Common uses of shell scripts include long or repetitive tasks, or the need to run the same set of commands on multiple systems. 

Adversaries may abuse Unix shells to execute various commands or payloads. Interactive shells may be accessed through command and control channels or during lateral movement such as with SSH. Adversaries may also leverage shell scripts to deliver and execute multiple commands on victims or as part of payloads used for persistence. 

If the device has been rooted or jailbroken, adversaries may locate and invoke a superuser binary to elevate their privileges and interact with the system as the root user. This dangerous level of permissions allows the adversary to run special commands and modify protected system files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1623/001)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1061 - AbstractEmu](../../../../Threat%20Intelligence/Software/Malware/S1061%20-%20AbstractEmu.md) — [AbstractEmu](https://attack.mitre.org/software/S1061) has included encoded shell scripts to potentially aid in the rooting process.(Citation: lookout_abstractemu_1021) [lookout_abstractemu_1021](https://www.lookout.com/blog/lookout-discovers-global-rooting-malware-campaign)
- [S0655 - BusyGasper](../../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can run shell commands.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S0555 - CHEMISTGAMES](../../../../Threat%20Intelligence/Software/Malware/S0555%20-%20CHEMISTGAMES.md) — [CHEMISTGAMES](https://attack.mitre.org/software/S0555) can run bash commands.(Citation: CYBERWARCON CHEMISTGAMES) [CYBERWARCON CHEMISTGAMES](https://www.youtube.com/watch?v=xoNSbm1aX_w)
- [S0550 - DoubleAgent](../../../../Threat%20Intelligence/Software/Malware/S0550%20-%20DoubleAgent.md) — [DoubleAgent](https://attack.mitre.org/software/S0550) can run arbitrary shell commands.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0544 - HenBox](../../../../Threat%20Intelligence/Software/Malware/S0544%20-%20HenBox.md) — [HenBox](https://attack.mitre.org/software/S0544) can run commands as root.(Citation: Palo Alto HenBox) [Palo Alto HenBox](https://unit42.paloaltonetworks.com/unit42-henbox-chickens-come-home-roost/)
- [S1082 - Sunbird](../../../../Threat%20Intelligence/Software/Malware/S1082%20-%20Sunbird.md) — [Sunbird](https://attack.mitre.org/software/S1082) can try to run arbitrary commands as root.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S0558 - Tiktok Pro](../../../../Threat%20Intelligence/Software/Malware/S0558%20-%20Tiktok%20Pro.md) — [Tiktok Pro](https://attack.mitre.org/software/S0558) can execute commands .(Citation: Zscaler TikTok Spyware) [Zscaler TikTok Spyware](https://www.zscaler.com/blogs/security-research/tiktok-spyware)

## Mitigations

- [M1002 - Attestation](../../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation can often detect jailbroken or rooted devices.
- [M1010 - Deploy Compromised Device Detection Method](../../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products can typically detect jailbroken or rooted devices.

## Detection strategies

- [DET0607 - Detection of Unix Shell](../../../../Defenses/Detection%20Strategies/DET0607%20-%20Detection%20of%20Unix%20Shell.md)

## Sources

- [Samsung Knox Mobile Threat Defense](https://partner.samsungknox.com/mtd)
