# T0801 - Monitor Process State

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may gather information about the physical process state. This information may be used to gain more information about the process itself or used as a trigger for malicious actions. The sources of process state information may vary such as, OPC tags, historian data, specific PLC block information, or network traffic.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0801)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [S1165 - FrostyGoop](../../../Threat%20Intelligence/Software/Malware/S1165%20-%20FrostyGoop.md) — [FrostyGoop](https://attack.mitre.org/software/S1165) can read data from holding registers via Modbus communication.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604)'s OPC and IEC 61850 protocol modules include the ability to send stVal requests to read the status of operational variables. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) uses a General Interrogation command to monitor the device’s Information Object Addresses (IOAs) and their IO state values.(Citation: Industroyer2 Forescout July 2022) [Industroyer2 Forescout July 2022](https://www.forescout.com/resources/industroyer2-and-incontroller-report/)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) examines fields recorded by the DP_RECV monitor to determine if the target system is in a particular state of operation. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — This type of attack technique cannot be easily mitigated with preventive controls since it is based on the abuse of system features.

## Detection strategies

- [DET0727 - Detection of Monitor Process State](../../../Defenses/Detection%20Strategies/DET0727%20-%20Detection%20of%20Monitor%20Process%20State.md)
