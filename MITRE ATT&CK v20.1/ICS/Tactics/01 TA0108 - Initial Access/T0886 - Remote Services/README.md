# T0886 - Remote Services

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may leverage remote services to move between assets and network segments. These services are often used to allow operators to interact with systems remotely within the network, some examples are RDP, SMB, SSH, and other similar mechanisms. (Citation: Blake Johnson, Dan Caban, Marina Krotofil, Dan Scali, Nathan Brubaker, Christopher Glyer December 2017) (Citation: Dragos December 2017) (Citation: Joe Slowik April 2019) 

Remote services could be used to support remote access, data transmission, authentication, name resolution, and other remote functions. Further, remote services may be necessary to allow operators and administrators to configure systems within the network from their engineering or management workstations. An adversary may use this technique to access devices which may be dual-homed (Citation: Blake Johnson, Dan Caban, Marina Krotofil, Dan Scali, Nathan Brubaker, Christopher Glyer December 2017) to multiple network segments, and can be used for [Program Download](https://attack.mitre.org/techniques/T0843) or to execute attacks on control devices directly through [Valid Accounts](https://attack.mitre.org/techniques/T0859).

Specific remote services (RDP & VNC) may be a precursor to enable [Graphical User Interface](https://attack.mitre.org/techniques/T0823) execution on devices such as HMIs or engineering workstation software.

Based on incident data, CISA and FBI assessed that Chinese state-sponsored actors also compromised various authorized remote access channels, including systems designed to transfer data and/or allow access between corporate and ICS networks.  (Citation: CISA AA21-201A Pipeline Intrusion July 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0886)

**Tactics**  [Initial Access](../README.md), [Lateral Movement](../../07%20TA0109%20-%20Lateral%20Movement/README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) used an IT helpdesk software to move the mouse on ICS control devices to maliciously release electricity breakers. (Citation: Andy Greenberg June 2017) [Andy Greenberg June 2017](https://www.wired.com/story/russian-hackers-attack-ukraine/)
- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) used MS-SQL access to a pivot machine, allowing code execution throughout the ICS network.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries gained initial access to the operational technology via the compromised Fortinet edge devices, and used used SSH, RDP, and SMB/Windows Admin Shares to connect to remote systems and execute commands.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), one victim reported actors leveraged Dropbear Secure Shell (SSH) software to enable remote access over port 22.(Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can use the CODESYS protocol to remotely connect to Schneider PLCs and perform maintenance functions on the device.(Citation: Wylie-22) [INCONTROLLER](https://attack.mitre.org/software/S1045) can use Telnet to upload payloads and execute commands on Omron PLCs. (Citation: Brubaker-Incontroller)(Citation: Dragos-Pipedream) The malware can also use HTTP-based CGI scripts (e.g., cpu.fcgi, ecat.fcgi) to gain administrative access to the device.(Citation: Wylie-22) [Dragos-Pipedream](https://hub.dragos.com/hubfs/116-Whitepapers/Dragos_ChernoviteWP_v2b.pdf?hsLang=en) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf) · [Brubaker-Incontroller](https://www.mandiant.com/resources/incontroller-state-sponsored-ics-tool)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) uses the SMB protocol to encrypt files located on remotely connected file shares. (Citation: Max Heinemeyer February 2020) [Max Heinemeyer February 2020](https://www.darktrace.com/en/blog/post-mortem-of-a-targeted-sodinokibi-ransomware-attack/)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) executes malicious SQL commands in the WinCC database server to propagate to remote systems. The malicious SQL commands include xp_cmdshell, sp_dumpdbilog, and sp_addextendedproc. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) utilized remote desktop protocol (RDP) jump boxes, poorly configured OT firewalls (Citation: Triton-EENews-2017), along with other traditional malware backdoors, to move into the ICS environment.(Citation: FireEye TRITON 2018)(Citation: Triton-EENews-2017) [Triton-EENews-2017](https://www.eenews.net/articles/the-inside-story-of-the-worlds-most-dangerous-malware/) · [FireEye TRITON 2018](https://web.archive.org/web/20200618231942/https://www.fireeye.com/blog/threat-research/2018/06/totally-tubular-treatise-on-triton-and-tristation.html)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Access Management technologies can help enforce authentication on critical remote service, examples include, but are not limited to, device management services (e.g., telnet, SSH), data access servers (e.g., HTTP, Historians), and HMI sessions (e.g., RDP, VNC).
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — Provide privileges corresponding to the restriction of a GUI session to control system operations (examples include HMI read-only vs. read-write modes). Ensure local users, such as operators and engineers, are giving prioritization over remote sessions and have the authority to regain control over a remote session if needed. Prevent remote access sessions (e.g., RDP, VNC) from taking over local sessions, especially those used for ICS control, especially HMIs.
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter application-layer protocol messages for remote services to block any unauthorized activity.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All remote services should require strong authentication before providing user access.
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Network allowlists can be implemented through either host-based files or system host files to specify what external connections (e.g., IP address, MAC address, port, protocol) can be made from a device.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment and control software movement between business and OT environments by way of one directional DMZs. Web access should be restricted from the OT environment. Engineering workstations, including transient cyber assets (TCAs) should have minimal connectivity to external networks, including Internet and email, further limit the extent to which these devices are dual-homed to multiple networks. (Citation: North America Transmission Forum December 2019) [North America Transmission Forum December 2019](https://www.natf.net/docs/natf/documents/resources/security/natf-transient-cyber-asset-guidance.pdf)
- [M0927 - Password Policies](../../../Defenses/Mitigations/M0927%20-%20Password%20Policies.md) — Enforce strong password requirements to prevent password brute force methods for lateral movement.
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — All communication sessions to remote services should be authenticated to prevent unauthorized access.
- [M0918 - User Account Management](../../../Defenses/Mitigations/M0918%20-%20User%20Account%20Management.md) — Limit the accounts that may use remote services. Limit the permissions for accounts that are at higher risk of compromise; for example, configure SSH so users can only run specific programs.

## Detection strategies

- [DET0804 - Detection of Remote Services](../../../Defenses/Detection%20Strategies/DET0804%20-%20Detection%20of%20Remote%20Services.md)

## Sources

- [Blake Johnson, Dan Caban, Marina Krotofil, Dan Scali, Nathan Brubaker, Christopher Glyer December 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)
- [CISA AA21-201A Pipeline Intrusion July 2021](https://us-cert.cisa.gov/sites/default/files/publications/AA21-201A_Chinese_Gas_Pipeline_Intrusion_Campaign_2011_to_2013%20%281%29.pdf)
- [Dragos December 2017](https://dragos.com/blog/trisis/TRISIS-01.pdf)
- [Joe Slowik April 2019](https://dragos.com/blog/industry-news/implications-of-it-ransomware-for-ics-environments/)
