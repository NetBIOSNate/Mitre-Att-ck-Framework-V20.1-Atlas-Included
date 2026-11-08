# G0071 - Orangeworm

[Enterprise](../../README.md) / [Groups](README.md)

[Orangeworm](https://attack.mitre.org/groups/G0071) is a group that has targeted organizations in the healthcare sector in the United States, Europe, and Asia since at least 2015, likely for the purpose of corporate espionage.(Citation: Symantec Orangeworm April 2018) Reverse engineering of [Kwampirs](https://attack.mitre.org/software/S0236), directly associated with [Orangeworm](https://attack.mitre.org/groups/G0071) activity, indicates significant functional and development overlaps with [Shamoon](https://attack.mitre.org/software/S0140).(Citation: Cylera Kwampirs 2022)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0071)

## Techniques used

- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Software used

- [S0099 - Arp](../Software/Tools/S0099%20-%20Arp.md)
- [S0106 - cmd](../Software/Tools/S0106%20-%20cmd.md)
- [S0100 - ipconfig](../Software/Tools/S0100%20-%20ipconfig.md)
- [S0236 - Kwampirs](../Software/Malware/S0236%20-%20Kwampirs.md)
- [S0039 - Net](../Software/Tools/S0039%20-%20Net.md)
- [S0104 - netstat](../Software/Tools/S0104%20-%20netstat.md)
- [S0103 - route](../Software/Tools/S0103%20-%20route.md)
- [S0096 - Systeminfo](../Software/Tools/S0096%20-%20Systeminfo.md)

## Sources

- [Cylera Kwampirs 2022](https://resources.cylera.com/hubfs/Cylera%20Labs/Cylera%20Labs%20Kwampirs%20Shamoon%20Technical%20Report.pdf)
- [Symantec Orangeworm April 2018](https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia)
