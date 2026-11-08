# C0037 - Water Curupira Pikabot Distribution

[Enterprise](../../README.md) / [Campaigns](README.md)

[Pikabot](https://attack.mitre.org/software/S1145) was distributed in [Water Curupira Pikabot Distribution](https://attack.mitre.org/campaigns/C0037) throughout 2023 by an entity linked to BlackBasta ransomware deployment via email attachments. This activity followed the take-down of [QakBot](https://attack.mitre.org/software/S0650), with several technical overlaps and similarities with [QakBot](https://attack.mitre.org/software/S0650), indicating a possible connection. The identified activity led to the deployment of tools such as [Cobalt Strike](https://attack.mitre.org/software/S0154), while coinciding with campaigns delivering [DarkGate](https://attack.mitre.org/software/S1111) and [IcedID](https://attack.mitre.org/software/S0483) en route to ransomware deployment.(Citation: TrendMicro Pikabot 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0037)

## Techniques used

- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1589.002 - Email Addresses](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1589%20-%20Gather%20Victim%20Identity%20Information/T1589.002%20-%20Email%20Addresses/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1218.011 - Rundll32](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.011%20-%20Rundll32/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Software used

- [S1111 - DarkGate](../Software/Malware/S1111%20-%20DarkGate.md)
- [S0483 - IcedID](../Software/Malware/S0483%20-%20IcedID.md)
- [S1145 - Pikabot](../Software/Malware/S1145%20-%20Pikabot.md)

## Sources

- [TrendMicro Pikabot 2024](https://www.trendmicro.com/en_us/research/24/a/a-look-into-pikabot-spam-wave-campaign.html)
