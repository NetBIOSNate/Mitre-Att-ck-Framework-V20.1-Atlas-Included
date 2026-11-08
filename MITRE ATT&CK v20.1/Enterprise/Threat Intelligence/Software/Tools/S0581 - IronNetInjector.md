# S0581 - IronNetInjector

[Enterprise](../../../README.md) / [Tools](README.md)

[IronNetInjector](https://attack.mitre.org/software/S0581) is a [Turla](https://attack.mitre.org/groups/G0010) toolchain that utilizes scripts from the open-source IronPython implementation of Python with a .NET injector to drop one or more payloads including [ComRAT](https://attack.mitre.org/software/S0126).(Citation: Unit 42 IronNetInjector February 2021 )

[MITRE ATT&CK record](https://attack.mitre.org/software/S0581)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1140 - Deobfuscate/Decode Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1055.001 - Dynamic-link Library Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.001%20-%20Dynamic-link%20Library%20Injection/README.md)
- [T1027.013 - Encrypted/Encoded File](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1036.004 - Masquerade Task or Service](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1055 - Process Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1059.006 - Python](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1053.005 - Scheduled Task](../../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)

## Used by

- [G0010 - Turla](../../Groups/G0010%20-%20Turla.md)

## Sources

- [Unit 42 IronNetInjector February 2021 ](https://unit42.paloaltonetworks.com/ironnetinjector/)
