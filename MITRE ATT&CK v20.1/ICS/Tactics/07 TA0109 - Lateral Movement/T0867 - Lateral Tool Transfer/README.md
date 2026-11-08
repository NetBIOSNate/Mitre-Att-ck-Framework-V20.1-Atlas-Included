# T0867 - Lateral Tool Transfer

[ICS](../../../README.md) / [Lateral Movement](../README.md)

Adversaries may transfer tools or other files from one system to another to stage adversary tools or other files over the course of an operation.(Citation: Enterprise ATT&CK) Copying of files may also be performed laterally between internal victim systems to support Lateral Movement with remote Execution using inherent file sharing protocols such as file sharing over SMB to connected network shares.(Citation: Enterprise ATT&CK)

In control systems environments, malware may use SMB and other file sharing protocols to move laterally through industrial networks.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0867)

**Tactics**  [Lateral Movement](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) moved their tools laterally within the ICS network. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) used a VBS script to facilitate lateral tool transfer. The VBS script was used to copy ICS-specific payloads with the following command: `cscript C:\Backinfo\ufn.vbs C:\Backinfo\101.dll C:\Delta\101.dll`(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [S0606 - Bad Rabbit](../../../Threat%20Intelligence/Software/Malware/S0606%20-%20Bad%20Rabbit.md) — [Bad Rabbit](https://attack.mitre.org/software/S0606) can move laterally through industrial networks by means of the SMB service. (Citation: Joe Slowik April 2019) [Joe Slowik April 2019](https://dragos.com/blog/industry-news/implications-of-it-ransomware-for-ics-environments/)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can use a Telnet session to load a malware implant on Omron PLCs.(Citation: CISA-AA22-103A)(Citation: Wylie-22) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0368 - NotPetya](../../../Threat%20Intelligence/Software/Malware/S0368%20-%20NotPetya.md) — [NotPetya](https://attack.mitre.org/software/S0368) can move laterally through industrial networks by means of the SMB service. (Citation: Joe Slowik April 2019) [Joe Slowik April 2019](https://dragos.com/blog/industry-news/implications-of-it-ransomware-for-ics-environments/)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) sends an SQL statement that creates a table and inserts a binary value into the table. The binary value is a hex string representation of the main Stuxnet DLL as an executable file (formed using resource 210) and an updated configuration data block. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) made attempts on multiple victim machines to transfer and execute the WMImplant tool.(Citation: FireEye TEMP.Veles 2018) [FireEye TEMP.Veles 2018](https://web.archive.org/web/20190202205824/https://www.fireeye.com/blog/threat-research/2018/10/triton-attribution-russian-government-owned-lab-most-likely-built-tools.html)
- [S0366 - WannaCry](../../../Threat%20Intelligence/Software/Malware/S0366%20-%20WannaCry.md) — [WannaCry](https://attack.mitre.org/software/S0366) can move laterally through industrial networks by means of the SMB service. (Citation: Joe Slowik April 2019) [Joe Slowik April 2019](https://dragos.com/blog/industry-news/implications-of-it-ransomware-for-ics-environments/)

## Detection strategies

- [DET0745 - Detection of Lateral Tool Transfer](../../../Defenses/Detection%20Strategies/DET0745%20-%20Detection%20of%20Lateral%20Tool%20Transfer.md)

## Mitigations

- [M0931 - Network Intrusion Prevention](../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware or unusual data transfer over known tools and protocols like FTP can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific obfuscation technique used by a particular adversary or tool and will likely be different across various malware families and versions. Adversaries will likely change tool C2 signatures over time or construct protocols in such a way as to avoid detection by common defensive tools.(Citation: University of Birmingham C2) [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)

## Sources

- [Enterprise ATT&CK](https://attack.mitre.org/techniques/T1570/)
