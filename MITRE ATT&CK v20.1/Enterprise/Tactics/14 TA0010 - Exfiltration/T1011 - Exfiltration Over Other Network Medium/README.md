# T1011 - Exfiltration Over Other Network Medium

[Enterprise](../../../README.md) / [Exfiltration](../README.md)

Adversaries may attempt to exfiltrate data over a different network medium than the command and control channel. If the command and control network is a wired Internet connection, the exfiltration may occur, for example, over a WiFi connection, modem, cellular data connection, Bluetooth, or another radio frequency (RF) channel.

Adversaries may choose to do this if they have sufficient access or proximity, and the connection might not be secured or defended as well as the primary Internet-connected channel because it is not routed through the same enterprise network.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1011)

**Tactics**  [Exfiltration](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1011.001 - Exfiltration Over Bluetooth](T1011.001%20-%20Exfiltration%20Over%20Bluetooth/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable WiFi connection, modem, cellular data connection, Bluetooth, or another radio frequency (RF) channel in local computer security settings or by group policy if it is not needed within an environment.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Prevent the creation of new network adapters where possible.(Citation: Microsoft GPO Bluetooth FEB 2009)(Citation: TechRepublic Wireless GPO FEB 2009) [Microsoft GPO Bluetooth FEB 2009](https://technet.microsoft.com/library/dd252791.aspx) · [TechRepublic Wireless GPO FEB 2009](https://www.techrepublic.com/blog/data-center/configuring-wireless-settings-via-group-policy/)

## Detection strategies

- [DET0077 - Detection of Exfiltration Over Alternate Network Interfaces](../../../Defenses/Detection%20Strategies/DET0077%20-%20Detection%20of%20Exfiltration%20Over%20Alternate%20Network%20Interfaces.md)
