# M0800 - Authorization Enforcement

[ICS](../../README.md) / [Mitigations](README.md)

The device or system should restrict read, manipulate, or execute privileges to only authenticated users who require access based on approved security policies.  Role-based Access Control (RBAC) schemes can help reduce the overhead of assigning permissions to the large number of devices within an ICS. For example, IEC 62351 provides examples of roles used to support common system operations within the electric power sector  (Citation: International Electrotechnical Commission July 2020), while IEEE 1686 defines standard permissions for users of IEDs. (Citation: Institute of Electrical and Electronics Engineers January 2014)

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0800)

## Mitigated techniques

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0858 - Change Operating Mode](../../Tactics/02%20TA0104%20-%20Execution/T0858%20-%20Change%20Operating%20Mode/README.md)
- [T0868 - Detect Operating Mode](../../Tactics/08%20TA0100%20-%20Collection/T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0843.001 - Download All](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.001%20-%20Download%20All/README.md)
- [T0871 - Execution through API](../../Tactics/02%20TA0104%20-%20Execution/T0871%20-%20Execution%20through%20API/README.md)
- [T0838 - Modify Alarm Settings](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0838%20-%20Modify%20Alarm%20Settings/README.md)
- [T0821 - Modify Controller Tasking](../../Tactics/02%20TA0104%20-%20Execution/T0821%20-%20Modify%20Controller%20Tasking/README.md)
- [T0836 - Modify Parameter](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0836%20-%20Modify%20Parameter/README.md)
- [T0889 - Modify Program](../../Tactics/03%20TA0110%20-%20Persistence/T0889%20-%20Modify%20Program/README.md)
- [T0843.002 - Online Edit](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.002%20-%20Online%20Edit/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0843 - Program Download](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/README.md)
- [T0845 - Program Upload](../../Tactics/08%20TA0100%20-%20Collection/T0845%20-%20Program%20Upload/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)

## Sources

- [Institute of Electrical and Electronics Engineers January 2014](https://standards.ieee.org/standard/1686-2013.html)
- [International Electrotechnical Commission July 2020](https://webstore.iec.ch/publication/6912)
