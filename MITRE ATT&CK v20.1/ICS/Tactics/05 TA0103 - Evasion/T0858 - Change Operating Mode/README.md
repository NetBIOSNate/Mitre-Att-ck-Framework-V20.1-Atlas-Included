# T0858 - Change Operating Mode

[ICS](../../../README.md) / [Evasion](../README.md)

Adversaries may change the operating mode of a controller to gain additional access to engineering functions such as Program Download.   Programmable controllers typically have several modes of operation that control the state of the user program and control access to the controllers API. Operating modes can be physically selected using a key switch on the face of the controller but may also be selected with calls to the controllers API. Operating modes and the mechanisms by which they are selected often vary by vendor and product line. Some commonly implemented operating modes are described below:  

* Program - This mode must be enabled before changes can be made to a devices program. This allows program uploads and downloads between the device and an engineering workstation. Often the PLCs logic Is halted, and all outputs may be forced off. (Citation: N.A. October 2017)  
* Run - Execution of the devices program occurs in this mode. Input and output (values, points, tags, elements, etc.) are monitored and used according to the programs logic. [Program Upload](https://attack.mitre.org/techniques/T0845) and [Program Download](https://attack.mitre.org/techniques/T0843) are disabled while in this mode. (Citation: Omron) (Citation: Machine Information Systems 2007)  (Citation: N.A. October 2017) (Citation: PLCgurus 2021)   
* Remote - Allows for remote changes to a PLCs operation mode. (Citation: PLCgurus 2021)    
* Stop - The PLC and program is stopped, while in this mode, outputs are forced off. (Citation: Machine Information Systems 2007)   
* Reset - Conditions on the PLC are reset to their original states. Warm resets may retain some memory while cold resets will reset all I/O and data registers. (Citation: Machine Information Systems 2007)   
* Test / Monitor mode - Similar to run mode, I/O is processed, although this mode allows for monitoring, force set, resets, and more generally tuning or debugging of the system. Often monitor mode may be used as a trial for initialization. (Citation: Omron)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0858)

**Tactics**  [Execution](../../02%20TA0104%20-%20Execution/README.md), [Evasion](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict operating mode changes to only required authenticated users (e.g., engineers, field technicians), preferably through implementing a role-based access mechanism. Further, physical mechanisms (e.g., keys) can also be used to limit unauthorized operating mode changes.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Procedure examples

- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can establish a remote HTTP connection to change the operating mode of Omron PLCs.(Citation: Dragos-Pipedream)(Citation: Wylie-22) [Dragos-Pipedream](https://hub.dragos.com/hubfs/116-Whitepapers/Dragos_ChernoviteWP_v2b.pdf?hsLang=en) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S1006 - PLC-Blaster](../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — [PLC-Blaster](https://attack.mitre.org/software/S1006) stops the execution of the user program on the target to enable the transfer of its own code. The worm then copies itself to the target and subsequently starts the target PLC again. (Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) has the ability to halt or run a program through the TriStation protocol. TsHi.py contains instances of halt and run functions being executed.(Citation: MDudek-ICS) [MDudek-ICS](https://github.com/MDudek-ICS/TRISIS-TRITON-HATMAN/tree/master/decompiled_code/library)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Detection strategies

- [DET0755 - Detection of Change Operating Mode](../../../Defenses/Detection%20Strategies/DET0755%20-%20Detection%20of%20Change%20Operating%20Mode.md)

## Sources

- [Machine Information Systems 2007](http://www.machine-information-systems.com/How_PLCs_Work.html)
- [N.A. October 2017](https://forumautomation.com/t/what-are-the-different-operating-modes-in-plc/2489)
- [Omron](https://www.omron-ap.com/service_support/FAQ/FAQ00002/index.asp#:~:text=In%20PROGRAM%20mode%2C%20the%20CPU,can%20be%20created%20or%20modified.)
- [PLCgurus 2021](https://www.plcgurus.net/plc-basics/)
