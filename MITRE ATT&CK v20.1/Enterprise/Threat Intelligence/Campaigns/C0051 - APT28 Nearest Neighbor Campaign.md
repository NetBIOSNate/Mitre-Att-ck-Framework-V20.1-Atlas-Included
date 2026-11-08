# C0051 - APT28 Nearest Neighbor Campaign

[Enterprise](../../README.md) / [Campaigns](README.md)

[APT28 Nearest Neighbor Campaign](https://attack.mitre.org/campaigns/C0051) was conducted by [APT28](https://attack.mitre.org/groups/G0007) from early February 2022 to November 2024 against organizations and individuals with expertise on Ukraine. APT28 primarily leveraged living-off-the-land techniques, while leveraging the zero-day exploitation of CVE-2022-38028. Notably, APT28 leveraged Wi-Fi networks in close proximity to the intended target to gain initial access to the victim environment. By daisy-chaining multiple compromised organizations nearby the intended target, APT28 discovered dual-homed systems (with both a wired and wireless network connection) to enable Wi-Fi and use compromised credentials to connect to the victim network.(Citation: Nearest Neighbor Volexity)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0051)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1584 - Compromise Infrastructure](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1006 - Direct Volume Access](../../Tactics/07%20TA0005%20-%20Stealth/T1006%20-%20Direct%20Volume%20Access/README.md)
- [T1561.001 - Disk Content Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.001%20-%20Disk%20Content%20Wipe/README.md)
- [T1567 - Exfiltration Over Web Service](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1090.001 - Internal Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.001%20-%20Internal%20Proxy/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1110.003 - Password Spraying](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1016.002 - Wi-Fi Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/T1016.002%20-%20Wi-Fi%20Discovery/README.md)
- [T1669 - Wi-Fi Networks](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1669%20-%20Wi-Fi%20Networks/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1686.003 - Windows Host Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.003%20-%20Windows%20Host%20Firewall/README.md)

## Software used

- [S1205 - cipher.exe](../Software/Tools/S1205%20-%20cipher.exe.md)
- [S0108 - netsh](../Software/Tools/S0108%20-%20netsh.md)

## Attributed groups

- [G0007 - APT28](../Groups/G0007%20-%20APT28.md)

## Sources

- [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
