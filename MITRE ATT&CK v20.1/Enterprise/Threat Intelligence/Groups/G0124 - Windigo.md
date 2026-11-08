# G0124 - Windigo

[Enterprise](../../README.md) / [Groups](README.md)

The [Windigo](https://attack.mitre.org/groups/G0124) group has been operating since at least 2011, compromising thousands of Linux and Unix servers using the [Ebury](https://attack.mitre.org/software/S0377) SSH backdoor to create a spam botnet. Despite law enforcement intervention against the creators, [Windigo](https://attack.mitre.org/groups/G0124) operators continued updating [Ebury](https://attack.mitre.org/software/S0377) through 2019.(Citation: ESET Windigo Mar 2014)(Citation: CERN Windigo June 2019)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0124)

## Techniques used

- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1518 - Software Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)

## Software used

- [S0377 - Ebury](../Software/Malware/S0377%20-%20Ebury.md)

## Sources

- [ESET Windigo Mar 2014](https://www.welivesecurity.com/2014/03/18/operation-windigo-the-vivisection-of-a-large-linux-server-side-credential-stealing-malware-campaign/)
- [CERN Windigo June 2019](https://security.web.cern.ch/advisories/windigo/windigo.shtml)
