# T0830 - Adversary-in-the-Middle

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries with privileged network access may seek to modify network traffic in real time using adversary-in-the-middle (AiTM) attacks. (Citation: Gabriel Sanchez October 2017) This type of attack allows the adversary to intercept traffic to and/or from a particular device on the network. If a AiTM attack is established, then the adversary has the ability to block, log, modify, or inject traffic into the communication stream. There are several ways to accomplish this attack, but some of the most-common are Address Resolution Protocol (ARP) poisoning and the use of a proxy. (Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)  

An AiTM attack may allow an adversary to perform the following attacks:  
[Block Reporting Message](https://attack.mitre.org/techniques/T0804), [Spoof Reporting Message](https://attack.mitre.org/techniques/T0856), [Modify Parameter](https://attack.mitre.org/techniques/T0836), [Unauthorized Command Message](https://attack.mitre.org/techniques/T0855)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0830)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0014 - Routers](../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) changed phone numbers tied to certain specific accounts in a designated contact list. They then used the changed phone numbers to redirect network traffic to websites controlled by them, thereby allowing them to capture and use any login codes sent to the devices via text message.(Citation: Triton-EENews-2017) [Triton-EENews-2017](https://www.eenews.net/articles/the-inside-story-of-the-worlds-most-dangerous-malware/)
- [S1010 - VPNFilter](../../../Threat%20Intelligence/Software/Malware/S1010%20-%20VPNFilter.md) — The [VPNFilter](https://attack.mitre.org/software/S1010)'s ssler module configures the device's iptables to redirect all traffic destined for port 80 to its local service listening on port 8888. Any outgoing web requests on port 80 are now intercepted by ssler and can be inspected by the ps module and manipulated before being sent to the legitimate HTTP service. (Citation: William Largent June 2018) (Citation: Carl Hurd March 2019) [Carl Hurd March 2019](https://www.youtube.com/watch?v=yuZazP22rpI) · [William Largent June 2018](https://blog.talosintelligence.com/2018/06/vpnfilter-update.html)

## Detection strategies

- [DET0764 - Detection of Adversary-in-the-Middle](../../../Defenses/Detection%20Strategies/DET0764%20-%20Detection%20of%20Adversary-in-the-Middle.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Limit access to network infrastructure and resources that can be used to reshape traffic or otherwise produce AiTM conditions.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Communication authenticity will ensure that any messages tampered with through AiTM can be detected, but cannot prevent eavesdropping on these. In addition, providing communication authenticity around various discovery protocols, such as DNS, can be used to prevent various AiTM procedures.
- [M0942 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable unnecessary legacy network protocols that may be used for AiTM if applicable.
- [M0931 - Network Intrusion Prevention](../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that can identify traffic patterns indicative of AiTM activity can be used to mitigate activity at the network level.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Network segmentation can be used to isolate infrastructure components that do not require broad network access. This may mitigate, or at least alleviate, the scope of AiTM activity.
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Utilize out-of-band communication to validate the integrity of data from the primary channel.
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — To protect against AiTM, authentication mechanisms should not send credentials across the network in plaintext and should also implement mechanisms to prevent replay attacks (such as nonces or timestamps). Challenge-response based authentication techniques that do not directly send credentials over the network provide better protection from AiTM.
- [M0814 - Static Network Configuration](../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — Statically defined ARP entries can prevent manipulation and sniffing of switched network traffic, as some AiTM techniques depend on sending spoofed ARP messages to manipulate network host's dynamic ARP tables.

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
- [Gabriel Sanchez October 2017](https://www.sans.org/reading-room/whitepapers/ICS/man-in-the-middle-attack-modbus-tcp-illustrated-wireshark-38095)
