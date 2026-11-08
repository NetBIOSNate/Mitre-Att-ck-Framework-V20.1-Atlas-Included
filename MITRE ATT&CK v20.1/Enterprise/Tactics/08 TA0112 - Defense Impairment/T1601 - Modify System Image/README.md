# T1601 - Modify System Image

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may make changes to the operating system of embedded network devices to weaken defenses and provide new capabilities for themselves.  On such devices, the operating systems are typically monolithic and most of the device functionality and capabilities are contained within a single file.(Citation: Cisco Networking Software Product Lines)(Citation: Network Device Integrity Methodology)

To change the operating system, the adversary typically only needs to affect this one file, replacing or modifying it.  This can either be done live in memory during system runtime for immediate effect, or in storage to implement the change on the next boot of the network device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1601)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1601.002 - Downgrade System Image](T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1601.001 - Patch System Image](T1601.001%20-%20Patch%20System%20Image/README.md)

## Detection strategies

- [DET0170 - Detection Strategy for Modify System Image on Network Devices](../../../Defenses/Detection%20Strategies/DET0170%20-%20Detection%20Strategy%20for%20Modify%20System%20Image%20on%20Network%20Devices.md)

## Mitigations

- [M1046 - Boot Integrity](../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Some vendors of embedded network devices provide cryptographic signing to ensure the integrity of operating system images at boot time. Implement where available, following vendor guidelines. (Citation: Cisco IOS Software Integrity Assurance - Secure Boot) [Cisco IOS Software Integrity Assurance - Secure Boot](https://tools.cisco.com/security/center/resources/integrity_assurance.html#35)
- [M1045 - Code Signing](../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Many vendors provide digitally signed operating system images to validate the integrity of the software used on their platform. Make use of this feature where possible in order to prevent and/or detect attempts by adversaries to compromise the system image. (Citation: Cisco IOS Software Integrity Assurance - Deploy Signed IOS) [Cisco IOS Software Integrity Assurance - Deploy Signed IOS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#34)
- [M1043 - Credential Access Protection](../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — Some embedded network devices are capable of storing passwords for local accounts in either plain-text or encrypted formats. Ensure that, where available, local passwords are always encrypted, per vendor recommendations. (Citation: Cisco IOS Software Integrity Assurance - Credentials Management) [Cisco IOS Software Integrity Assurance - Credentials Management](https://tools.cisco.com/security/center/resources/integrity_assurance.html#40)
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Most embedded network devices support TACACS+ and/or RADIUS. Follow vendor prescribed best practices for hardening access control.(Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles. Prevent credential overlap across systems of administrator and privileged accounts, particularly between network and non-network platforms, such as servers or endpoints.

## Procedure examples

- [S9013 - DRYHOOK](../../../Threat%20Intelligence/Software/Malware/S9013%20-%20DRYHOOK.md) — [DRYHOOK](https://attack.mitre.org/software/S9013) has modified the Ivanti Connect Secure VPN authentication Perl module `DSAuth.pm` by reading its contents in the buffer, then finding and replacing select lines of code.(Citation: Google UNC5221 Ivanti January 2025)(Citation: Picus Security UNC5221 Ivanti May 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day) · [Picus Security UNC5221 Ivanti May 2025](https://www.picussecurity.com/resource/blog/unc5221-cve-2025-22457-ivanti-connect-secure)

## Sources

- [Cisco Networking Software Product Lines](https://www.cisco.com/c/en/us/support/ios-nx-os-software/index.html#GUID-CCB80DF4-C5E7-4543-A3D2-598EF13E5FCA)
- [Network Device Integrity Methodology](https://media.defense.gov/2023/Oct/06/2003315573/-1/-1/0/NETWORK%20DEVICE%20INTEGRITY%20NDI%20METHODOLOGY.PDF)
