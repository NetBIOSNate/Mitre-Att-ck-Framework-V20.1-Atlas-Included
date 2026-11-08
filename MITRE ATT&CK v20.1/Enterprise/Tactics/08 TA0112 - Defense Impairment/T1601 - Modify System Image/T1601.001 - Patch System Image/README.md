# T1601.001 - Patch System Image

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1601 - Modify System Image](../README.md)

Adversaries may modify the operating system of a network device to introduce new capabilities or weaken existing defenses.(Citation: Killing the myth of Cisco IOS rootkits)(Citation: Killing IOS diversity myth)(Citation: Cisco IOS Shellcode)(Citation: Cisco IOS Forensics Developments)(Citation: Juniper Netscreen of the Dead) Some network devices are built with a monolithic architecture, where the entire operating system and most of the functionality of the device is contained within a single file.  Adversaries may change this file in storage, to be loaded in a future boot, or in memory during runtime.

To change the operating system in storage, the adversary will typically use the standard procedures available to device operators. This may involve downloading a new file via typical protocols used on network devices, such as TFTP, FTP, SCP, or a console connection.  The original file may be overwritten, or a new file may be written alongside of it and the device reconfigured to boot to the compromised image.

To change the operating system in memory, the adversary typically can use one of two methods. In the first, the adversary would make use of native debug commands in the original, unaltered running operating system that allow them to directly modify the relevant memory addresses containing the running operating system.  This method typically requires administrative level access to the device.

In the second method for changing the operating system in memory, the adversary would make use of the boot loader. The boot loader is the first piece of software that loads when the device starts that, in turn, will launch the operating system.  Adversaries may use malicious code previously implanted in the boot loader, such as through the [ROMMONkit](https://attack.mitre.org/techniques/T1542/004) method, to directly manipulate running operating system code in memory.  This malicious code in the bootloader provides the capability of direct memory manipulation to the adversary, allowing them to patch the live operating system during runtime.

By modifying the instructions stored in the system image file, adversaries may either weaken existing defenses or provision new capabilities that the device did not have before. Examples of existing defenses that can be impeded include encryption, via [Weaken Encryption](https://attack.mitre.org/techniques/T1600), authentication, via [Network Device Authentication](https://attack.mitre.org/techniques/T1556/004), and perimeter defenses, via [Network Boundary Bridging](https://attack.mitre.org/techniques/T1599).  Adding new capabilities for the adversary’s purpose include [Keylogging](https://attack.mitre.org/techniques/T1056/001), [Multi-hop Proxy](https://attack.mitre.org/techniques/T1090/003), and [Port Knocking](https://attack.mitre.org/techniques/T1205/001).

Adversaries may also compromise existing commands in the operating system to produce false output to mislead defenders.   When this method is used in conjunction with [Downgrade System Image](https://attack.mitre.org/techniques/T1601/002), one example of a compromised system command may include changing the output of the command that shows the version of the currently running operating system.  By patching the operating system, the adversary can change this command to instead display the original, higher revision number that they replaced through the system downgrade. 

When the operating system is patched in storage, this can be achieved in either the resident storage (typically a form of flash memory, which is non-volatile) or via [TFTP Boot](https://attack.mitre.org/techniques/T1542/005). 

When the technique is performed on the running operating system in memory and not on the stored copy, this technique will not survive across reboots.  However, live memory modification of the operating system can be combined with [ROMMONkit](https://attack.mitre.org/techniques/T1542/004) to achieve persistence.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1601/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [S0519 - SYNful Knock](../../../../Threat%20Intelligence/Software/Malware/S0519%20-%20SYNful%20Knock.md) — [SYNful Knock](https://attack.mitre.org/software/S0519) is malware that is inserted into a network device by patching the operating system image.(Citation: Mandiant - Synful Knock)(Citation: Cisco Synful Knock Evolution) [Mandiant - Synful Knock](https://cloud.google.com/blog/topics/threat-intelligence/synful-knock-acis/) · [Cisco Synful Knock Evolution](https://blogs.cisco.com/security/evolution-of-attacks-on-cisco-ios-devices)

## Mitigations

- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Some vendors of embedded network devices provide cryptographic signing to ensure the integrity of operating system images at boot time. Implement where available, following vendor guidelines. (Citation: Cisco IOS Software Integrity Assurance - Secure Boot) [Cisco IOS Software Integrity Assurance - Secure Boot](https://tools.cisco.com/security/center/resources/integrity_assurance.html#35)
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Many vendors provide digitally signed operating system images to validate the integrity of the software used on their platform. Make use of this feature where possible in order to prevent and/or detect attempts by adversaries to compromise the system image. (Citation: Cisco IOS Software Integrity Assurance - Deploy Signed IOS) [Cisco IOS Software Integrity Assurance - Deploy Signed IOS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#34)
- [M1043 - Credential Access Protection](../../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — Some embedded network devices are capable of storing passwords for local accounts in either plain-text or encrypted formats. Ensure that, where available, local passwords are always encrypted, per vendor recommendations. (Citation: Cisco IOS Software Integrity Assurance - Credentials Management) [Cisco IOS Software Integrity Assurance - Credentials Management](https://tools.cisco.com/security/center/resources/integrity_assurance.html#40)
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Most embedded network devices support TACACS+ and/or RADIUS. Follow vendor prescribed best practices for hardening access control.(Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles. Prevent credential overlap across systems of administrator and privileged accounts, particularly between network and non-network platforms, such as servers or endpoints.

## Detection strategies

- [DET0469 - Detection Strategy for Patch System Image on Network Devices](../../../../Defenses/Detection%20Strategies/DET0469%20-%20Detection%20Strategy%20for%20Patch%20System%20Image%20on%20Network%20Devices.md)

## Sources

- [Killing IOS diversity myth](https://www.usenix.org/legacy/event/woot/tech/final_files/Cui.pdf)
- [Cisco IOS Forensics Developments](https://www.recurity-labs.com/research/RecurityLabs_Developments_in_IOS_Forensics.pdf)
- [Cisco IOS Shellcode](http://2015.zeronights.org/assets/files/05-Nosenko.pdf)
- [Juniper Netscreen of the Dead](https://www.blackhat.com/presentations/bh-usa-09/NEILSON/BHUSA09-Neilson-NetscreenDead-SLIDES.pdf)
- [Killing the myth of Cisco IOS rootkits](https://drwho.virtadpt.net/images/killing_the_myth_of_cisco_ios_rootkits.pdf)
