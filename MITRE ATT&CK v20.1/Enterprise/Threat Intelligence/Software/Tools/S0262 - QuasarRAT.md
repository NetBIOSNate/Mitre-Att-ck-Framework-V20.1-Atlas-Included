# S0262 - QuasarRAT

[Enterprise](../../../README.md) / [Tools](README.md)

[QuasarRAT](https://attack.mitre.org/software/S0262) is an open-source, remote access tool that has been publicly available on GitHub since at least 2014. [QuasarRAT](https://attack.mitre.org/software/S0262) is developed in the C# language.(Citation: GitHub QuasarRAT)(Citation: Volexity Patchwork June 2018)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0262)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Aliases

- xRAT

## Techniques used

- [T1010 - Application Window Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1010%20-%20Application%20Window%20Discovery/README.md)
- [T1548.002 - Bypass User Account Control](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1553.002 - Code Signing](../../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1555 - Credentials from Password Stores](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1555.003 - Credentials from Web Browsers](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1552.001 - Credentials In Files](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1564.001 - Hidden Files and Directories](../../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.001%20-%20Hidden%20Files%20and%20Directories/README.md)
- [T1564.003 - Hidden Window](../../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.003%20-%20Hidden%20Window/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1056.001 - Keylogging](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1112 - Modify Registry](../../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1095 - Non-Application Layer Protocol](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1571 - Non-Standard Port](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1090 - Proxy](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1021.001 - Remote Desktop Protocol](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1053.005 - Scheduled Task](../../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1573.001 - Symmetric Cryptography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1614 - System Location Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1614%20-%20System%20Location%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1125 - Video Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1125%20-%20Video%20Capture/README.md)
- [T1059.003 - Windows Command Shell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Used by

- [G0099 - APT-C-36](../../Groups/G0099%20-%20APT-C-36.md)
- [G0135 - BackdoorDiplomacy](../../Groups/G0135%20-%20BackdoorDiplomacy.md)
- [G0078 - Gorgon Group](../../Groups/G0078%20-%20Gorgon%20Group.md)
- [G0094 - Kimsuky](../../Groups/G0094%20-%20Kimsuky.md)
- [G0140 - LazyScripter](../../Groups/G0140%20-%20LazyScripter.md)
- [G0045 - menuPass](../../Groups/G0045%20-%20menuPass.md)
- [G0040 - Patchwork](../../Groups/G0040%20-%20Patchwork.md)

## Sources

- [Securelist APT10 March 2021](https://securelist.com/apt10-sophisticated-multi-layered-loader-ecipekac-discovered-in-a41apt-campaign/101519/)
- [TrendMicro Patchwork Dec 2017](https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf)
- [GitHub QuasarRAT](https://github.com/quasar/QuasarRAT)
- [Volexity Patchwork June 2018](https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/)
