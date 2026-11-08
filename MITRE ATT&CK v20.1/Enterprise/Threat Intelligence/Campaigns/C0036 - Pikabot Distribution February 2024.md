# C0036 - Pikabot Distribution February 2024

[Enterprise](../../README.md) / [Campaigns](README.md)

[Pikabot](https://attack.mitre.org/software/S1145) was distributed in [Pikabot Distribution February 2024](https://attack.mitre.org/campaigns/C0036) using malicious emails with embedded links leading to malicious ZIP archives requiring user interaction for follow-on infection. The version of [Pikabot](https://attack.mitre.org/software/S1145) distributed featured significant changes over the 2023 variant, including reduced code complexity and simplified obfuscation mechanisms.(Citation: Elastic Pikabot 2024)(Citation: Zscaler Pikabot 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0036)

## Techniques used

- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)

## Software used

- [S1145 - Pikabot](../Software/Malware/S1145%20-%20Pikabot.md)

## Sources

- [Elastic Pikabot 2024](https://www.elastic.co/security-labs/pikabot-i-choose-you)
- [Zscaler Pikabot 2024](https://www.zscaler.com/blogs/security-research/d-evolution-pikabot)
