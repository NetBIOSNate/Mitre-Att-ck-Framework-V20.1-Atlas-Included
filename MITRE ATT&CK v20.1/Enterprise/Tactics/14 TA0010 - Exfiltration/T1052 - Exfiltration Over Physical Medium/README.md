# T1052 - Exfiltration Over Physical Medium

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may attempt to exfiltrate data via a physical medium, such as a removable drive. In certain circumstances, such as an air-gapped network compromise, exfiltration could occur via a physical medium or device introduced by a user. Such media could be an external hard drive, USB drive, cellular phone, MP3 player, or other removable storage and processing device. The physical medium or device could be used as the final exfiltration point or to hop between otherwise disconnected systems.(Citation: USB Drives Threaten Enterprise Security)(Citation: Tropic Trooper’s USBferry)(Citation: APT37 Adds New Capabilities for Air-Gapped Networks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1052)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1052.001 - Exfiltration over USB](T1052.001%20-%20Exfiltration%20over%20USB/README.md)

## Mitigations

- [M1057 - Data Loss Prevention](../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can detect and block sensitive data being copied to physical mediums.
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable Autorun if it is unnecessary. (Citation: Microsoft Disable Autorun) Disallow or restrict removable media at an organizational policy level if they are not required for business operations. (Citation: TechNet Removable Media Control) [Microsoft Disable Autorun](https://support.microsoft.com/en-us/kb/967715) · [TechNet Removable Media Control](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx)
- [M1034 - Limit Hardware Installation](../../../Defenses/Mitigations/M1034%20-%20Limit%20Hardware%20Installation.md) — Limit the use of USB devices and removable media within a network.

## Detection strategies

- [DET0123 - Detection of Data Exfiltration via Removable Media](../../../Defenses/Detection%20Strategies/DET0123%20-%20Detection%20of%20Data%20Exfiltration%20via%20Removable%20Media.md)

## Sources

- [USB Drives Threaten Enterprise Security](https://www.crowdstrike.com/en-us/blog/usb-drives-threaten-enterprise-security/)
- [Tropic Trooper’s USBferry](https://www.trendmicro.com/en_us/research/20/e/tropic-troopers-back-usbferry-attack-targets-air-gapped-environments.html)
- [APT37 Adds New Capabilities for Air-Gapped Networks](https://www.zscaler.com/blogs/security-research/apt37-adds-new-capabilities-air-gapped-networks)
