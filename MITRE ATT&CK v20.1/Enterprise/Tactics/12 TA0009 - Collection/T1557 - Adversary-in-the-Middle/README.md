# T1557 - Adversary-in-the-Middle

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may attempt to position themselves between two or more networked devices using an adversary-in-the-middle (AiTM) technique to support follow-on behaviors such as [Network Sniffing](https://attack.mitre.org/techniques/T1040), [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002), or replay attacks ([Exploitation for Credential Access](https://attack.mitre.org/techniques/T1212)). By abusing features of common networking protocols that can determine the flow of network traffic (e.g. ARP, DNS, LLMNR, etc.), adversaries may force a device to communicate through an adversary controlled system so they can collect information or perform additional actions.(Citation: Rapid7 MiTM Basics)

For example, adversaries may manipulate victim DNS settings to enable other malicious activities such as preventing/redirecting users from accessing legitimate sites and/or pushing additional malware.(Citation: ttint_rat)(Citation: dns_changer_trojans)(Citation: ad_blocker_with_miner) Adversaries may also manipulate DNS and leverage their position in order to intercept user credentials, including access tokens ([Steal Application Access Token](https://attack.mitre.org/techniques/T1528)) and session cookies ([Steal Web Session Cookie](https://attack.mitre.org/techniques/T1539)).(Citation: volexity_0day_sophos_FW)(Citation: Token tactics) [Downgrade Attack](https://attack.mitre.org/techniques/T1689)s can also be used to establish an AiTM position, such as by negotiating a less secure, deprecated, or weaker version of communication protocol (SSL/TLS) or encryption algorithm.(Citation: mitm_tls_downgrade_att)(Citation: taxonomy_downgrade_att_tls)(Citation: tlseminar_downgrade_att)

Adversaries may also leverage the AiTM position to attempt to monitor and/or modify traffic, such as in [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002). Adversaries can set up a position similar to AiTM to prevent traffic from flowing to the appropriate destination, potentially to impair defenses and/or in support of a [Network Denial of Service](https://attack.mitre.org/techniques/T1498).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1557)

**Tactics**  [Credential Access](../../09%20TA0006%20-%20Credential%20Access/README.md), [Collection](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1557.002 - ARP Cache Poisoning](T1557.002%20-%20ARP%20Cache%20Poisoning/README.md)
- [T1557.003 - DHCP Spoofing](T1557.003%20-%20DHCP%20Spoofing/README.md)
- [T1557.004 - Evil Twin](T1557.004%20-%20Evil%20Twin/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable legacy network protocols that may be used to intercept network traffic if applicable, especially those that are not needed within an environment.
- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Ensure that all wired and/or wireless traffic is encrypted appropriately. Use best practices for authentication protocols, such as Kerberos, and ensure web traffic that may contain credentials is protected by SSL/TLS.
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Use network appliances and host-based security software to block network traffic that is not necessary within the environment, such as legacy protocols that may be leveraged for AiTM conditions.
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit access to network infrastructure and resources that can be used to reshape traffic or otherwise produce AiTM conditions.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that can identify traffic patterns indicative of AiTM activity can be used to mitigate activity at the network level.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Network segmentation can be used to isolate infrastructure components that do not require broad network access. This may mitigate, or at least alleviate, the scope of AiTM activity.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to be suspicious about certificate errors. Adversaries may use their own certificates in an attempt to intercept HTTPS traffic. Certificate errors may arise when the application’s certificate does not match the one expected by the host.

## Procedure examples

- [C0046 - ArcaneDoor](../../../Threat%20Intelligence/Campaigns/C0046%20-%20ArcaneDoor.md) — [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) included interception of HTTP traffic to victim devices to identify and parse command and control information sent to the device.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [S0281 - Dok](../../../Threat%20Intelligence/Software/Malware/S0281%20-%20Dok.md) — [Dok](https://attack.mitre.org/software/S0281) proxies web traffic to potentially monitor and alter victim HTTP(S) traffic.(Citation: objsee mac malware 2017)(Citation: CheckPoint Dok) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html) · [CheckPoint Dok](https://blog.checkpoint.com/2017/04/27/osx-malware-catching-wants-read-https-traffic/)
- [S9003 - evilginx2](../../../Threat%20Intelligence/Software/Tools/S9003%20-%20evilginx2.md) — [evilginx2](https://attack.mitre.org/software/S9003) has the ability to act as an adversary-in-the-middle (AiTM) relay between a legitimate website and a phished user to capture all transmitted data including usernames, passwords, authentication tokens, and session cookies and tokens.(Citation: Evilginx 2 July 2018)(Citation: Breakdev Evilginx 3.0 May 2023)(Citation: Breakdev Evilginx 3.2 AUG 2023)(Citation: Sophos Evilginx MAR 2025) [Sophos Evilginx MAR 2025](https://www.sophos.com/en-us/blog/stealing-user-credentials-with-evilginx) · [Breakdev Evilginx 3.2 AUG 2023](https://breakdev.org/evilginx-3-2/) · [Breakdev Evilginx 3.0 May 2023](https://breakdev.org/evilginx-3-0-evilginx-mastery/) · [Evilginx 2 July 2018](https://breakdev.org/evilginx-2-next-generation-of-phishing-2fa-tokens/)
- [S9044 - Kali365](../../../Threat%20Intelligence/Software/Malware/S9044%20-%20Kali365.md) — [Kali365](https://attack.mitre.org/software/S9044) has created obfuscated phishing landing pages that act as an adversary in the middle infrastructure that intercepts communications between the victim host and legitimate services to steal credentials and user sessions.(Citation: Artic Wolf Labs Kali365 Device Code April 2026)(Citation: Artic Wolf Kali365 Device Code OAuth June 2026)(Citation: SpyCloud Kali365 June 2026) [Artic Wolf Labs Kali365 Device Code April 2026](https://arcticwolf.com/resources/blog/token-bingo-dont-let-your-code-be-the-winner/) · [Artic Wolf Kali365 Device Code OAuth June 2026](https://arcticwolf.com/resources/blog/kali365-expands-into-aws-microsoft-okta-xerox-max-messenger/) · [SpyCloud Kali365 June 2026](https://spycloud.com/blog/kali365-anatomy-of-a-microsoft365-phishing-as-a-service-kit/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used modified versions of PHProxy to examine web traffic between the victim and the accessed website.(Citation: CISA AA20-301A Kimsuky) [CISA AA20-301A Kimsuky](https://us-cert.cisa.gov/ncas/alerts/aa20-301a)
- [S1188 - Line Runner](../../../Threat%20Intelligence/Software/Malware/S1188%20-%20Line%20Runner.md) — [Line Runner](https://attack.mitre.org/software/S1188) intercepts HTTP requests to the victim Cisco ASA, looking for a request with a 32-character, victim dependent parameter. If that parameter matches a value in the malware, a contained payload is then written to a Lua script and executed.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [G0129 - Mustang Panda](../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) leveraged a captive portal hijack that redirected the victim to a webpage that prompted the victim to download a malicious payload.(Citation: Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025) [Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats)
- [S1131 - NPPSPY](../../../Threat%20Intelligence/Software/Tools/S1131%20-%20NPPSPY.md) — [NPPSPY](https://attack.mitre.org/software/S1131) opens a new network listener for the <code>mpnotify.exe</code> process that is typically contacted by the Winlogon process in Windows. A new, alternative RPC channel is set up with a malicious DLL recording plaintext credentials entered into Winlogon, effectively intercepting and redirecting the logon information.(Citation: Huntress NPPSPY 2022) [Huntress NPPSPY 2022](https://www.huntress.com/blog/cleartext-shenanigans-gifting-user-passwords-to-adversaries-with-nppspy)
- [G1041 - Sea Turtle](../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) modified DNS records at service providers to redirect traffic from legitimate resources to [Sea Turtle](https://attack.mitre.org/groups/G1041)-controlled servers to enable adversary-in-the-middle attacks for credential capture.(Citation: Talos Sea Turtle 2019)(Citation: Talos Sea Turtle 2019_2) [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/) · [Talos Sea Turtle 2019_2](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)

## Detection strategies

- [DET0296 - Detect Adversary-in-the-Middle via Network and Configuration Anomalies](../../../Defenses/Detection%20Strategies/DET0296%20-%20Detect%20Adversary-in-the-Middle%20via%20Network%20and%20Configuration%20Anomalies.md)

## Sources

- [dns_changer_trojans](https://www.trendmicro.com/vinfo/us/threat-encyclopedia/web-attack/125/how-dns-changer-trojans-direct-users-to-threats)
- [volexity_0day_sophos_FW](https://www.volexity.com/blog/2022/06/15/driftingcloud-zero-day-sophos-firewall-exploitation-and-an-insidious-breach/)
- [taxonomy_downgrade_att_tls](https://arxiv.org/abs/1809.05681)
- [ad_blocker_with_miner](https://securelist.com/ad-blocker-with-miner-included/101105/)
- [Token tactics](https://www.microsoft.com/en-us/security/blog/2022/11/16/token-tactics-how-to-prevent-detect-and-respond-to-cloud-token-theft/)
- [mitm_tls_downgrade_att](https://www.praetorian.com/blog/man-in-the-middle-tls-ssl-protocol-downgrade-attack/)
- [Rapid7 MiTM Basics](https://www.rapid7.com/fundamentals/man-in-the-middle-attacks/)
- [tlseminar_downgrade_att](https://tlseminar.github.io/downgrade-attacks/)
- [ttint_rat](https://blog.netlab.360.com/ttint-an-iot-remote-control-trojan-spread-through-2-0-day-vulnerabilities/)
