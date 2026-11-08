# T1553.006 - Code Signing Policy Modification

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1553 - Subvert Trust Controls](../README.md)

Adversaries may modify code signing policies to enable execution of unsigned or self-signed code. Code signing provides a level of authenticity on a program from a developer and a guarantee that the program has not been tampered with. Security controls can include enforcement mechanisms to ensure that only valid, signed code can be run on an operating system. 

Some of these security controls may be enabled by default, such as Driver Signature Enforcement (DSE) on Windows or System Integrity Protection (SIP) on macOS.(Citation: Microsoft DSE June 2017)(Citation: Apple Disable SIP) Other such controls may be disabled by default but are configurable through application controls, such as only allowing signed Dynamic-Link Libraries (DLLs) to execute on a system. Since it can be useful for developers to modify default signature enforcement policies during the development and testing of applications, disabling of these features may be possible with elevated permissions.(Citation: Microsoft Unsigned Driver Apr 2017)(Citation: Apple Disable SIP)

Adversaries may modify code signing policies in a number of ways, including through use of command-line or GUI utilities, [Modify Registry](https://attack.mitre.org/techniques/T1112), rebooting the computer in a debug/recovery mode, or by altering the value of variables in kernel memory.(Citation: Microsoft TESTSIGNING Feb 2021)(Citation: Apple Disable SIP)(Citation: FireEye HIKIT Rootkit Part 2)(Citation: GitHub Turla Driver Loader) Examples of commands that can modify the code signing policy of a system include <code>bcdedit.exe -set TESTSIGNING ON</code> on Windows and <code>csrutil disable</code> on macOS.(Citation: Microsoft TESTSIGNING Feb 2021)(Citation: Apple Disable SIP) Depending on the implementation, successful modification of a signing policy may require reboot of the compromised system. Additionally, some implementations can introduce visible artifacts for the user (ex: a watermark in the corner of the screen stating the system is in Test Mode). Adversaries may attempt to remove such artifacts.(Citation: F-Secure BlackEnergy 2014)

To gain access to kernel memory to modify variables related to signature checks, such as modifying <code>g_CiOptions</code> to disable Driver Signature Enforcement, adversaries may conduct [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T1068) using a signed, but vulnerable driver.(Citation: Unit42 AcidBox June 2020)(Citation: GitHub Turla Driver Loader)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1553/006)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0087 - APT39](../../../../Threat%20Intelligence/Groups/G0087%20-%20APT39.md) — [APT39](https://attack.mitre.org/groups/G0087) has used malware to turn off the <code>RequireSigned</code> feature which ensures only signed DLLs can be run on Windows.(Citation: FBI FLASH APT39 September 2020) [FBI FLASH APT39 September 2020](https://www.iranwatch.org/sites/default/files/public-intelligence-alert.pdf)
- [S0089 - BlackEnergy](../../../../Threat%20Intelligence/Software/Malware/S0089%20-%20BlackEnergy.md) — [BlackEnergy](https://attack.mitre.org/software/S0089) has enabled the <code>TESTSIGNING</code> boot configuration option to facilitate loading of a driver component.(Citation: F-Secure BlackEnergy 2014) [F-Secure BlackEnergy 2014](https://blog-assets.f-secure.com/wp-content/uploads/2019/10/15163408/BlackEnergy_Quedagh.pdf)
- [S0009 - Hikit](../../../../Threat%20Intelligence/Software/Malware/S0009%20-%20Hikit.md) — [Hikit](https://attack.mitre.org/software/S0009) has attempted to disable driver signing verification by tampering with several Registry keys prior to the loading of a rootkit driver component.(Citation: FireEye HIKIT Rootkit Part 2) [FireEye HIKIT Rootkit Part 2](https://web.archive.org/web/20210920172620/https://www.fireeye.com/blog/threat-research/2012/08/hikit-rootkit-advanced-persistent-attack-techniques-part-2.html)
- [S0664 - Pandora](../../../../Threat%20Intelligence/Software/Malware/S0664%20-%20Pandora.md) — [Pandora](https://attack.mitre.org/software/S0664) can use CVE-2017-15303 to disable Windows Driver Signature Enforcement (DSE) protection and load its driver.(Citation: Trend Micro Iron Tiger April 2021) [Trend Micro Iron Tiger April 2021](https://www.trendmicro.com/en_us/research/21/d/iron-tiger-apt-updates-toolkit-with-evolved-sysupdate-malware-va.html)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has modified variables in kernel memory to turn off Driver Signature Enforcement after exploiting vulnerabilities that obtained kernel mode privileges.(Citation: Unit42 AcidBox June 2020)(Citation: GitHub Turla Driver Loader) [Unit42 AcidBox June 2020](https://unit42.paloaltonetworks.com/acidbox-rare-malware/) · [GitHub Turla Driver Loader](https://github.com/hfiref0x/TDL)

## Mitigations

- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Use of Secure Boot may prevent some implementations of modification to code signing policies.(Citation: Microsoft TESTSIGNING Feb 2021) [Microsoft TESTSIGNING Feb 2021](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/the-testsigning-boot-configuration-option)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the usage of local administrator and domain administrator accounts to be used for day-to-day operations that may expose them to potential adversaries.
- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper permissions are set for the Registry to prevent users from modifying keys related to code signing policies.

## Detection strategies

- [DET0523 - Detect Code Signing Policy Modification (Windows & macOS)](../../../../Defenses/Detection%20Strategies/DET0523%20-%20Detect%20Code%20Signing%20Policy%20Modification%20%28Windows%20%26%20macOS%29.md)

## Sources

- [Apple Disable SIP](https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection)
- [F-Secure BlackEnergy 2014](https://blog-assets.f-secure.com/wp-content/uploads/2019/10/15163408/BlackEnergy_Quedagh.pdf)
- [FireEye HIKIT Rootkit Part 2](https://web.archive.org/web/20210920172620/https://www.fireeye.com/blog/threat-research/2012/08/hikit-rootkit-advanced-persistent-attack-techniques-part-2.html)
- [Microsoft Unsigned Driver Apr 2017](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/installing-an-unsigned-driver-during-development-and-test)
- [Microsoft DSE June 2017](https://docs.microsoft.com/en-us/previous-versions/windows/hardware/design/dn653559%28v=vs.85%29?redirectedfrom=MSDN)
- [Microsoft TESTSIGNING Feb 2021](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/the-testsigning-boot-configuration-option)
- [Unit42 AcidBox June 2020](https://unit42.paloaltonetworks.com/acidbox-rare-malware/)
- [GitHub Turla Driver Loader](https://github.com/hfiref0x/TDL)
