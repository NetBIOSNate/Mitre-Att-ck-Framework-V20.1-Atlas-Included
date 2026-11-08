# T1495 - Firmware Corruption

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may overwrite or corrupt the flash memory contents of system BIOS or other firmware in devices attached to a system in order to render them inoperable or unable to boot, thus denying the availability to use the devices and/or the system.(Citation: Symantec Chernobyl W95.CIH) Firmware is software that is loaded and executed from non-volatile memory on hardware devices in order to initialize and manage device functionality. These devices may include the motherboard, hard drive, or video cards.

In general, adversaries may manipulate, overwrite, or corrupt firmware in order to deny the use of the system or devices. For example, corruption of firmware responsible for loading the operating system for network devices may render the network devices inoperable.(Citation: dhs_threat_to_net_devices)(Citation: cisa_malware_orgs_ukraine) Depending on the device, this attack may also result in [Data Destruction](https://attack.mitre.org/techniques/T1485).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1495)

**Tactics**  [Impact](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), adversaries performed a factory-reset on compromised devices that hampered forensic investigations.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0606 - Bad Rabbit](../../../Threat%20Intelligence/Software/Malware/S0606%20-%20Bad%20Rabbit.md) — [Bad Rabbit](https://attack.mitre.org/software/S0606) has used an executable that installs a modified bootloader to prevent normal boot-up.(Citation: Secure List Bad Rabbit) [Secure List Bad Rabbit](https://securelist.com/bad-rabbit-ransomware/82851/)
- [S0266 - TrickBot](../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) module "Trickboot" can write or erase the UEFI/BIOS firmware of a compromised device.(Citation: Eclypsium Trickboot December 2020) [Eclypsium Trickboot December 2020](https://eclypsium.com/wp-content/uploads/2020/12/TrickBot-Now-Offers-TrickBoot-Persist-Brick-Profit.pdf)

## Mitigations

- [M1046 - Boot Integrity](../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Check the integrity of the existing BIOS and device firmware to determine if it is vulnerable to modification.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Prevent adversary access to privileged accounts or access necessary to replace system firmware.
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Patch the BIOS and other firmware as necessary to prevent successful use of known vulnerabilities.

## Detection strategies

- [DET0167 - Firmware Modification via Flash Tool or Corrupted Firmware Upload](../../../Defenses/Detection%20Strategies/DET0167%20-%20Firmware%20Modification%20via%20Flash%20Tool%20or%20Corrupted%20Firmware%20Upload.md)

## Sources

- [cisa_malware_orgs_ukraine](https://www.cisa.gov/uscert/ncas/alerts/aa22-057a)
- [dhs_threat_to_net_devices](https://cyber.dhs.gov/assets/report/ar-16-20173.pdf)
- [MITRE Trustworthy Firmware Measurement](http://www.mitre.org/publications/project-stories/going-deep-into-the-bios-with-mitre-firmware-security-research)
- [Symantec Chernobyl W95.CIH](https://web.archive.org/web/20190508170055/https://www.symantec.com/security-center/writeup/2000-122010-2655-99)
