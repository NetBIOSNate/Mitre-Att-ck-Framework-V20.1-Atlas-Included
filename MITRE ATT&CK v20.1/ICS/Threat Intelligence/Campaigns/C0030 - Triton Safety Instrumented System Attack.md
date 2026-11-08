# C0030 - Triton Safety Instrumented System Attack

[ICS](../../README.md) / [Campaigns](README.md)

[Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030) was a campaign employed by [TEMP.Veles](https://attack.mitre.org/groups/G0088) which leveraged the [Triton](https://attack.mitre.org/software/S1009) malware framework against a petrochemical organization.(Citation: Triton-EENews-2017) The malware and techniques used within this campaign targeted specific Triconex [Safety Controller](https://attack.mitre.org/assets/A0010)s within the environment.(Citation: FireEye TRITON 2018) The incident was eventually discovered due to a safety trip that occurred as a result of an issue in the malware.(Citation: FireEye TRITON 2017)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0030)

## Techniques used

- [T0830 - Adversary-in-the-Middle](../../Tactics/08%20TA0100%20-%20Collection/T0830%20-%20Adversary-in-the-Middle/README.md)
- [T1701 - Command and Scripting Interpreter](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1692.001 - Command Message](../../Tactics/05%20TA0103%20-%20Evasion/T1692%20-%20Unauthorized%20Message/T1692.001%20-%20Command%20Message/README.md)
- [T0872 - Indicator Removal on Host](../../Tactics/05%20TA0103%20-%20Evasion/T0872%20-%20Indicator%20Removal%20on%20Host/README.md)
- [T0867 - Lateral Tool Transfer](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0867%20-%20Lateral%20Tool%20Transfer/README.md)
- [T0828 - Loss of Productivity and Revenue](../../Tactics/12%20TA0105%20-%20Impact/T0828%20-%20Loss%20of%20Productivity%20and%20Revenue/README.md)
- [T1701.001 - PowerShell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.001%20-%20PowerShell/README.md)
- [T0843.003 - Program Append](../../Tactics/07%20TA0109%20-%20Lateral%20Movement/T0843%20-%20Program%20Download/T0843.003%20-%20Program%20Append/README.md)
- [T0886 - Remote Services](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0886%20-%20Remote%20Services/README.md)
- [T0859 - Valid Accounts](../../Tactics/03%20TA0110%20-%20Persistence/T0859%20-%20Valid%20Accounts/README.md)

## Software used

- [S1009 - Triton](../Software/Malware/S1009%20-%20Triton.md)

## Attributed groups

- [G0088 - TEMP.Veles](../Groups/G0088%20-%20TEMP.Veles.md)

## Sources

- [Triton-EENews-2017](https://www.eenews.net/articles/the-inside-story-of-the-worlds-most-dangerous-malware/)
- [FireEye TRITON 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)
- [FireEye TRITON 2018](https://web.archive.org/web/20200618231942/https://www.fireeye.com/blog/threat-research/2018/06/totally-tubular-treatise-on-triton-and-tristation.html)
