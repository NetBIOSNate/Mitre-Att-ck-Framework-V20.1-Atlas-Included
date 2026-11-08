# T0892 - Change Credential

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may modify software and device credentials to prevent operator and responder access. Depending on the device, the modification or addition of this password could prevent any device configuration actions from being accomplished and may require a factory reset or replacement of hardware. These credentials are often built-in features provided by the device vendors as a means to restrict access to management interfaces.

An adversary with access to valid or hardcoded credentials could change the credential to prevent future authorized device access. Change Credential may be especially damaging when paired with other techniques such as Modify Program, Data Destruction, or Modify Controller Tasking. In these cases, a device’s configuration may be destroyed or include malicious actions for the process environment, which cannot not be removed through normal device configuration actions. 

Additionally, recovery of the device and original configuration may be difficult depending on the features provided by the device. In some cases, these passwords cannot be removed onsite and may require that the device be sent back to the vendor for additional recovery steps.


A chain of incidents occurred in Germany, where adversaries locked operators out of their building automation system (BAS) controllers by enabling a previously unset BCU key. (Citation: German BAS Lockout Dec 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0892)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
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

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries changed the login password of Moxa NPort Serial Device Servers to impede system recovery.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary remotely accessed internet-facing devices (e.g., MicroLogix 1100 and 1400 controllers, etc.) and changed passwords resulting in loss of monitoring and control for the affected utilities.(Citation: Tenable Minnesota Water Utilities)(Citation: Forescout Water Systems Attack)(Citation: Dragos Water Under Attack)(Citation: FBI Water and Wastewater) [FBI Water and Wastewater](https://www.fbi.gov/investigate/cyber/alerts/2026/malicious-cyber-actors-targeting-water-and-wastewater-sector-internet--facing-programmable-logic-controllers-causing-operational-disruptions) · [Dragos Water Under Attack](https://www.dragos.com/blog/water-utility-attacks-decade-of-gaps) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know) · [Forescout Water Systems Attack](https://www.forescout.com/blog/ot-security-analysis-exposed-devices-attacked-in-us-water-systems/)
- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) locked out operators by changing the PLCs passwords and IP addresses.(Citation: Tenable Minnesota Water Utilities) [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)

## Detection strategies

- [DET0771 - Detection of Change Credential](../../../Defenses/Detection%20Strategies/DET0771%20-%20Detection%20of%20Change%20Credential.md)

## Mitigations

- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Take and store data backups from end user systems and critical servers. Ensure backup and storage systems are hardened and kept separate from the corporate network to prevent compromise. Maintain and exercise incident response plans (Citation: Department of Homeland Security October 2009), including the management of gold-copy back-up images and configurations for key systems to enable quick recovery and response from adversarial activities that impact control, view, or availability. [Department of Homeland Security October 2009](https://us-cert.cisa.gov/sites/default/files/recommended_practices/final-RP_ics_cybersecurity_incident_response_100609.pdf)
- [M0927 - Password Policies](../../../Defenses/Mitigations/M0927%20-%20Password%20Policies.md) — Applications and appliances that utilize default username and password should be changed immediately after the installation, and before deployment to a production environment.(Citation: CISA June 2013) [CISA June 2013](https://us-cert.cisa.gov/ncas/alerts/TA13-175A)
- [M0811 - Redundancy of Service](../../../Defenses/Mitigations/M0811%20-%20Redundancy%20of%20Service.md) — Retain cold-standby or replacement hardware of similar models to ensure continued operations of critical functions if the primary system is compromised or unavailable. (Citation: M. Rentschler and H. Heine) [M. Rentschler and H. Heine](https://ieeexplore.ieee.org/document/6505877)

## Sources

- [German BAS Lockout Dec 2021](https://www.darkreading.com/attacks-breaches/lights-out-cyberattacks-shut-down-building-automation-systems)
