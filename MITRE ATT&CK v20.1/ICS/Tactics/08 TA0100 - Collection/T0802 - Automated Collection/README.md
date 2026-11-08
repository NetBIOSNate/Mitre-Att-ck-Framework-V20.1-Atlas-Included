# T0802 - Automated Collection

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may automate collection of industrial environment information using tools or scripts. This automated collection may leverage native control protocols and tools available in the control systems environment. For example, the OPC protocol may be used to enumerate and gather information. Access to a system or interface with these native protocols may allow collection and enumeration of other attached, communicating servers and devices.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0802)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)

## Mitigations

- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Utilize network allowlists to restrict unnecessary connections to network devices (e.g., comm servers, serial to ethernet converters) and services, especially in cases when devices have limits on the number of simultaneous sessions they support.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Prevent unauthorized systems from accessing control servers or field devices containing industrial information, especially services used for common automation protocols (e.g., DNP3, OPC).

## Procedure examples

- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — Using OPC, a component of [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) gathers any details about connected devices and sends them back to the C2 for the attackers to analyze. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) automatically collects protocol object data to learn about control devices in the environment. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) leverages a hardcoded list of remote-station IP addresses to iteratively initiate communications and collect information across multiple priority IEC-104 priority levels.(Citation: Industroyer2 Forescout July 2022) [Industroyer2 Forescout July 2022](https://www.forescout.com/resources/industroyer2-and-incontroller-report/)

## Detection strategies

- [DET0734 - Detection of Automated Collection](../../../Defenses/Detection%20Strategies/DET0734%20-%20Detection%20of%20Automated%20Collection.md)
