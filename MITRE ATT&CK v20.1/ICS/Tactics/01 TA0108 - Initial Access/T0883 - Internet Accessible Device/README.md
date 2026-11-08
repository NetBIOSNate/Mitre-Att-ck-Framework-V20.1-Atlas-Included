# T0883 - Internet Accessible Device

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may gain access into industrial environments through systems exposed directly to the internet for remote access rather than through [External Remote Services](https://attack.mitre.org/techniques/T0822). Internet Accessible Devices are exposed to the internet unintentionally or intentionally without adequate protections. This may allow for adversaries to move directly into the control system network. Access onto these devices is accomplished without the use of exploits, these would be represented within the [Exploit Public-Facing Application](https://attack.mitre.org/techniques/T0819) technique.

Adversaries may leverage built in functions for remote access which may not be protected or utilize minimal legacy protections that may be targeted. (Citation: NCCIC January 2014) These services may be discoverable through the use of online scanning tools. 

In the case of the Bowman dam incident, adversaries leveraged access to the dam control network through a cellular modem. Access to the device was protected by password authentication, although the application was vulnerable to brute forcing. (Citation: NCCIC January 2014) (Citation: Danny Yadron December 2015) (Citation: Mark Thompson March 2016)

In Trend Micros manufacturing deception operations adversaries were detected leveraging direct internet access to an ICS environment through the exposure of operational protocols such as Siemens S7, Omron FINS, and EtherNet/IP, in addition to misconfigured VNC access. (Citation: Stephen Hilt, Federico Maggi, Charles Perine, Lord Remorin, Martin Rsler, and Rainer Vosseler)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0883)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary located internet-exposed PLCs (e.g., Rockwell Automation/Allen-Bradley MicroLogix 1100 and 1400 PLCs, etc.) at water and wastewater utilities, including cellular-connected water towers and sewer lift stations, and logged in to them directly.(Citation: Tenable Minnesota Water Utilities)(Citation: Forescout Water Systems Attack)(Citation: FBI Water and Wastewater) [FBI Water and Wastewater](https://www.fbi.gov/investigate/cyber/alerts/2026/malicious-cyber-actors-targeting-water-and-wastewater-sector-internet--facing-programmable-logic-controllers-causing-operational-disruptions) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know) · [Forescout Water Systems Attack](https://www.forescout.com/blog/ot-security-analysis-exposed-devices-attacked-in-us-water-systems/)
- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) accessed internet accessible PLCs that were exposed through cellular gateways across multiple vendors including Rockwell Automation/Allen-Bradley, Schneider Electric, and Siemens.(Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1157 - Fuxnet](../../../Threat%20Intelligence/Software/Malware/S1157%20-%20Fuxnet.md) — [Fuxnet](https://attack.mitre.org/software/S1157) execution relied upon accessing Internet-accessible devices for initial access and deployment.(Citation: Claroty Fuxnet 2024) [Claroty Fuxnet 2024](https://claroty.com/team82/research/unpacking-the-blackjack-groups-fuxnet-malware)
- [C0031 - Unitronics Defacement Campaign](../../../Threat%20Intelligence/Campaigns/C0031%20-%20Unitronics%20Defacement%20Campaign.md) — During the [Unitronics Defacement Campaign](https://attack.mitre.org/campaigns/C0031), the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) exploited devices connected to the public internet, such as internet connected Unitronics [Programmable Logic Controller (PLC)](https://attack.mitre.org/assets/A0003) with [Human-Machine Interface (HMI)](https://attack.mitre.org/assets/A0002) and networking equipment such as cellular modems found in OT environments.(Citation: CISA AA23-335A IRGC-Affiliated December 2023)(Citation: Lisa Zahner December 2023) [CISA AA23-335A IRGC-Affiliated December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-335a) · [Lisa Zahner December 2023](https://veronews.com/2023/12/15/hackers-in-iran-attack-computer-at-vero-utilities/)

## Mitigations

- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls. Steps should be taken to periodically inventory internet accessible devices to determine if it differs from the expected.

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0796 - Detection of Internet Accessible Device](../../../Defenses/Detection%20Strategies/DET0796%20-%20Detection%20of%20Internet%20Accessible%20Device.md)

## Sources

- [Danny Yadron December 2015](https://www.wsj.com/articles/iranian-hackers-infiltrated-new-york-dam-in-2013-1450662559)
- [Mark Thompson March 2016](https://time.com/4270728/iran-cyber-attack-dam-fbi/)
- [NCCIC January 2014](https://www.us-cert.gov/sites/default/files/Monitors/ICS-CERT_Monitor_Jan-April2014.pdf)
- [Stephen Hilt, Federico Maggi, Charles Perine, Lord Remorin, Martin Rsler, and Rainer Vosseler](https://documents.trendmicro.com/assets/white_papers/wp-caught-in-the-act-running-a-realistic-factory-honeypot-to-capture-real-threats.pdf)
