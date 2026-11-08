# M0804 - Human User Authentication

[ICS](../../README.md) / [Mitigations](README.md)

Require user authentication before allowing access to data or accepting commands to a device. While strong multi-factor authentication is preferable, it is not always feasible within ICS environments. Performing strong user authentication also requires additional security controls and processes which are often the target of related adversarial techniques (e.g., Valid Accounts, Default Credentials). Therefore, associated ATT&CK mitigations should be considered in addition to this, including [Multi-factor Authentication](https://attack.mitre.org/mitigations/M0932), [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), [User Account Management](https://attack.mitre.org/mitigations/M0918), [Privileged Account Management](https://attack.mitre.org/mitigations/M0926), and [User Account Control](https://attack.mitre.org/mitigations/M1052).

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0804)

## Mitigated techniques

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0858 - Change Operating Mode](../../Tactics/02%20TA0104%20-%20Execution/T0858%20-%20Change%20Operating%20Mode/README.md)
- [T0885 - Commonly Used Port](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0885%20-%20Commonly%20Used%20Port/README.md)
- [T0868 - Detect Operating Mode](../../Tactics/08%20TA0100%20-%20Collection/T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0843.001 - Download All](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.001%20-%20Download%20All/README.md)
- [T0871 - Execution through API](../../Tactics/02%20TA0104%20-%20Execution/T0871%20-%20Execution%20through%20API/README.md)
- [T0838 - Modify Alarm Settings](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0838%20-%20Modify%20Alarm%20Settings/README.md)
- [T0821 - Modify Controller Tasking](../../Tactics/02%20TA0104%20-%20Execution/T0821%20-%20Modify%20Controller%20Tasking/README.md)
- [T1693 - Modify Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/README.md)
- [T0836 - Modify Parameter](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0836%20-%20Modify%20Parameter/README.md)
- [T0889 - Modify Program](../../Tactics/03%20TA0110%20-%20Persistence/T0889%20-%20Modify%20Program/README.md)
- [T1693.002 - Module Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.002%20-%20Module%20Firmware/README.md)
- [T0843.002 - Online Edit](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.002%20-%20Online%20Edit/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0843 - Program Download](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/README.md)
- [T0845 - Program Upload](../../Tactics/08%20TA0100%20-%20Collection/T0845%20-%20Program%20Upload/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)
