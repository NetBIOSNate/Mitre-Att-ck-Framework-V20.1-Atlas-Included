# S0105 - dsquery

[Enterprise](../../../README.md) / [Tools](README.md)

[dsquery](https://attack.mitre.org/software/S0105) is a command-line utility that can be used to query Active Directory for information from a system within a domain. (Citation: TechNet Dsquery) It is typically installed only on Windows Server versions but can be installed on non-server variants through the Microsoft-provided Remote Server Administration Tools bundle.

[MITRE ATT&CK record](https://attack.mitre.org/software/S0105)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Aliases

- dsquery.exe

## Used by

- [G0096 - APT41](../../Groups/G0096%20-%20APT41.md)
- [C0017 - C0017](../../Campaigns/C0017%20-%20C0017.md)
- [G0061 - FIN8](../../Groups/G0061%20-%20FIN8.md)
- [C0012 - Operation CuckooBees](../../Campaigns/C0012%20-%20Operation%20CuckooBees.md)
- [C0014 - Operation Wocao](../../Campaigns/C0014%20-%20Operation%20Wocao.md)

## Techniques used

- [T1087.002 - Domain Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1069.002 - Domain Groups](../../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.002%20-%20Domain%20Groups/README.md)
- [T1482 - Domain Trust Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)

## Sources

- [TechNet Dsquery](https://technet.microsoft.com/en-us/library/cc732952.aspx)
