# S0193 - Forfiles

[Enterprise](../../../README.md) / [Tools](README.md)

[Forfiles](https://attack.mitre.org/software/S0193) is a Windows utility commonly used in batch jobs to execute commands on one or more selected files or directories (ex: list all directories in a drive, read the first line of all files created yesterday, etc.). Forfiles can be executed from either the command line, Run window, or batch files/scripts. (Citation: Microsoft Forfiles Aug 2016)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0193)

## Used by

- [G0007 - APT28](../../Groups/G0007%20-%20APT28.md)

## Techniques used

- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1202 - Indirect Command Execution](../../../Tactics/07%20TA0005%20-%20Stealth/T1202%20-%20Indirect%20Command%20Execution/README.md)

## Sources

- [Microsoft Forfiles Aug 2016](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc753551%28v=ws.11%29)
