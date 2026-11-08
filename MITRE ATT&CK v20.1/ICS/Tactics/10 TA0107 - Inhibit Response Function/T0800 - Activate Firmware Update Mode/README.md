# T0800 - Activate Firmware Update Mode

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may activate firmware update mode on devices to prevent expected response functions from engaging in reaction to an emergency or process malfunction. For example, devices such as protection relays may have an operation mode designed for firmware installation. This mode may halt process monitoring and related functions to allow new firmware to be loaded. A device left in update mode may be placed in an inactive holding state if no firmware is provided to it. By entering and leaving a device in this mode, the adversary may deny its usual functionalities.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0800)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — All devices or systems changes, including all administrative functions, should require authentication. Consider using access management technologies to enforce authorization on all management interface access attempts, especially when the device does not inherently provide strong authentication and authorization functions.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — Restrict configurations changes and firmware updating abilities to only authorized individuals.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter for protocols and payloads associated with firmware activation or updating activity.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — Devices that allow remote management of firmware should require authentication before allowing any changes. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918)
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Procedure examples

- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The [Industroyer](https://attack.mitre.org/software/S0604) SIPROTEC DoS module places the victim device into firmware update mode. This is a legitimate use case under normal circumstances, but in this case is used the adversary to prevent the SIPROTEC from performing its designed protective functions. As a result the normal safeguards are disabled, leaving an unprotected link in the electric transmission. (Citation: Joe Slowik August 2019) [Joe Slowik August 2019](https://dragos.com/wp-content/uploads/CRASHOVERRIDE.pdf)

## Detection strategies

- [DET0802 - Detection of Activate Firmware Update Mode](../../../Defenses/Detection%20Strategies/DET0802%20-%20Detection%20of%20Activate%20Firmware%20Update%20Mode.md)
