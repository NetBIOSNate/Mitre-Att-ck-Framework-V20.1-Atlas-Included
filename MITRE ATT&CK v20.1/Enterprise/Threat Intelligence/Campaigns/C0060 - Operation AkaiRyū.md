# C0060 - Operation AkaiRyū

[Enterprise](../../README.md) / [Campaigns](README.md)

[Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060) (Japanese for RedDragon) was a cyberespionage spearphishing campaign conducted by [MirrorFace](https://attack.mitre.org/groups/G1054) between June and September 2024 against entities in Japan and Central Europe. [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060) notably included the first reported targeting of a European entity by [MirrorFace](https://attack.mitre.org/groups/G1054), as well as their use of [UPPERCUT](https://attack.mitre.org/software/S0275), which was thought to be exclusive to [menuPass](https://attack.mitre.org/groups/G0045).(Citation: ESET MirrorFace 2025)(Citation: Trend Micro Earth Kasha Anel NOV 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0060)

## Aliases

- AkaiRyū

## Techniques used

- [T1217 - Browser Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1217%20-%20Browser%20Information%20Discovery/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1585.003 - Cloud Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.003%20-%20Cloud%20Accounts/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1585.002 - Email Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.002%20-%20Email%20Accounts/README.md)
- [T1586.002 - Email Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1586%20-%20Compromise%20Accounts/T1586.002%20-%20Email%20Accounts/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1219.001 - IDE Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.001%20-%20IDE%20Tunneling/README.md)
- [T1608.005 - Link Target](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.005%20-%20Link%20Target/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036.008 - Masquerade File Type](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1127.001 - MSBuild](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.001%20-%20MSBuild/README.md)
- [T1137.001 - Office Template Macros](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.001%20-%20Office%20Template%20Macros/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S9027 - ANELLDR](../Software/Malware/S9027%20-%20ANELLDR.md)
- [S0099 - Arp](../Software/Tools/S0099%20-%20Arp.md)
- [S1087 - AsyncRAT](../Software/Tools/S1087%20-%20AsyncRAT.md)
- [S1144 - FRP](../Software/Tools/S1144%20-%20FRP.md)
- [S9023 - HiddenFace](../Software/Malware/S9023%20-%20HiddenFace.md)
- [S9026 - ROAMINGHOUSE](../Software/Malware/S9026%20-%20ROAMINGHOUSE.md)
- [S1071 - Rubeus](../Software/Tools/S1071%20-%20Rubeus.md)
- [S0275 - UPPERCUT](../Software/Malware/S0275%20-%20UPPERCUT.md)

## Attributed groups

- [G1054 - MirrorFace](../Groups/G1054%20-%20MirrorFace.md)

## Sources

- [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/)
- [Trend Micro Earth Kasha Anel NOV 2024](https://www.trendmicro.com/en_us/research/24/k/return-of-anel-in-the-recent-earth-kasha-spearphishing-campaign.html)
