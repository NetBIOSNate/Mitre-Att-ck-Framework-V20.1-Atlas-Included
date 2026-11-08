# T1693 - Modify Firmware

[ICS](../../../README.md) / [Persistence](../README.md)

Firmware is low-level software embedded in hardware that enables systems and devices to function properly and is commonly found in ICS environments. Adversaries may modify firmware on a system or device by installing malicious or vulnerable versions that enable them to achieve objectives such as [Persistence](https://attack.mitre.org/tactics/TA0110), [Impair Process Control](https://attack.mitre.org/tactics/TA0106), and [Inhibit Response Function](https://attack.mitre.org/tactics/TA0107). 

Adversaries may modify system and device firmware by using the built-in firmware update functionality which may support local or remote installation. The malicious or vulnerable firmware may be delivered via [Replication Through Removable Media](https://attack.mitre.org/techniques/T0847), [Supply Chain Compromise](https://attack.mitre.org/techniques/T0862), or [Remote Services](https://attack.mitre.org/techniques/T0886). Once installed, the malicious or vulnerable firmware could be used to provide [Rootkit](https://attack.mitre.org/techniques/T0851) and [Hooking](https://attack.mitre.org/techniques/T0874) functionality, [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T0890), or [Denial of Service](https://attack.mitre.org/techniques/T0814).(Citation: Basnight, Zachry, et al.)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1693)

**Tactics**  [Persistence](../README.md), [Inhibit Response Function](../../10%20TA0107%20-%20Inhibit%20Response%20Function/README.md), [Impair Process Control](../../11%20TA0106%20-%20Impair%20Process%20Control/README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Sub-techniques

- [T1693.002 - Module Firmware](T1693.002%20-%20Module%20Firmware/README.md)
- [T1693.001 - System Firmware](T1693.001%20-%20System%20Firmware/README.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — All devices or systems changes, including all administrative functions, should require authentication. Consider using access management technologies to enforce authorization on all management interface access attempts, especially when the device does not inherently provide strong authentication and authorization functions.
- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Perform integrity checks of firmware before uploading it on a device. Utilize cryptographic hashes to verify the firmware has not been tampered with by comparing it to a trusted hash of the firmware. This could be from trusted data sources (e.g., vendor site) or through a third-party verification service.
- [M0946 - Boot Integrity](../../../Defenses/Mitigations/M0946%20-%20Boot%20Integrity.md) — Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification. Use Trusted Platform Module technology.(Citation: N/A) Move system's root of trust to hardware to prevent tampering with the SPI flash memory.(Citation: ESET Research Whitepapers September 2018) Technologies such as Intel Boot Guard can assist with this.(Citation: Intel) [ESET Research Whitepapers September 2018](https://www.welivesecurity.com/wp-content/uploads/2018/09/ESET-LoJax.pdf) · [Intel](https://www.intel.com/content/dam/www/public/us/en/documents/white-papers/security-technologies-4th-gen-core-retail-paper.pdf) · [N/A](https://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf)
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Devices should verify that firmware has been properly signed by the vendor before allowing installation.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0808 - Encrypt Network Traffic](../../../Defenses/Mitigations/M0808%20-%20Encrypt%20Network%20Traffic.md) — The encryption of firmware should be considered to prevent adversaries from identifying possible vulnerabilities within the firmware.
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — The encryption of firmware should be considered to prevent adversaries from identifying possible vulnerabilities within the firmware.
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter for protocols and payloads associated with firmware activation or updating activity.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — Devices that allow remote management of firmware should require authentication before allowing any changes. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Detection strategies

- [DET0904 - Detection of Firmware Modification](../../../Defenses/Detection%20Strategies/DET0904%20-%20Detection%20of%20Firmware%20Modification.md)

## Sources

- [Basnight, Zachry, et al.](http://www.sciencedirect.com/science/article/pii/S1874548213000231)
