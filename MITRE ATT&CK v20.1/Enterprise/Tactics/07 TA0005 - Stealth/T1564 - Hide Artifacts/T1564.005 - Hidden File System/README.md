# T1564.005 - Hidden File System

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may use a hidden file system to conceal malicious activity from users and security tools. File systems provide a structure to store and access data from physical storage. Typically, a user engages with a file system through applications that allow them to access files and directories, which are an abstraction from their physical location (ex: disk sector). Standard file systems include FAT, NTFS, ext4, and APFS. File systems can also contain other structures, such as the Volume Boot Record (VBR) and Master File Table (MFT) in NTFS.(Citation: MalwareTech VFS Nov 2014)

Adversaries may use their own abstracted file system, separate from the standard file system present on the infected system. In doing so, adversaries can hide the presence of malicious components and file input/output from security tools. Hidden file systems, sometimes referred to as virtual file systems, can be implemented in numerous ways. One implementation would be to store a file system in reserved disk space unused by disk structures or standard file system partitions.(Citation: MalwareTech VFS Nov 2014)(Citation: FireEye Bootkits) Another implementation could be for an adversary to drop their own portable partition image as a file on top of the standard file system.(Citation: ESET ComRAT May 2020) Adversaries may also fragment files across the existing file system structure in non-standard ways.(Citation: Kaspersky Equation QA)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/005)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0114 - BOOTRASH](../../../../Threat%20Intelligence/Software/Malware/S0114%20-%20BOOTRASH.md) — [BOOTRASH](https://attack.mitre.org/software/S0114) has used unallocated disk space between partitions for a hidden file system that stores components of the Nemesis bootkit.(Citation: FireEye Bootkits) [FireEye Bootkits](https://www.fireeye.com/blog/threat-research/2015/12/fin1-targets-boot-record.html)
- [S0126 - ComRAT](../../../../Threat%20Intelligence/Software/Malware/S0126%20-%20ComRAT.md) — [ComRAT](https://attack.mitre.org/software/S0126) has used a portable FAT16 partition image placed in %TEMP% as a hidden file system.(Citation: ESET ComRAT May 2020) [ESET ComRAT May 2020](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET_Turla_ComRAT.pdf)
- [G0020 - Equation](../../../../Threat%20Intelligence/Groups/G0020%20-%20Equation.md) — [Equation](https://attack.mitre.org/groups/G0020) has used an encrypted virtual file system stored in the Windows Registry.(Citation: Kaspersky Equation QA) [Kaspersky Equation QA](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064459/Equation_group_questions_and_answers.pdf)
- [S0019 - Regin](../../../../Threat%20Intelligence/Software/Malware/S0019%20-%20Regin.md) — [Regin](https://attack.mitre.org/software/S0019) has used a hidden file system to store some of its components.(Citation: Kaspersky Regin) [Kaspersky Regin](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070305/Kaspersky_Lab_whitepaper_Regin_platform_eng.pdf)
- [G0041 - Strider](../../../../Threat%20Intelligence/Groups/G0041%20-%20Strider.md) — [Strider](https://attack.mitre.org/groups/G0041) has used a hidden file system that is stored as a file on disk.(Citation: Kaspersky ProjectSauron Full Report) [Kaspersky ProjectSauron Full Report](https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf)
- [S0022 - Uroburos](../../../../Threat%20Intelligence/Software/Malware/S0022%20-%20Uroburos.md) — [Uroburos](https://attack.mitre.org/software/S0022) can use concealed storage mechanisms including an NTFS or FAT-16 filesystem encrypted with CAST-128 in CBC mode.(Citation: Joint Cybersecurity Advisory AA23-129A Snake Malware May 2023) [Joint Cybersecurity Advisory AA23-129A Snake Malware May 2023](https://www.cisa.gov/sites/default/files/2023-05/aa23-129a_snake_malware_2.pdf)

## Detection strategies

- [DET0461 - Detection Strategy for Hidden File System Abuse](../../../../Defenses/Detection%20Strategies/DET0461%20-%20Detection%20Strategy%20for%20Hidden%20File%20System%20Abuse.md)

## Sources

- [FireEye Bootkits](https://www.fireeye.com/blog/threat-research/2015/12/fin1-targets-boot-record.html)
- [ESET ComRAT May 2020](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET_Turla_ComRAT.pdf)
- [MalwareTech VFS Nov 2014](https://www.malwaretech.com/2014/11/virtual-file-systems-for-beginners.html)
- [Kaspersky Equation QA](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064459/Equation_group_questions_and_answers.pdf)
