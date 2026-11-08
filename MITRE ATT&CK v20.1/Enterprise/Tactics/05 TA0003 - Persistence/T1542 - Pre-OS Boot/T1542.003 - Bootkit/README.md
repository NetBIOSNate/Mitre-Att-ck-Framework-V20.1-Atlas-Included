# T1542.003 - Bootkit

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1542 - Pre-OS Boot](../README.md)

Adversaries may use bootkits to persist on systems. A bootkit is a malware variant that modifies the boot sectors of a hard drive, allowing malicious code to execute before a computer's operating system has loaded. Bootkits reside at a layer below the operating system and may make it difficult to perform full remediation unless an organization suspects one was used and can act accordingly.

In BIOS systems, a bootkit may modify the Master Boot Record (MBR) and/or Volume Boot Record (VBR).(Citation: Mandiant M Trends 2016) The MBR is the section of disk that is first loaded after completing hardware initialization by the BIOS. It is the location of the boot loader. An adversary who has raw access to the boot drive may overwrite this area, diverting execution during startup from the normal boot loader to adversary code.(Citation: Lau 2011)

The MBR passes control of the boot process to the VBR. Similar to the case of MBR, an adversary who has raw access to the boot drive may overwrite the VBR to divert execution during startup to adversary code.

In UEFI (Unified Extensible Firmware Interface) systems, a bootkit may instead create or modify files in the EFI system partition (ESP). The ESP is a partition on data storage used by devices containing UEFI that allows the system to boot the OS and other utilities used by the system. An adversary can use the newly created or patched files in the ESP to run malicious kernel code.(Citation: Microsoft Security)(Citation: welivesecurity)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542/003)

**Tactics**  [Persistence](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has deployed a bootkit along with [Downdelph](https://attack.mitre.org/software/S0134) to ensure its persistence on the victim. The bootkit shares code with some variants of [BlackEnergy](https://attack.mitre.org/software/S0089).(Citation: ESET Sednit Part 3) [ESET Sednit Part 3](http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part3.pdf)
- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) deployed Master Boot Record bootkits on Windows systems to hide their malware and maintain persistence on victim systems.(Citation: FireEye APT41 Aug 2019) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [S0114 - BOOTRASH](../../../../Threat%20Intelligence/Software/Malware/S0114%20-%20BOOTRASH.md) — [BOOTRASH](https://attack.mitre.org/software/S0114) is a Volume Boot Record (VBR) bootkit that uses the VBR to maintain persistence.(Citation: Mandiant M Trends 2016)(Citation: FireEye Bootkits)(Citation: FireEye BOOTRASH SANS) [FireEye Bootkits](https://www.fireeye.com/blog/threat-research/2015/12/fin1-targets-boot-record.html) · [FireEye BOOTRASH SANS](https://web.archive.org/web/20190926040727/https://www.sans.org/cyber-security-summit/archives/file/summit-archive-1498163766.pdf) · [Mandiant M Trends 2016](https://web.archive.org/web/20211024160454/https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/rpt-mtrends-2016.pdf)
- [S0484 - Carberp](../../../../Threat%20Intelligence/Software/Malware/S0484%20-%20Carberp.md) — [Carberp](https://attack.mitre.org/software/S0484) has installed a bootkit on the system to maintain persistence.(Citation: ESET Carberp March 2012) [ESET Carberp March 2012](https://www.eset.com/fileadmin/eset/US/resources/docs/white-papers/white-papers-win-32-carberp.pdf)
- [S0182 - FinFisher](../../../../Threat%20Intelligence/Software/Malware/S0182%20-%20FinFisher.md) — Some [FinFisher](https://attack.mitre.org/software/S0182) variants incorporate an MBR rootkit.(Citation: FinFisher Citation)(Citation: Microsoft FinFisher March 2018) [Microsoft FinFisher March 2018](https://cloudblogs.microsoft.com/microsoftsecure/2018/03/01/finfisher-exposed-a-researchers-tale-of-defeating-traps-tricks-and-complex-virtual-machines/) · [FinFisher Citation](https://web.archive.org/web/20171222050934/http://www.finfisher.com/FinFisher/index.html)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) malware WhiskeyAlfa-Three modifies sector 0 of the Master Boot Record (MBR) to ensure that the malware will persist even if a victim machine shuts down.(Citation: Novetta Blockbuster)(Citation: Novetta Blockbuster Destructive Malware) [Novetta Blockbuster Destructive Malware](https://web.archive.org/web/20160303200515/https:/operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf) · [Novetta Blockbuster](https://web.archive.org/web/20160226161828/https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf)
- [S0112 - ROCKBOOT](../../../../Threat%20Intelligence/Software/Malware/S0112%20-%20ROCKBOOT.md) — [ROCKBOOT](https://attack.mitre.org/software/S0112) is a Master Boot Record (MBR) bootkit that uses the MBR to establish persistence.(Citation: FireEye Bootkits) [FireEye Bootkits](https://www.fireeye.com/blog/threat-research/2015/12/fin1-targets-boot-record.html)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) can implant malicious code into a compromised device's firmware.(Citation: Eclypsium Trickboot December 2020) [Eclypsium Trickboot December 2020](https://eclypsium.com/wp-content/uploads/2020/12/TrickBot-Now-Offers-TrickBoot-Persist-Brick-Profit.pdf)
- [S0689 - WhisperGate](../../../../Threat%20Intelligence/Software/Malware/S0689%20-%20WhisperGate.md) — [WhisperGate](https://attack.mitre.org/software/S0689) overwrites the MBR with a bootloader component that performs destructive wiping operations on hard drives and displays a fake ransom note when the host boots.(Citation: Crowdstrike WhisperGate January 2022)(Citation: Cybereason WhisperGate February 2022)(Citation: Microsoft WhisperGate January 2022)(Citation: Cisco Ukraine Wipers January 2022)(Citation: Medium S2W WhisperGate January 2022) [Cisco Ukraine Wipers January 2022](https://blog.talosintelligence.com/2022/01/ukraine-campaign-delivers-defacement.html) · [Crowdstrike WhisperGate January 2022](https://www.crowdstrike.com/blog/technical-analysis-of-whispergate-malware) · [Cybereason WhisperGate February 2022](https://www.cybereason.com/blog/cybereason-vs.-whispergate-wiper) · [Microsoft WhisperGate January 2022](https://www.microsoft.com/security/blog/2022/01/15/destructive-malware-targeting-ukrainian-organizations/) · [Medium S2W WhisperGate January 2022](https://medium.com/s2wblog/analysis-of-destructive-malware-whispergate-targeting-ukraine-9d5d158f19f3)

## Detection strategies

- [DET0150 - Detection Strategy for File Creation or Modification of Boot Files](../../../../Defenses/Detection%20Strategies/DET0150%20-%20Detection%20Strategy%20for%20File%20Creation%20or%20Modification%20of%20Boot%20Files.md)

## Mitigations

- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Use Trusted Platform Module technology and a secure or trusted boot process to prevent system integrity from being compromised.(Citation: TCG Trusted Platform Module)(Citation: TechNet Secure Boot Process) [TechNet Secure Boot Process](https://docs.microsoft.com/en-us/windows/security/information-protection/secure-the-windows-10-boot-process) · [TCG Trusted Platform Module](http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure proper permissions are in place to help prevent adversary access to privileged accounts necessary to install a bootkit.

## Sources

- [Lau 2011](http://www.symantec.com/connect/blogs/are-mbr-infections-back-fashion)
- [Mandiant M Trends 2016](https://web.archive.org/web/20211024160454/https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/rpt-mtrends-2016.pdf)
- [welivesecurity](https://www.welivesecurity.com/2023/03/01/blacklotus-uefi-bootkit-myth-confirmed/)
- [Microsoft Security](https://www.microsoft.com/en-us/security/blog/2023/04/11/guidance-for-investigating-attacks-using-cve-2022-21894-the-blacklotus-campaign/)
