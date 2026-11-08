# T1016.002 - Wi-Fi Discovery

[Enterprise](../../../../README.md) / [Discovery](../../README.md) / [T1016 - System Network Configuration Discovery](../README.md)

Adversaries may search for information about Wi-Fi networks, such as network names and passwords, on compromised systems. Adversaries may use Wi-Fi information as part of [Account Discovery](https://attack.mitre.org/techniques/T1087), [Remote System Discovery](https://attack.mitre.org/techniques/T1018), and other discovery or [Credential Access](https://attack.mitre.org/tactics/TA0006) activity to support both ongoing and future campaigns.

Adversaries may collect various types of information about Wi-Fi networks from hosts. For example, on Windows names and passwords of all Wi-Fi networks a device has previously connected to may be available through `netsh wlan show profiles` to enumerate Wi-Fi names and then `netsh wlan show profile “Wi-Fi name” key=clear` to show a Wi-Fi network’s corresponding password.(Citation: BleepingComputer Agent Tesla steal wifi passwords)(Citation: Malware Bytes New AgentTesla variant steals WiFi credentials)(Citation: Check Point APT35 CharmPower January 2022) Additionally, names and other details of locally reachable Wi-Fi networks can be discovered using calls to `wlanAPI.dll` [Native API](https://attack.mitre.org/techniques/T1106) functions.(Citation: Binary Defense Emotes Wi-Fi Spreader)

On Linux, names and passwords of all Wi-Fi-networks a device has previously connected to may be available in files under ` /etc/NetworkManager/system-connections/`.(Citation: Wi-Fi Password of All Connected Networks in Windows/Linux) On macOS, the password of a known Wi-Fi may be identified with ` security find-generic-password -wa wifiname` (requires admin username/password).(Citation: Find Wi-Fi Password on Mac)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1016/002)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0331 - Agent Tesla](../../../../Threat%20Intelligence/Software/Malware/S0331%20-%20Agent%20Tesla.md) — [Agent Tesla](https://attack.mitre.org/software/S0331) can collect names and passwords of all Wi-Fi networks to which a device has previously connected.(Citation: Malwarebytes Agent Tesla April 2020) [Malwarebytes Agent Tesla April 2020](https://blog.malwarebytes.com/threat-analysis/2020/04/new-agenttesla-variant-steals-wifi-credentials/)
- [C0051 - APT28 Nearest Neighbor Campaign](../../../../Threat%20Intelligence/Campaigns/C0051%20-%20APT28%20Nearest%20Neighbor%20Campaign.md) — During [APT28 Nearest Neighbor Campaign](https://attack.mitre.org/campaigns/C0051), [APT28](https://attack.mitre.org/groups/G0007) collected information on wireless interfaces within range of a compromised system.(Citation: Nearest Neighbor Volexity) [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
- [S0674 - CharmPower](../../../../Threat%20Intelligence/Software/Malware/S0674%20-%20CharmPower.md) — [CharmPower](https://attack.mitre.org/software/S0674) can use `netsh wlan show profiles` to list specific Wi-Fi profile details.(Citation: Check Point APT35 CharmPower January 2022) [Check Point APT35 CharmPower January 2022](https://research.checkpoint.com/2022/apt35-exploits-log4j-vulnerability-to-distribute-new-modular-powershell-toolkit/)
- [S0367 - Emotet](../../../../Threat%20Intelligence/Software/Malware/S0367%20-%20Emotet.md) — [Emotet](https://attack.mitre.org/software/S0367) can extract names of all locally reachable Wi-Fi networks and then perform a brute-force attack to spread to new networks.(Citation: Binary Defense Emotes Wi-Fi Spreader) [Binary Defense Emotes Wi-Fi Spreader](https://www.binarydefense.com/resources/blog/emotet-evolves-with-new-wi-fi-spreader/)
- [S0409 - Machete](../../../../Threat%20Intelligence/Software/Malware/S0409%20-%20Machete.md) — [Machete](https://attack.mitre.org/software/S0409) uses the <code>netsh wlan show networks mode=bssid</code> and <code>netsh wlan show interfaces</code> commands to list all nearby WiFi networks and connected interfaces.(Citation: ESET Machete July 2019) [ESET Machete July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/08/ESET_Machete.pdf)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has collected names and passwords of all Wi-Fi networks to which a device has previously connected.(Citation: Check Point APT35 CharmPower January 2022) [Check Point APT35 CharmPower January 2022](https://research.checkpoint.com/2022/apt35-exploits-log4j-vulnerability-to-distribute-new-modular-powershell-toolkit/)
- [S1228 - PUBLOAD](../../../../Threat%20Intelligence/Software/Malware/S1228%20-%20PUBLOAD.md) — [PUBLOAD](https://attack.mitre.org/software/S1228) has collected information on Wi-Fi networks from victim hosts leveraging `netsh wlan show profiles`, `netsh wlan show interface`, and `netsh wlan show`. (Citation: Trend Micro MUSTANG PANDA PUBLOAD HIUPAN SEPTEMBER 2024) [Trend Micro MUSTANG PANDA PUBLOAD HIUPAN SEPTEMBER 2024](https://www.trendmicro.com/en_us/research/24/i/earth-preta-new-malware-and-strategies.html)

## Detection strategies

- [DET0464 - Behavioral Detection of Wi-Fi Discovery Activity](../../../../Defenses/Detection%20Strategies/DET0464%20-%20Behavioral%20Detection%20of%20Wi-Fi%20Discovery%20Activity.md)

## Sources

- [Binary Defense Emotes Wi-Fi Spreader](https://www.binarydefense.com/resources/blog/emotet-evolves-with-new-wi-fi-spreader/)
- [Check Point APT35 CharmPower January 2022](https://research.checkpoint.com/2022/apt35-exploits-log4j-vulnerability-to-distribute-new-modular-powershell-toolkit/)
- [Wi-Fi Password of All Connected Networks in Windows/Linux](https://www.geeksforgeeks.org/wi-fi-password-connected-networks-windowslinux/)
- [Malware Bytes New AgentTesla variant steals WiFi credentials](https://www.malwarebytes.com/blog/news/2020/04/new-agenttesla-variant-steals-wifi-credentials)
- [Find Wi-Fi Password on Mac](https://mackeeper.com/blog/find-wi-fi-password-on-mac/)
- [BleepingComputer Agent Tesla steal wifi passwords](https://www.bleepingcomputer.com/news/security/hackers-steal-wifi-passwords-using-upgraded-agent-tesla-malware/)
