# T1694.001 - Default Credentials

[ICS](../../../../README.md) / [Lateral Movement](../../README.md) / [T1694 - Insecure Credentials](../README.md)

Adversaries may leverage manufacturer or supplier set default credentials on control system devices. These default credentials may have administrative permissions and may be necessary for initial configuration of the device. It is general best practice to change the passwords for these accounts as soon as possible, but some manufacturers may have devices that have passwords or usernames that cannot be changed.(Citation: Keith Stouffer May 2015)

Default credentials are normally documented in an instruction manual that is either packaged with the device, published online through official means, or published online through unofficial means. Adversaries may leverage default credentials that have not been properly modified or disabled.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1694/001)

**Tactics**  [Persistence](../../../03%20TA0110%20-%20Persistence/README.md), [Lateral Movement](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0756 - Detection of Default Credentials](../../../../Defenses/Detection%20Strategies/DET0756%20-%20Detection%20of%20Default%20Credentials.md)

## Mitigations

- [M0801 - Access Management](../../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Ensure embedded controls and network devices are protected through access management, as these devices often have unknown default accounts which could be used to gain unauthorized access.
- [M0927 - Password Policies](../../../../Defenses/Mitigations/M0927%20-%20Password%20Policies.md) — Review vendor documents and security alerts for potentially unknown or overlooked default credentials within existing devices.

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0014 - Routers](../../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used default credentials to access Hitatchi RTUs, Mikronika RTUs, Hitachi Relion Protection and Control Relays, Mikronika HMI Computers, and Moxa NPort Serial Device Servers.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0066 - 2026 U.S. Water Utilities Attacks](../../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary logged in to internet-exposed PLCs using default credentials.(Citation: Tenable Minnesota Water Utilities) [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)
- [G1027 - CyberAv3ngers](../../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) accessed internet-accessible equipment using default credentials.(Citation: Tenable Minnesota Water Utilities)(Citation: Dispel Iran Water Utilities) [Dispel Iran Water Utilities](https://dispel.com/blog/minnesota-water-utility-attacks-secure-remote-access-ot) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)
- [C0031 - Unitronics Defacement Campaign](../../../../Threat%20Intelligence/Campaigns/C0031%20-%20Unitronics%20Defacement%20Campaign.md) — During the [Unitronics Defacement Campaign](https://attack.mitre.org/campaigns/C0031), the [CyberAv3ngers](https://attack.mitre.org/groups/G1027) discovered and exploited default credentials found on many Unitronics [Programmable Logic Controller (PLC)](https://attack.mitre.org/assets/A0003) [Human-Machine Interface (HMI)](https://attack.mitre.org/assets/A0002). For many of these devices, the default password was set to ‘1111’.(Citation: CISA AA23-335A IRGC-Affiliated December 2023)(Citation: CISA Unitronics November 2023) [CISA AA23-335A IRGC-Affiliated December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-335a) · [CISA Unitronics November 2023](https://www.cisa.gov/news-events/alerts/2023/11/28/exploitation-unitronics-plcs-used-water-and-wastewater-systems)

## Sources

- [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
