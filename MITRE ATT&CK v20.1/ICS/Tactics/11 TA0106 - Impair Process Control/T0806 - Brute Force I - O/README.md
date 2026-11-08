# T0806 - Brute Force I/O

[ICS](../../../README.md) / [Impair Process Control](../README.md)

Adversaries may repetitively or successively change I/O point values to perform an action. Brute Force I/O may be achieved by changing either a range of I/O point values or a single point value repeatedly to manipulate a process function. The adversary's goal and the information they have about the target environment will influence which of the options they choose. In the case of brute forcing a range of point values, the adversary may be able to achieve an impact without targeting a specific point. In the case where a single point is targeted, the adversary may be able to generate instability on the process function associated with that particular point. 

Adversaries may use Brute Force I/O to cause failures within various industrial processes. These failures could be the result of wear on equipment or damage to downstream equipment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0806)

**Tactics**  [Impair Process Control](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [S1157 - Fuxnet](../../../Threat%20Intelligence/Software/Malware/S1157%20-%20Fuxnet.md) — [Fuxnet](https://attack.mitre.org/software/S1157) repeatedly wrote arbitrary data over the Meter-Bus channel from impacted devices to connected sensors to render sensor data acquisition useless.(Citation: Claroty Fuxnet 2024) [Claroty Fuxnet 2024](https://claroty.com/team82/research/unpacking-the-blackjack-groups-fuxnet-malware)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The [Industroyer](https://attack.mitre.org/software/S0604) IEC 104 module has 3 modes available to perform its attack. These modes are range, shift, and sequence. The range mode operates in 2 stages. The first stage of range mode gathers Information Object Addresses (IOA) and sends select and execute packets to switch the state. The second stage of range mode has an infinite loop where it will switch the state of all of the previously discovered IOAs. Shift mode is similar to range mode, but instead of staying within the same range, it will add a shift value to the default range values. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) can iterate across a device’s IOAs to modify the ON/OFF value of a given IO state.(Citation: Industroyer2 Mandiant April 2022)(Citation: Industroyer2 Forescout July 2022) [Industroyer2 Mandiant April 2022](https://www.mandiant.com/resources/blog/industroyer-v2-old-malware-new-tricks) · [Industroyer2 Forescout July 2022](https://www.forescout.com/resources/industroyer2-and-incontroller-report/)

## Mitigations

- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Allow/denylists can be used to block access when excessive I/O connections are detected from a system or device during a specified time period.
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Utilize network allowlists to restrict unnecessary connections to network devices (e.g., comm servers, serial to ethernet converters) and services, especially in cases when devices have limits on the number of simultaneous sessions they support.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational assets and their management devices based on their functional role within the process. Enabling more strict isolation to more critical control and operational information within the control environment. (Citation: Karen Scarfone; Paul Hoffman September 2009) (Citation: Keith Stouffer May 2015) (Citation: Department of Homeland Security September 2016) (Citation: Dwight Anderson 2014) [Karen Scarfone; Paul Hoffman September 2009](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-41r1.pdf) · [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf) · [Dwight Anderson 2014](https://www.sans.org/reading-room/whitepapers/ICS/protect-critical-infrastructure-systems-whitelisting-35312)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Devices should authenticate all messages between master and outstation assets.

## Detection strategies

- [DET0737 - Detection of Brute Force I/O](../../../Defenses/Detection%20Strategies/DET0737%20-%20Detection%20of%20Brute%20Force%20I%20-%20O.md)
