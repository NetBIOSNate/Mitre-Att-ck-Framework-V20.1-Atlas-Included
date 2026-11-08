# T0843.002 - Online Edit

[ICS](../../../../README.md) / [Lateral Movement](../../README.md) / [T0843 - Program Download](../README.md)

Adversaries may execute an online edit of a PLC to update parts of an existing program. It does not require stopping the PLC which allows it to continue running during transfer and reconfiguration without interruption to process control. Adversaries may leverage this approach to minimize downtime and evade detection. 

The ability to perform an online edit to the PLC typically relies on access to a workstation with the vendor-specific PLC programming software installed.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0843/002)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Mitigations

- [M0801 - Access Management](../../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0947 - Audit](../../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Provide the ability to verify the integrity of programs downloaded on a controller. While techniques like CRCs and checksums are commonly used, they are not cryptographically secure and can be vulnerable to collisions. Preferably cryptographic hash functions (e.g., SHA-2, SHA-3) should be used.(Citation: IEC February 2019) [IEC February 2019](https://webstore.iec.ch/publication/34421)
- [M0800 - Authorization Enforcement](../../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — ll field controllers should restrict the download of programs, including online edits and program appends, to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism.
- [M0945 - Code Signing](../../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Utilize code signatures to verify the integrity and authenticity of programs downloaded to the device.
- [M0802 - Communication Authenticity](../../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0937 - Filter Network Traffic](../../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter for protocols and payloads associated with program download activity to prevent unauthorized device configurations.
- [M0804 - Human User Authentication](../../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Detection strategies

- [DET0915 - Detection of Online Edit](../../../../Defenses/Detection%20Strategies/DET0915%20-%20Detection%20of%20Online%20Edit.md)
