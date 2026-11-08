# T1693.001 - System Firmware

[ICS](../../../../README.md) / [Impair Process Control](../../README.md) / [T1693 - Modify Firmware](../README.md)

System firmware on modern assets is often designed with an update feature. Older device firmware may be factory installed and require special reprograming equipment. When available, the firmware update feature enables vendors to remotely patch bugs and perform upgrades. Device firmware updates are often delegated to the user and may be done using a software update package. It may also be possible to perform this task over the network.

An adversary may exploit the firmware update feature on accessible devices to upload malicious or out-of-date firmware. Malicious modification of device firmware may provide an adversary with root access to a device, given firmware is one of the lowest programming abstraction layers.(Citation: Basnight, Zachry, et al.)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1693/001)

**Tactics**  [Persistence](../../../03%20TA0110%20-%20Persistence/README.md), [Inhibit Response Function](../../../10%20TA0107%20-%20Inhibit%20Response%20Function/README.md), [Impair Process Control](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) overwrote the serial-to-ethernet gateways with custom firmware to make systems either disabled, shutdown, and/or unrecoverable. (Citation: Ukraine15 - EISAC - 201603) [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries corrupted the firmware in the Hitachi RTUs resulting in a fault that triggered a reboot loop.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0041 - FrostyGoop Incident](../../../../Threat%20Intelligence/Campaigns/C0041%20-%20FrostyGoop%20Incident.md) — During [FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041), the adversary initiated a firmware downgrade on impacted devices.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S1009 - Triton](../../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) is able to read, write and execute code in memory on the safety controller at an arbitrary address within the devices firmware region. This allows the malware to make changes to the running firmware in memory and modify how the device operates. (Citation: DHS CISA February 2019) [DHS CISA February 2019](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%20-%20Safety%20System%20Targeted%20Malware%20%28Update%20B%29.pdf)

## Mitigations

- [M0801 - Access Management](../../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — All devices or systems changes, including all administrative functions, should require authentication. Consider using access management technologies to enforce authorization on all management interface access attempts, especially when the device does not inherently provide strong authentication and authorization functions.
- [M0947 - Audit](../../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Perform integrity checks of firmware before uploading it on a device. Utilize cryptographic hashes to verify the firmware has not been tampered with by comparing it to a trusted hash of the firmware. This could be from trusted data sources (e.g., vendor site) or through a third-party verification service.
- [M0946 - Boot Integrity](../../../../Defenses/Mitigations/M0946%20-%20Boot%20Integrity.md) — Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification. Use Trusted Platform Module technology.(Citation: N/A) Move system's root of trust to hardware to prevent tampering with the SPI flash memory.(Citation: ESET Research Whitepapers September 2018) Technologies such as Intel Boot Guard can assist with this.(Citation: Intel) [ESET Research Whitepapers September 2018](https://www.welivesecurity.com/wp-content/uploads/2018/09/ESET-LoJax.pdf) · [Intel](https://www.intel.com/content/dam/www/public/us/en/documents/white-papers/security-technologies-4th-gen-core-retail-paper.pdf) · [N/A](https://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf)
- [M0945 - Code Signing](../../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Devices should verify that firmware has been properly signed by the vendor before allowing installation.
- [M0802 - Communication Authenticity](../../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for device management should authenticate all network messages to prevent unauthorized system changes.
- [M0808 - Encrypt Network Traffic](../../../../Defenses/Mitigations/M0808%20-%20Encrypt%20Network%20Traffic.md) — The encryption of firmware should be considered to prevent adversaries from identifying possible vulnerabilities within the firmware.
- [M0941 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — The encryption of firmware should be considered to prevent adversaries from identifying possible vulnerabilities within the firmware.
- [M0937 - Filter Network Traffic](../../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Filter for protocols and payloads associated with firmware activation or updating activity.
- [M0804 - Human User Authentication](../../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — Devices that allow remote management of firmware should require authentication before allowing any changes. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0813 - Software Process and Device Authentication](../../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Authenticate connections from software and devices to prevent unauthorized systems from accessing protected management functions.
- [M0951 - Update Software](../../../../Defenses/Mitigations/M0951%20-%20Update%20Software.md) — Patch the BIOS and EFI as necessary.

## Detection strategies

- [DET0731 - Detection of System Firmware](../../../../Defenses/Detection%20Strategies/DET0731%20-%20Detection%20of%20System%20Firmware.md)

## Sources

- [Basnight, Zachry, et al.](http://www.sciencedirect.com/science/article/pii/S1874548213000231)
