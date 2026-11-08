# C0030 - Triton Safety Instrumented System Attack

[Enterprise](../../README.md) / [Campaigns](README.md)

[Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030) was a campaign employed by [TEMP.Veles](https://attack.mitre.org/groups/G0088) which leveraged the [Triton](https://attack.mitre.org/software/S1009) malware framework against a petrochemical organization.(Citation: Triton-EENews-2017) The malware and techniques used within this campaign targeted specific Triconex [Safety Controller](https://attack.mitre.org/assets/A0010)s within the environment.(Citation: FireEye TRITON 2018) The incident was eventually discovered due to a safety trip that occurred as a result of an issue in the malware.(Citation: FireEye TRITON 2017)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0030)

## Techniques used

- [T1595 - Active Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/README.md)
- [T1573 - Encrypted Channel](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/README.md)
- [T1027.005 - Indicator Removal from Tools](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.005%20-%20Indicator%20Removal%20from%20Tools/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1056.003 - Web Portal Capture](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.003%20-%20Web%20Portal%20Capture/README.md)

## Attributed groups

- [G0088 - TEMP.Veles](../Groups/G0088%20-%20TEMP.Veles.md)

## Software used

- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)

## Sources

- [Triton-EENews-2017](https://www.eenews.net/articles/the-inside-story-of-the-worlds-most-dangerous-malware/)
- [FireEye TRITON 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)
- [FireEye TRITON 2018](https://web.archive.org/web/20200618231942/https://www.fireeye.com/blog/threat-research/2018/06/totally-tubular-treatise-on-triton-and-tristation.html)
