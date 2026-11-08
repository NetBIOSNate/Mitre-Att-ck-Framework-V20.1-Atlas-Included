# G1021 - Cinnamon Tempest

[Enterprise](../../README.md) / [Groups](README.md)

[Cinnamon Tempest](https://attack.mitre.org/groups/G1021) is a China-based threat group that has been active since at least 2021 deploying multiple strains of ransomware based on the leaked [Babuk](https://attack.mitre.org/software/S0638) source code. [Cinnamon Tempest](https://attack.mitre.org/groups/G1021) does not operate their ransomware on an affiliate model or purchase access but appears to act independently in all stages of the attack lifecycle. Based on victimology, the short lifespan of each ransomware variant, and use of malware attributed to government-sponsored threat groups, [Cinnamon Tempest](https://attack.mitre.org/groups/G1021) may be motivated by intellectual property theft or cyberespionage rather than financial gain.(Citation: Microsoft Ransomware as a Service)(Citation: Microsoft Threat Actor Naming July 2023)(Citation: Trend Micro Cheerscrypt May 2022)(Citation: SecureWorks BRONZE STARLIGHT Ransomware Operations June 2022)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1021)

## Aliases

- DEV-0401
- Emperor Dragonfly
- BRONZE STARLIGHT

## Techniques used

- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1484.001 - Group Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.001%20-%20Group%20Policy%20Modification/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1080 - Taint Shared Content](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1080%20-%20Taint%20Shared%20Content/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Software used

- [S1096 - Cheerscrypt](../Software/Malware/S1096%20-%20Cheerscrypt.md)
- [S0154 - Cobalt Strike](../Software/Malware/S0154%20-%20Cobalt%20Strike.md)
- [S1097 - HUI Loader](../Software/Malware/S1097%20-%20HUI%20Loader.md)
- [S0357 - Impacket](../Software/Tools/S0357%20-%20Impacket.md)
- [S0664 - Pandora](../Software/Malware/S0664%20-%20Pandora.md)
- [S0013 - PlugX](../Software/Malware/S0013%20-%20PlugX.md)
- [S1040 - Rclone](../Software/Tools/S1040%20-%20Rclone.md)
- [S0633 - Sliver](../Software/Tools/S0633%20-%20Sliver.md)

## Sources

- [Sygnia Emperor Dragonfly October 2022](https://blog.sygnia.co/revealing-emperor-dragonfly-a-chinese-ransomware-group)
- [SecureWorks BRONZE STARLIGHT Ransomware Operations June 2022](https://www.secureworks.com/research/bronze-starlight-ransomware-operations-use-hui-loader)
- [Trend Micro Cheerscrypt May 2022](https://www.trendmicro.com/en_se/research/22/e/new-linux-based-ransomware-cheerscrypt-targets-exsi-devices.html)
- [Microsoft Threat Actor Naming July 2023](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide)
- [Microsoft Ransomware as a Service](https://www.microsoft.com/en-us/security/blog/2022/05/09/ransomware-as-a-service-understanding-the-cybercrime-gig-economy-and-how-to-protect-yourself/)
- [Dell SecureWorks BRONZE STARLIGHT Profile](https://www.secureworks.com/research/threat-profiles/bronze-starlight)
