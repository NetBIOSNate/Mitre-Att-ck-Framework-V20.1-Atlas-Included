# G0009 - Deep Panda

[Enterprise](../../README.md) / [Groups](README.md)

[Deep Panda](https://attack.mitre.org/groups/G0009) is a suspected Chinese threat group known to target many industries, including government, defense, financial, and telecommunications. (Citation: Alperovitch 2014) The intrusion into healthcare company Anthem has been attributed to [Deep Panda](https://attack.mitre.org/groups/G0009). (Citation: ThreatConnect Anthem) This group is also known as Shell Crew, WebMasters, KungFu Kittens, and PinkPanther. (Citation: RSA Shell Crew) [Deep Panda](https://attack.mitre.org/groups/G0009) also appears to be known as Black Vine based on the attribution of both group names to the Anthem intrusion. (Citation: Symantec Black Vine) Some analysts track [Deep Panda](https://attack.mitre.org/groups/G0009) and [APT19](https://attack.mitre.org/groups/G0073) as the same group, but it is unclear from open source information if the groups are the same. (Citation: ICIT China's Espionage Jul 2016)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0009)

## Aliases

- Shell Crew
- WebMasters
- KungFu Kittens
- PinkPanther
- Black Vine

## Techniques used

- [T1546.008 - Accessibility Features](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.008%20-%20Accessibility%20Features/README.md)
- [T1564.003 - Hidden Window](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.003%20-%20Hidden%20Window/README.md)
- [T1027.005 - Indicator Removal from Tools](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.005%20-%20Indicator%20Removal%20from%20Tools/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1218.010 - Regsvr32](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.010%20-%20Regsvr32/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S0021 - Derusbi](../Software/Malware/S0021%20-%20Derusbi.md)
- [S0080 - Mivast](../Software/Malware/S0080%20-%20Mivast.md)
- [S0039 - Net](../Software/Tools/S0039%20-%20Net.md)
- [S0097 - Ping](../Software/Tools/S0097%20-%20Ping.md)
- [S0074 - Sakula](../Software/Malware/S0074%20-%20Sakula.md)
- [S0142 - StreamEx](../Software/Malware/S0142%20-%20StreamEx.md)
- [S0057 - Tasklist](../Software/Tools/S0057%20-%20Tasklist.md)

## Sources

- [Alperovitch 2014](https://web.archive.org/web/20200424075623/https:/www.crowdstrike.com/blog/deep-thought-chinese-targeting-national-security-think-tanks/)
- [Symantec Black Vine](https://web.archive.org/web/20170823094836/http:/www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-black-vine-cyberespionage-group.pdf)
- [RSA Shell Crew](https://www.rsa.com/content/dam/en/white-paper/rsa-incident-response-emerging-threat-profile-shell-crew.pdf)
- [ICIT China's Espionage Jul 2016](https://web.archive.org/web/20171017072306/https://icitech.org/icit-brief-chinas-espionage-dynasty-economic-death-by-a-thousand-cuts/)
- [ThreatConnect Anthem](https://www.threatconnect.com/the-anthem-hack-all-roads-lead-to-china/)
