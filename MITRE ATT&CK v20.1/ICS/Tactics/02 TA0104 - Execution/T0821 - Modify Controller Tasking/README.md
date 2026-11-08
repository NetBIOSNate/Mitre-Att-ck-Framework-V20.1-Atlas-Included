# T0821 - Modify Controller Tasking

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may modify the tasking of a controller to allow for the execution of their own programs. This can allow an adversary to manipulate the execution flow and behavior of a controller. 

According to 61131-3, the association of a Task with a Program Organization Unit (POU) defines a task association. (Citation: IEC February 2013) An adversary may modify these associations or create new ones to manipulate the execution flow of a controller. Modification of controller tasking can be accomplished using a Program Download in addition to other types of program modification such as online edit and program append.

Tasks have properties, such as interval, frequency and priority to meet the requirements of program execution. Some controller vendors implement tasks with implicit, pre-defined properties whereas others allow for these properties to be formulated explicitly. An adversary may associate their program with tasks that have a higher priority or execute associated programs more frequently. For instance, to ensure cyclic execution of their program on a Siemens controller, an adversary may add their program to the task, Organization Block 1 (OB1).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0821)

**Tactics**  [Execution](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Procedure examples

- [S1006 - PLC-Blaster](../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — [PLC-Blaster](https://attack.mitre.org/software/S1006)'s code is stored in OB9999. The original code on the target is untouched. The OB is automatically detected by the PLC and executed. (Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) infects OB1 so that its malicious code sequence is executed at the start of a cycle. It also infects OB35. OB35 acts as a watchdog, and on certain conditions, it can stop the execution of OB1. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009)'s argument-setting and inject.bin shellcode are added to the program table on the Tricon so that they are executed by the firmware once each cycle. (Citation: DHS CISA February 2019) (Citation: Jos Wetzels January 2018) [DHS CISA February 2019](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%20-%20Safety%20System%20Targeted%20Malware%20%28Update%20B%29.pdf) · [Jos Wetzels January 2018](https://www.midnightbluelabs.com/blog/2018/1/16/analyzing-the-triton-industrial-malware)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Provide the ability to verify the integrity of controller tasking. While techniques like CRCs and checksums are commonly used, they are not cryptographically secure and can be vulnerable to collisions. Preferably cryptographic hash functions (e.g., SHA-2, SHA-3) should be used. (Citation: IEC February 2019) [IEC February 2019](https://webstore.iec.ch/publication/34421)
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict the modification of controller tasks to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism.
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Utilize code signatures to verify the integrity and authenticity of programs installed on safety or control assets, including the associated controller tasking.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support Account Use Policies, Password Policies, and User Account Management.

## Detection strategies

- [DET0741 - Detection of Modify Controller Tasking](../../../Defenses/Detection%20Strategies/DET0741%20-%20Detection%20of%20Modify%20Controller%20Tasking.md)

## Sources

- [IEC February 2013](https://webstore.iec.ch/publication/4552)
