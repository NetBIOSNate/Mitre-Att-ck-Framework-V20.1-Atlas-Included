# M0807 - Network Allowlists

[ICS](../../README.md) / [Mitigations](README.md)

Network allowlists can be implemented through either host-based files or system hosts files to specify what connections (e.g., IP address, MAC address, port, protocol) can be made from a device. Allowlist techniques that operate at the  application layer (e.g., DNP3, Modbus, HTTP) are addressed in [Filter Network Traffic](https://attack.mitre.org/mitigations/M0937) mitigation.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0807)

## Mitigated techniques

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0878 - Alarm Suppression](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0878%20-%20Alarm%20Suppression/README.md)
- [T0802 - Automated Collection](../../Tactics/08%20TA0100%20-%20Collection/T0802%20-%20Automated%20Collection/README.md)
- [T1695 - Block Communications](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/README.md)
- [T1691 - Block Operational Technology Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/README.md)
- [T0806 - Brute Force I/O](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0806%20-%20Brute%20Force%20I%20-%20O/README.md)
- [T0858 - Change Operating Mode](../../Tactics/02%20TA0104%20-%20Execution/T0858%20-%20Change%20Operating%20Mode/README.md)
- [T1691.001 - Command Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.001%20-%20Command%20Message/README.md)
- [T1692.001 - Command Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.001%20-%20Command%20Message/README.md)
- [T0884 - Connection Proxy](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0884%20-%20Connection%20Proxy/README.md)
- [T0879 - Damage to Property](../../Tactics/12%20TA0105%20-%20Impact/T0879%20-%20Damage%20to%20Property/README.md)
- [T0868 - Detect Operating Mode](../../Tactics/08%20TA0100%20-%20Collection/T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0843.001 - Download All](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.001%20-%20Download%20All/README.md)
- [T1695.002 - Ethernet](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.002%20-%20Ethernet/README.md)
- [T0838 - Modify Alarm Settings](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0838%20-%20Modify%20Alarm%20Settings/README.md)
- [T1693 - Modify Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/README.md)
- [T1693.002 - Module Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.002%20-%20Module%20Firmware/README.md)
- [T0843.002 - Online Edit](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.002%20-%20Online%20Edit/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0843 - Program Download](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/README.md)
- [T0845 - Program Upload](../../Tactics/08%20TA0100%20-%20Collection/T0845%20-%20Program%20Upload/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T1691.002 - Reporting Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.002%20-%20Reporting%20Message/README.md)
- [T1692.002 - Reporting Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.002%20-%20Reporting%20Message/README.md)
- [T0848 - Rogue Master](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0848%20-%20Rogue%20Master/README.md)
- [T1695.001 - Serial COM](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.001%20-%20Serial%20COM/README.md)
- [T0869 - Standard Application Layer Protocol](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)
- [T1692 - Unauthorized Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/README.md)
- [T1695.003 - Wi-Fi](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.003%20-%20Wi-Fi/README.md)
