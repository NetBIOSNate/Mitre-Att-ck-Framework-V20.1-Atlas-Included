# T0849 - Masquerading

[ICS](../../../README.md) / [Evasion](../README.md)

Adversaries may use masquerading to disguise a malicious application or executable as another file, to avoid operator and engineer suspicion. Possible disguises of these masquerading files can include commonly found programs, expected vendor executables and configuration files, and other commonplace application and naming conventions. By impersonating expected and vendor-relevant files and applications, operators and engineers may not notice the presence of the underlying malicious content and possibly end up running those masquerading as legitimate functions. 

Applications and other files commonly found on Windows systems or in engineering workstations have been impersonated before. This can be as simple as renaming a file to effectively disguise it in the ICS environment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0849)

**Tactics**  [Evasion](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) transferred executable files as .txt and then renamed them to .exe, likely to avoid detection through extension tracking.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [S0605 - EKANS](../../../Threat%20Intelligence/Software/Malware/S0605%20-%20EKANS.md) — [EKANS](https://attack.mitre.org/software/S0605) masquerades itself as a valid executable with the filename update.exe. Many valid programs use the process name update.exe to perform background software updates. (Citation: Dragos Threat Intelligence February 2020) [Dragos Threat Intelligence February 2020](https://www.dragos.com/blog/industry-news/ekans-ransomware-and-ics-operations/)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) searches for whether the Ahnlab autoup.exe service is running on the target system and injects its payload into this existing process. (Citation: Tom Fakterman August 2019) [Tom Fakterman August 2019](https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) renames s7otbxdx.dll, a dll responsible for handling communications with a PLC. It replaces this dll file with its own version that allows it to intercept any calls that are made to access the PLC. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009)'s injector, inject.bin, masquerades as a standard compiled PowerPC program for the Tricon. (Citation: DHS CISA February 2019) [Triton](https://attack.mitre.org/software/S1009) was configured to masquerade as trilog.exe, which is the Triconex software for analyzing SIS logs.(Citation: FireEye TRITON) [FireEye TRITON](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html) · [DHS CISA February 2019](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%20-%20Safety%20System%20Targeted%20Malware%20%28Update%20B%29.pdf)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Require signed binaries.
- [M0938 - Execution Prevention](../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Use tools that restrict program execution via application control by attributes other than file name for common system and application utilities.
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Use file system access controls to protect system and application folders.

## Detection strategies

- [DET0725 - Detection of Masquerading](../../../Defenses/Detection%20Strategies/DET0725%20-%20Detection%20of%20Masquerading.md)
