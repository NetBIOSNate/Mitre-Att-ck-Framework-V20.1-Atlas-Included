# C0055 - Quad7 Activity

[Enterprise](../../README.md) / [Campaigns](README.md)

Quad7 Activity, also known as CovertNetwork-1658 or the 7777 Botnet, is a network of compromised small office/home office (SOHO) routers. (Citation: Bitsight 7777 Botnet) (Citation: Microsoft Storm-0940) The botnet was initially composed primarily of TP-Link routers and was named Quad7 due to compromised devices exposing TCP port 7777 with the distinctive banner <code>xlogin</code>. Later activity showed a significant increase in compromised Asus routers and the addition of new ports and banners, including TCP port 63256 displaying <code>alogin</code>. Quad7 infrastructure functions as a collection of egress IPs that various China-affiliated threat actors have used to conduct password-spraying and brute-force operations. (Citation: Bitsight 7777 Botnet)(Citation: Medium 777-Botnet) Microsoft has reported that Storm-0940 leveraged credentials obtained through Quad7 Activity to target organizations in North America and Europe, including government agencies, non-governmental organizations, think tanks, law firms, energy firms, IT providers, and defense industrial base entities. (Citation: Microsoft Storm-0940)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0055)

## Techniques used

- [T1584.005 - Botnet](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.005%20-%20Botnet/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1589.002 - Email Addresses](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1589%20-%20Gather%20Victim%20Identity%20Information/T1589.002%20-%20Email%20Addresses/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1090.002 - External Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.002%20-%20External%20Proxy/README.md)
- [T1071.002 - File Transfer Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.002%20-%20File%20Transfer%20Protocols/README.md)
- [T1027.011 - Fileless Storage](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.011%20-%20Fileless%20Storage/README.md)
- [T1665 - Hide Infrastructure](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1665%20-%20Hide%20Infrastructure/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1584.008 - Network Devices](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.008%20-%20Network%20Devices/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1110.003 - Password Spraying](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Software used

- [S0095 - ftp](../Software/Tools/S0095%20-%20ftp.md)

## Sources

- [Bitsight 7777 Botnet](https://www.bitsight.com/blog/7777-botnet-insights-multi-target-botnet)
- [Medium 777-Botnet](https://gi7w0rm.medium.com/the-curious-case-of-the-7777-botnet-86e3464c3ffd)
- [Microsoft Storm-0940](https://www.microsoft.com/en-us/security/blog/2024/10/31/chinese-threat-actor-storm-0940-uses-credentials-from-password-spray-attacks-from-a-covert-network/)
- [TP-Link Quad 7 AUG 2025](https://www.tp-link.com/us/support/faq/4365/)
