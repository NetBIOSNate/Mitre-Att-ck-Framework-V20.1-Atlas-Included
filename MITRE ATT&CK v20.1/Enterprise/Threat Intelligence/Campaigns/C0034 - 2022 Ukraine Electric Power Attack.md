# C0034 - 2022 Ukraine Electric Power Attack

[Enterprise](../../README.md) / [Campaigns](README.md)

The [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034) was a [Sandworm Team](https://attack.mitre.org/groups/G0034) campaign that used a combination of GOGETTER, Neo-REGEORG, [CaddyWiper](https://attack.mitre.org/software/S0693), and living of the land (LotL) techniques to gain access to a Ukrainian electric utility to send unauthorized commands from their SCADA system.(Citation: Mandiant-Sandworm-Ukraine-2022)(Citation: Dragos-Sandworm-Ukraine-2022)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0034)

## Techniques used

- [T1485 - Data Destruction](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1484.001 - Group Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.001%20-%20Group%20Policy%20Modification/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1036.004 - Masquerade Task or Service](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)

## Attributed groups

- [G0034 - Sandworm Team](../Groups/G0034%20-%20Sandworm%20Team.md)

## Software used

- [S0693 - CaddyWiper](../Software/Malware/S0693%20-%20CaddyWiper.md)

## Sources

- [Dragos-Sandworm-Ukraine-2022](https://www.dragos.com/blog/new-details-electrum-ukraine-electric-sector-compromise-2022/)
- [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)
