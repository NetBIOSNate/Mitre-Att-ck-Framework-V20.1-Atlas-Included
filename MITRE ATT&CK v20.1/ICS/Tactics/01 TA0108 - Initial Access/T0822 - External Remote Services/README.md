# T0822 - External Remote Services

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may leverage external remote services as a point of initial access into your network. These services allow users to connect to internal network resources from external locations. Examples are VPNs, Citrix, and other access mechanisms. Remote service gateways often manage connections and credential authentication for these services. (Citation: Daniel Oakley, Travis Smith, Tripwire)

External remote services allow administration of a control system from outside the system. Often, vendors and internal engineering groups have access to external remote services to control system networks via the corporate network. In some cases, this access is enabled directly from the internet. While remote access enables ease of maintenance when a control system is in a remote area, compromise of remote access solutions is a liability. The adversary may use these services to gain access to and execute attacks against a control system network. Access to valid accounts is often a requirement. 

As they look for an entry point into the control system network, adversaries may begin searching for existing point-to-point VPN implementations at trusted third party networks or through remote support employee connections where split tunneling is enabled. (Citation: Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0822)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) used Valid Accounts taken from the Windows Domain Controller to access the control system Virtual Private Network (VPN) used by grid operators. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries gained initial access by compromising Fortinet edge devices. (Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S1157 - Fuxnet](../../../Threat%20Intelligence/Software/Malware/S1157%20-%20Fuxnet.md) — [Fuxnet](https://attack.mitre.org/software/S1157) initial execution relied on accessing external remote services for victim environments.(Citation: Claroty Fuxnet 2024) [Claroty Fuxnet 2024](https://claroty.com/team82/research/unpacking-the-blackjack-groups-fuxnet-malware)
- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary gained remote computer access to the system over radio.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0014 - Routers](../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)

## Mitigations

- [M0936 - Account Use Policies](../../../Defenses/Mitigations/M0936%20-%20Account%20Use%20Policies.md) — Configure features related to account use like login attempt lockouts, specific login times, and password strength requirements as examples. Consider these features as they relate to assets which may impact safety and availability. (Citation: Keith Stouffer May 2015) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0942 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider removal of remote services which are not regularly in use, or only enabling them when required (e.g., vendor remote access). Ensure all external remote access point (e.g., jump boxes, VPN concentrator) are configured with least functionality, especially the removal of unnecessary services. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0935 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M0935%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit access to remote services through centrally managed concentrators such as VPNs and other managed remote access systems.
- [M0932 - Multi-factor Authentication](../../../Defenses/Mitigations/M0932%20-%20Multi-factor%20Authentication.md) — Use strong multi-factor authentication for remote service accounts to mitigate an adversary's ability to leverage stolen credentials. Be aware of multi-factor authentication interception techniques for some implementations.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls. Consider a jump server or host into the DMZ for greater access control. Leverage this DMZ or corporate resources for vendor access. (Citation: Keith Stouffer May 2015) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0927 - Password Policies](../../../Defenses/Mitigations/M0927%20-%20Password%20Policies.md) — Set and enforce secure password policies for accounts.
- [M0918 - User Account Management](../../../Defenses/Mitigations/M0918%20-%20User%20Account%20Management.md) — Consider utilizing jump boxes for external remote access. Additionally, dynamic account management may be used to easily remove accounts when not in use.

## Detection strategies

- [DET0803 - Detection of External Remote Services](../../../Defenses/Detection%20Strategies/DET0803%20-%20Detection%20of%20External%20Remote%20Services.md)

## Sources

- [Daniel Oakley, Travis Smith, Tripwire](https://attack.mitre.org/wiki/Technique/T1133)
- [Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016](https://assets.contentstack.io/v3/assets/blt36c2e63521272fdc/blt6a77276749b76a40/607f235992f0063e5c070fff/E-ISAC_SANS_Ukraine_DUC_5%5b73%5d.pdf)
