# S0508 - ngrok

[Enterprise](../../../README.md) / [Tools](README.md)

[ngrok](https://attack.mitre.org/software/S0508) is a legitimate reverse proxy tool that can create a secure tunnel to servers located behind firewalls or on local machines that do not have a public IP. [ngrok](https://attack.mitre.org/software/S0508) has been leveraged by threat actors in several campaigns including use for lateral movement and data exfiltration.(Citation: Zdnet Ngrok September 2018)(Citation: FireEye Maze May 2020)(Citation: Cyware Ngrok May 2019)(Citation: MalwareBytes LazyScripter Feb 2021)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0508)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Used by

- [G1003 - Ember Bear](../../Groups/G1003%20-%20Ember%20Bear.md)
- [G0117 - Fox Kitten](../../Groups/G0117%20-%20Fox%20Kitten.md)
- [G0140 - LazyScripter](../../Groups/G0140%20-%20LazyScripter.md)
- [G0049 - OilRig](../../Groups/G0049%20-%20OilRig.md)
- [G1015 - Scattered Spider](../../Groups/G1015%20-%20Scattered%20Spider.md)
- [C0058 - SharePoint ToolShell Exploitation](../../Campaigns/C0058%20-%20SharePoint%20ToolShell%20Exploitation.md)

## Techniques used

- [T1568.002 - Domain Generation Algorithms](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/T1568.002%20-%20Domain%20Generation%20Algorithms/README.md)
- [T1567 - Exfiltration Over Web Service](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1572 - Protocol Tunneling](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1090 - Proxy](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1102 - Web Service](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/README.md)

## Sources

- [Zdnet Ngrok September 2018](https://www.zdnet.com/article/sly-malware-author-hides-cryptomining-botnet-behind-ever-shifting-proxy-service/)
- [Cyware Ngrok May 2019](https://cyware.com/news/cyber-attackers-leverage-tunneling-service-to-drop-lokibot-onto-victims-systems-6f610e44)
- [MalwareBytes LazyScripter Feb 2021](https://web.archive.org/web/20211003035156/https://www.malwarebytes.com/resources/files/2021/02/lazyscripter.pdf)
- [FireEye Maze May 2020](https://www.fireeye.com/blog/threat-research/2020/05/tactics-techniques-procedures-associated-with-maze-ransomware-incidents.html)
