# T1565.001 - Stored Data Manipulation

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1565 - Data Manipulation](../README.md)

Adversaries may insert, delete, or manipulate data at rest in order to influence external outcomes or hide activity, thus threatening the integrity of the data.(Citation: FireEye APT38 Oct 2018)(Citation: DOJ Lazarus Sony 2018) By manipulating stored data, adversaries may attempt to affect a business process, organizational understanding, and decision making.

Stored data could include a variety of file formats, such as Office files, databases, stored emails, and custom file formats. The type of modification and the impact it will have depends on the type of data as well as the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system that would typically be gained through a prolonged information gathering campaign in order to have the desired impact.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1565/001)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Consider encrypting important information to reduce an adversary’s ability to perform tailored data modifications.
- [M1029 - Remote Data Storage](../../../../Defenses/Mitigations/M1029%20-%20Remote%20Data%20Storage.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and manipulate backups. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure least privilege principles are applied to important information resources to reduce exposure to data manipulation risk.

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used DYEPACK to create, delete, and alter records in databases used for SWIFT transactions.(Citation: FireEye APT38 Oct 2018) [FireEye APT38 Oct 2018](https://services.google.com/fh/files/misc/apt38-un-usual-suspects.pdf)
- [S1135 - MultiLayer Wiper](../../../../Threat%20Intelligence/Software/Malware/S1135%20-%20MultiLayer%20Wiper.md) — [MultiLayer Wiper](https://attack.mitre.org/software/S1135) changes the original path information of deleted files to make recovery efforts more difficult.(Citation: Unit42 Agrius 2023) [Unit42 Agrius 2023](https://unit42.paloaltonetworks.com/agonizing-serpens-targets-israeli-tech-higher-ed-sectors/)
- [S0562 - SUNSPOT](../../../../Threat%20Intelligence/Software/Malware/S0562%20-%20SUNSPOT.md) — [SUNSPOT](https://attack.mitre.org/software/S0562) created a copy of the SolarWinds Orion software source file with a <code>.bk</code> extension to backup the original content, wrote [SUNBURST](https://attack.mitre.org/software/S0559) using the same filename but with a <code>.tmp</code> extension, and then moved [SUNBURST](https://attack.mitre.org/software/S0559) using <code>MoveFileEx</code> to the original filename with a <code>.cs</code> extension so it could be compiled within Orion software.(Citation: CrowdStrike SUNSPOT Implant January 2021) [CrowdStrike SUNSPOT Implant January 2021](https://www.crowdstrike.com/blog/sunspot-malware-technical-analysis/)

## Detection strategies

- [DET0193 - Detection Strategy for Stored Data Manipulation across OS Platforms.](../../../../Defenses/Detection%20Strategies/DET0193%20-%20Detection%20Strategy%20for%20Stored%20Data%20Manipulation%20across%20OS%20Platforms.md)

## Sources

- [DOJ Lazarus Sony 2018](https://www.justice.gov/opa/press-release/file/1092091/download)
- [FireEye APT38 Oct 2018](https://services.google.com/fh/files/misc/apt38-un-usual-suspects.pdf)
