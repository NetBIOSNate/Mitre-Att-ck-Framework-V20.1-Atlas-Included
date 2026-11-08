# S0695 - Donut

[Enterprise](../../../README.md) / [Tools](README.md)

[Donut](https://attack.mitre.org/software/S0695) is an open source framework used to generate position-independent shellcode.(Citation: Donut Github)(Citation: Introducing Donut) [Donut](https://attack.mitre.org/software/S0695) generated code has been used by multiple threat actors to inject and load malicious payloads into memory.(Citation: NCC Group WastedLocker June 2020)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0695)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1059 - Command and Scripting Interpreter](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1027.015 - Compression](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.015%20-%20Compression/README.md)
- [T1685 - Disable or Modify Tools](../../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1027.013 - Encrypted/Encoded File](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1070 - Indicator Removal](../../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.007 - JavaScript](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1106 - Native API](../../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1055 - Process Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1059.006 - Python](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1620 - Reflective Code Loading](../../../Tactics/07%20TA0005%20-%20Stealth/T1620%20-%20Reflective%20Code%20Loading/README.md)
- [T1027.002 - Software Packing](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1059.005 - Visual Basic](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Used by

- [G0119 - Indrik Spider](../../Groups/G0119%20-%20Indrik%20Spider.md)

## Sources

- [NCC Group WastedLocker June 2020](https://research.nccgroup.com/2020/06/23/wastedlocker-a-new-ransomware-variant-developed-by-the-evil-corp-group/)
- [Introducing Donut](https://thewover.github.io/Introducing-Donut/)
- [Donut Github](https://github.com/TheWover/donut)
