# T1011.001 - Exfiltration Over Bluetooth

[Enterprise](../../../../README.md) / [Exfiltration](../../README.md) / [T1011 - Exfiltration Over Other Network Medium](../README.md)

Adversaries may attempt to exfiltrate data over Bluetooth rather than the command and control channel. If the command and control network is a wired Internet connection, an adversary may opt to exfiltrate data using a Bluetooth communication channel.

Adversaries may choose to do this if they have sufficient access and proximity. Bluetooth connections might not be secured or defended as well as the primary Internet-connected channel because it is not routed through the same enterprise network.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1011/001)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0143 - Flame](../../../../Threat%20Intelligence/Software/Malware/S0143%20-%20Flame.md) — [Flame](https://attack.mitre.org/software/S0143) has a module named BeetleJuice that contains Bluetooth functionality that may be used in different ways, including transmitting encoded information from the infected system over the Bluetooth protocol, acting as a Bluetooth beacon, and identifying other Bluetooth devices in the vicinity.(Citation: Symantec Beetlejuice) [Symantec Beetlejuice](https://web.archive.org/web/20120604050149/https://www.symantec.com/connect/blogs/flamer-recipe-bluetoothache)

## Detection strategies

- [DET0554 - Detection of Bluetooth-Based Data Exfiltration](../../../../Defenses/Detection%20Strategies/DET0554%20-%20Detection%20of%20Bluetooth-Based%20Data%20Exfiltration.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable Bluetooth in local computer security settings or by group policy if it is not needed within an environment.
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Prevent the creation of new network adapters where possible.
