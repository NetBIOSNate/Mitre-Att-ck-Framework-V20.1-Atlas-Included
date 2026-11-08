# M0930 - Network Segmentation

[ICS](../../README.md) / [Mitigations](README.md)

Architect sections of the network to isolate critical systems, functions, or resources. Use physical and logical segmentation to prevent access to potentially sensitive systems and information. Use a DMZ to contain any internet-facing services that should not be exposed from the internal network.  Restrict network access to only required systems and services. In addition, prevent systems from other networks or business functions (e.g., enterprise) from accessing critical process control systems. For example, in IEC 62443, systems within the same secure level should be grouped into a zone, and access to that zone is restricted by a conduit, or mechanism to restrict data flows between zones by segmenting the network. (Citation: IEC February 2019) (Citation: IEC August 2013)

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0930)

## Mitigated techniques

- [T0800 - Activate Firmware Update Mode](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0800%20-%20Activate%20Firmware%20Update%20Mode/README.md)
- [T0830 - Adversary-in-the-Middle](../../Tactics/08%20TA0100%20-%20Collection/T0830%20-%20Adversary-in-the-Middle/README.md)
- [T0878 - Alarm Suppression](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0878%20-%20Alarm%20Suppression/README.md)
- [T0802 - Automated Collection](../../Tactics/08%20TA0100%20-%20Collection/T0802%20-%20Automated%20Collection/README.md)
- [T1695 - Block Communications](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/README.md)
- [T0846.002 - Broadcast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.002%20-%20Broadcast%20Discovery/README.md)
- [T0806 - Brute Force I/O](../../Tactics/11%20TA0106%20-%20Impair%20Process%20Control/T0806%20-%20Brute%20Force%20I%20-%20O/README.md)
- [T0858 - Change Operating Mode](../../Tactics/02%20TA0104%20-%20Execution/T0858%20-%20Change%20Operating%20Mode/README.md)
- [T1692.001 - Command Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.001%20-%20Command%20Message/README.md)
- [T0885 - Commonly Used Port](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0885%20-%20Commonly%20Used%20Port/README.md)
- [T0868 - Detect Operating Mode](../../Tactics/08%20TA0100%20-%20Collection/T0868%20-%20Detect%20Operating%20Mode/README.md)
- [T0816 - Device Restart/Shutdown](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0816%20-%20Device%20Restart%20-%20Shutdown/README.md)
- [T0843.001 - Download All](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.001%20-%20Download%20All/README.md)
- [T1695.002 - Ethernet](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.002%20-%20Ethernet/README.md)
- [T0819 - Exploit Public-Facing Application](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0819%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T0866 - Exploitation of Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0866%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T0822 - External Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0822%20-%20External%20Remote%20Services/README.md)
- [T0883 - Internet Accessible Device](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0883%20-%20Internet%20Accessible%20Device/README.md)
- [T0838 - Modify Alarm Settings](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0838%20-%20Modify%20Alarm%20Settings/README.md)
- [T1693 - Modify Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/README.md)
- [T1693.002 - Module Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.002%20-%20Module%20Firmware/README.md)
- [T0846.003 - Multicast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.003%20-%20Multicast%20Discovery/README.md)
- [T0842 - Network Sniffing](../../Tactics/06%20TA0102%20-%20Discovery/T0842%20-%20Network%20Sniffing/README.md)
- [T0843.002 - Online Edit](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.002%20-%20Online%20Edit/README.md)
- [T0861 - Point & Tag Identification](../../Tactics/08%20TA0100%20-%20Collection/T0861%20-%20Point%20%26%20Tag%20Identification/README.md)
- [T0846.001 - Port Scan](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.001%20-%20Port%20Scan/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0843 - Program Download](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/README.md)
- [T0845 - Program Upload](../../Tactics/08%20TA0100%20-%20Collection/T0845%20-%20Program%20Upload/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T1692.002 - Reporting Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.002%20-%20Reporting%20Message/README.md)
- [T0848 - Rogue Master](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0848%20-%20Rogue%20Master/README.md)
- [T1695.001 - Serial COM](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.001%20-%20Serial%20COM/README.md)
- [T0881 - Service Stop](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0881%20-%20Service%20Stop/README.md)
- [T0869 - Standard Application Layer Protocol](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0869%20-%20Standard%20Application%20Layer%20Protocol/README.md)
- [T1693.001 - System Firmware](../../Tactics/03%20TA0110%20-%20Persistence/T1693%20-%20Modify%20Firmware/T1693.001%20-%20System%20Firmware/README.md)
- [T0864 - Transient Cyber Asset](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0864%20-%20Transient%20Cyber%20Asset/README.md)
- [T1692 - Unauthorized Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/README.md)
- [T1695.003 - Wi-Fi](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1695%20-%20Block%20Communications/T1695.003%20-%20Wi-Fi/README.md)

## Sources

- [IEC August 2013](https://webstore.iec.ch/publication/7033)
- [IEC February 2019](https://webstore.iec.ch/publication/34421)
