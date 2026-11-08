# T1691.001 - Command Message

[ICS](../../../../README.md) / [Inhibit Response Function](../../README.md) / [T1691 - Block Operational Technology Message](../README.md)

Adversaries may block a command message from reaching its intended target to prevent command execution. In OT networks, command messages are sent to provide instructions to control system devices. A blocked command message can inhibit response functions from correcting a disruption or unsafe condition.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)(Citation: Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1691/001)

**Tactics**  [Inhibit Response Function](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0784 - Detection of Block Command Message](../../../../Defenses/Detection%20Strategies/DET0784%20-%20Detection%20of%20Block%20Command%20Message.md)

## Mitigations

- [M0807 - Network Allowlists](../../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Utilize network allowlists to restrict unnecessary connections to network devices (e.g., comm servers, serial to ethernet converters) and services, especially in cases when devices have limits on the number of simultaneous sessions they support.
- [M0810 - Out-of-Band Communications Channel](../../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Provide an alternative method for sending critical command messages to outstations, this could include using radio/cell communication to send messages to a field technician that physically performs the control function.
- [M0814 - Static Network Configuration](../../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — Unauthorized connections can be prevented by statically defining the hosts and ports used for automation protocol connections.

## Targeted assets

- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) blocked command messages by using malicious firmware to render serial-to-ethernet converters inoperable. (Citation: Ukraine15 - EISAC - 201603) [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [S0604 - Industroyer](../../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — In [Industroyer](https://attack.mitre.org/software/S0604) the first COM port from the configuration file is used for the actual communication and the two other COM ports are just opened to prevent other processes accessing them. Thus, the IEC 101 payload component is able to take over and maintain control of the RTU device. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
- [Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016](https://assets.contentstack.io/v3/assets/blt36c2e63521272fdc/blt6a77276749b76a40/607f235992f0063e5c070fff/E-ISAC_SANS_Ukraine_DUC_5%5b73%5d.pdf)
