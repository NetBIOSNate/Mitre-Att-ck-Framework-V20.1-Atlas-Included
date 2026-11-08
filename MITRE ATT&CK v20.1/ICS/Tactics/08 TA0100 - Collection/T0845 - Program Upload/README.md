# T0845 - Program Upload

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may attempt to upload a program from a PLC to gather information about an industrial process. Uploading a program may allow them to acquire and study the underlying logic. Methods of program upload include vendor software, which enables the user to upload and read a program running on a PLC. This software can be used to upload the target program to a workstation, jump box, or an interfacing device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0845)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict program uploads to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter for protocols and payloads associated with program upload activity to prevent unauthorized access to device configurations.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Detection strategies

- [DET0761 - Detection of Program Upload](../../../Defenses/Detection%20Strategies/DET0761%20-%20Detection%20of%20Program%20Upload.md)

## Procedure examples

- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) used the program upload feature to exfiltrate project files from victim PLCs. (Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can use the CODESYS protocol to upload programs from Schneider PLCs.(Citation: Wylie-22)(Citation: Brubaker-Incontroller) [INCONTROLLER](https://attack.mitre.org/software/S1045) can obtain existing program logic from Omron PLCs by using either the program upload or backup functions available through the HTTP server.(Citation: Wylie-22) [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf) · [Brubaker-Incontroller](https://www.mandiant.com/resources/incontroller-state-sponsored-ics-tool)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) calls the SafeAppendProgramMod to transfer its payloads to the Tricon. Part of this call includes preforming a program upload. (Citation: MDudek-ICS) [MDudek-ICS](https://github.com/MDudek-ICS/TRISIS-TRITON-HATMAN/tree/master/decompiled_code/library)
