# S1063 - Brute Ratel C4

[Enterprise](../../../README.md) / [Tools](README.md)

[Brute Ratel C4](https://attack.mitre.org/software/S1063) is a commercial red-teaming and adversarial attack simulation tool that first appeared in December 2020. [Brute Ratel C4](https://attack.mitre.org/software/S1063) was specifically designed to avoid detection by endpoint detection and response (EDR) and antivirus (AV) capabilities, and deploys agents called badgers to enable arbitrary command execution for lateral movement, privilege escalation, and persistence. In September 2022, a cracked version of [Brute Ratel C4](https://attack.mitre.org/software/S1063) was leaked in the cybercriminal underground, leading to its use by threat actors.(Citation: Dark Vortex Brute Ratel C4)(Citation: Palo Alto Brute Ratel July 2022)(Citation: MDSec Brute Ratel August 2022)(Citation: SANS Brute Ratel October 2022)(Citation: Trend Micro Black Basta October 2022)

[MITRE ATT&CK record](https://attack.mitre.org/software/S1063)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Aliases

- BRc4

## Techniques used

- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1685 - Disable or Modify Tools](../../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1574.001 - DLL](../../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1071.004 - DNS](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.004%20-%20DNS/README.md)
- [T1087.002 - Domain Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1069.002 - Domain Groups](../../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.002%20-%20Domain%20Groups/README.md)
- [T1482 - Domain Trust Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1027.007 - Dynamic API Resolution](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.007%20-%20Dynamic%20API%20Resolution/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1558.003 - Kerberoasting](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1204.002 - Malicious File](../../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1036.008 - Masquerade File Type](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1106 - Native API](../../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1046 - Network Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1095 - Non-Application Layer Protocol](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1027 - Obfuscated Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1055.002 - Portable Executable Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.002%20-%20Portable%20Executable%20Injection/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1572 - Protocol Tunneling](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1620 - Reflective Code Loading](../../../Tactics/07%20TA0005%20-%20Stealth/T1620%20-%20Reflective%20Code%20Loading/README.md)
- [T1021 - Remote Services](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1113 - Screen Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1518.001 - Security Software Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/T1518.001%20-%20Security%20Software%20Discovery/README.md)
- [T1569.002 - Service Execution](../../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1497.003 - Time Based Checks](../../../Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/T1497.003%20-%20Time%20Based%20Checks/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1102 - Web Service](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/README.md)
- [T1059.003 - Windows Command Shell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1021.006 - Windows Remote Management](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.006%20-%20Windows%20Remote%20Management/README.md)

## Sources

- [MDSec Brute Ratel August 2022](https://www.mdsec.co.uk/2022/08/part-3-how-i-met-your-beacon-brute-ratel/)
- [Dark Vortex Brute Ratel C4](https://bruteratel.com/)
- [Palo Alto Brute Ratel July 2022](https://unit42.paloaltonetworks.com/brute-ratel-c4-tool/)
- [Trend Micro Black Basta October 2022](https://www.trendmicro.com/en_us/research/22/j/black-basta-infiltrates-networks-via-qakbot-brute-ratel-and-coba.html)
- [SANS Brute Ratel October 2022](https://www.sans.org/blog/cracked-brute-ratel-c4-framework-proliferates-across-the-cybercriminal-underground/)
