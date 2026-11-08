# T0868 - Detect Operating Mode

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may gather information about a PLCs or controllers current operating mode. Operating modes dictate what change or maintenance functions can be manipulated and are often controlled by a key switch on the PLC (e.g.,  run, prog [program], and remote). Knowledge of these states may be valuable to an adversary to determine if they are able to reprogram the PLC. Operating modes and the mechanisms by which they are selected often vary by vendor and product line. Some commonly implemented operating modes are described below:  

* Program - This mode must be enabled before changes can be made to a devices program. This allows program uploads and downloads between the device and an engineering workstation. Often the PLCs logic Is halted, and all outputs may be forced off. (Citation: N.A. October 2017)  
* Run - Execution of the devices program occurs in this mode. Input and output (values, points, tags, elements, etc.) are monitored and used according to the programs logic.[Program Upload](https://attack.mitre.org/techniques/T0845) and [Program Download](https://attack.mitre.org/techniques/T0843) are disabled while in this mode. (Citation: Omron) (Citation: Machine Information Systems 2007)  (Citation: N.A. October 2017) (Citation: PLCgurus 2021)   
* Remote - Allows for remote changes to a PLCs operation mode. (Citation: PLCgurus 2021)    
* Stop - The PLC and program is stopped, while in this mode, outputs are forced off. (Citation: Machine Information Systems 2007)   
* Reset - Conditions on the PLC are reset to their original states. Warm resets may retain some memory while cold resets will reset all I/O and data registers. (Citation: Machine Information Systems 2007)   
* Test / Monitor mode - Similar to run mode, I/O is processed, although this mode allows for monitoring, force set, resets, and more generally tuning or debugging of the system. Often monitor mode may be used as a trial for initialization. (Citation: Omron)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0868)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict the modification of programs to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Perform inline allowlisting of automation protocol commands to prevent devices from sending unauthorized command or reporting messages. Allow/denylist techniques need to be designed with sufficient accuracy to prevent the unintended blocking of valid messages.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) contains a file named TS_cnames.py which contains default definitions for program state (TS_progstate). Program state is referenced in TsHi.py.(Citation: MDudek-ICS) [Triton](https://attack.mitre.org/software/S1009) contains a file named TS_cnames.py which contains default definitions for key state (TS_keystate). Key state is referenced in TsHi.py.(Citation: MDudek-ICS) [MDudek-ICS](https://github.com/MDudek-ICS/TRISIS-TRITON-HATMAN/tree/master/decompiled_code/library)

## Detection strategies

- [DET0768 - Detection of Detect Operating Mode](../../../Defenses/Detection%20Strategies/DET0768%20-%20Detection%20of%20Detect%20Operating%20Mode.md)

## Sources

- [Machine Information Systems 2007](http://www.machine-information-systems.com/How_PLCs_Work.html)
- [N.A. October 2017](https://forumautomation.com/t/what-are-the-different-operating-modes-in-plc/2489)
- [Omron](https://www.omron-ap.com/service_support/FAQ/FAQ00002/index.asp#:~:text=In%20PROGRAM%20mode%2C%20the%20CPU,can%20be%20created%20or%20modified.)
- [PLCgurus 2021](https://www.plcgurus.net/plc-basics/)
