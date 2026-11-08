# T1691 - Block Operational Technology Message

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may block messages between systems and devices in an OT/ICS environment to disrupt processes. Messages typically fall into two categories: (1) reporting messages that contain telemetry data about the current state of systems, devices, and processes and (2) command messages that contain instructions to control systems, devices, and processes. Both types of messages are critical for the proper functioning of industrial control processes and failure of the messages to reach their intended destinations could inhibit response functions or create an unsafe condition that could have physical impacts.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)(Citation: Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016)

Adversaries may block communications by either making modifications to software ([System Firmware](https://attack.mitre.org/techniques/T0857), [Module Firmware](https://attack.mitre.org/techniques/T0839), [Hooking](https://attack.mitre.org/techniques/T0874), and [Rootkit](https://attack.mitre.org/techniques/T0851)) and services ([Service Stop](https://attack.mitre.org/techniques/T0881), [Denial of Service](https://attack.mitre.org/techniques/T0814)) on systems and devices or by positioning themselves between systems and devices and intercepting and blocking the communications such as the case with an [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T0830) attack.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1691)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Sub-techniques

- [T1691.001 - Command Message](T1691.001%20-%20Command%20Message/README.md)
- [T1691.002 - Reporting Message](T1691.002%20-%20Reporting%20Message/README.md)

## Detection strategies

- [DET0903 - Detection of Block Operational Technology Message](../../../Defenses/Detection%20Strategies/DET0903%20-%20Detection%20of%20Block%20Operational%20Technology%20Message.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Mitigations

- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Utilize network allowlists to restrict unnecessary connections to network devices (e.g., comm servers, serial to ethernet converters) and services, especially in cases when devices have limits on the number of simultaneous sessions they support.
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Provide an alternative method for sending critical commands message to outstations, this could include using radio/cell communication to send messages to a field technician that physically performs the control function.
- [M0814 - Static Network Configuration](../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — Unauthorized connections can be prevented by statically defining the hosts and ports used for automation protocol connections.

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
- [Electricity Information Sharing and Analysis Center; SANS Industrial Control Systems March 2016](https://assets.contentstack.io/v3/assets/blt36c2e63521272fdc/blt6a77276749b76a40/607f235992f0063e5c070fff/E-ISAC_SANS_Ukraine_DUC_5%5b73%5d.pdf)
