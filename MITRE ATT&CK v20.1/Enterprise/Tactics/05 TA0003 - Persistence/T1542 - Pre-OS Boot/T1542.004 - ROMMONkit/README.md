# T1542.004 - ROMMONkit

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1542 - Pre-OS Boot](../README.md)

Adversaries may abuse the ROM Monitor (ROMMON) by loading an unauthorized firmware with adversary code to provide persistent access and manipulate device behavior that is difficult to detect.(Citation: Cisco Synful Knock Evolution)(Citation: Cisco Blog Legacy Device Attacks)


ROMMON is a Cisco network device firmware that functions as a boot loader, boot image, or boot helper to initialize hardware and software when the platform is powered on or reset. Similar to [TFTP Boot](https://attack.mitre.org/techniques/T1542/005), an adversary may upgrade the ROMMON image locally or remotely (for example, through TFTP) with adversary code and restart the device in order to overwrite the existing ROMMON image. This provides adversaries with the means to update the ROMMON to gain persistence on a system in a way that may be difficult to detect.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542/004)

**Tactics**  [Persistence](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically check the integrity of system image to ensure it has not been modified. (Citation: Cisco IOS Software Integrity Assurance - Image File Integrity) (Citation: Cisco IOS Software Integrity Assurance - Image File Verification) (Citation: Cisco IOS Software Integrity Assurance - Change Control) [Cisco IOS Software Integrity Assurance - Image File Integrity](https://tools.cisco.com/security/center/resources/integrity_assurance.html#30) · [Cisco IOS Software Integrity Assurance - Image File Verification](https://tools.cisco.com/security/center/resources/integrity_assurance.html#7) · [Cisco IOS Software Integrity Assurance - Change Control](https://tools.cisco.com/security/center/resources/integrity_assurance.html#31)
- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Enable secure boot features to validate the digital signature of the boot environment and system image using a special purpose hardware device. If the validation check fails, the device will fail to boot preventing loading of unauthorized software. (Citation: Cisco IOS Software Integrity Assurance - Secure Boot) [Cisco IOS Software Integrity Assurance - Secure Boot](https://tools.cisco.com/security/center/resources/integrity_assurance.html#35)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific protocols, such as TFTP, can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific technique used by a particular adversary or tool, and will likely be different across various network configurations.

## Detection strategies

- [DET0175 - Detection Strategy for T1542.004 Pre-OS Boot: ROMMONkit](../../../../Defenses/Detection%20Strategies/DET0175%20-%20Detection%20Strategy%20for%20T1542.004%20Pre-OS%20Boot%20-%20ROMMONkit.md)

## Sources

- [Cisco Synful Knock Evolution](https://blogs.cisco.com/security/evolution-of-attacks-on-cisco-ios-devices)
- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
