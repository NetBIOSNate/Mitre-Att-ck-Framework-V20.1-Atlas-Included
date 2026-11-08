# T0864 - Transient Cyber Asset

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may target devices that are transient across ICS networks and external networks. Normally, transient assets are brought into an environment by authorized personnel and do not remain in that environment on a permanent basis. (Citation: North American Electric Reliability Corporation June 2021) Transient assets are commonly needed to support management functions and may be more common in systems where a remotely managed asset is not feasible, external connections for remote access do not exist, or 3rd party contractor/vendor access is required. 

Adversaries may take advantage of transient assets in different ways. For instance, adversaries may target a transient asset when it is connected to an external network and then leverage its trusted access in another environment to launch an attack. They may also take advantage of installed applications and libraries that are used by legitimate end-users to interact with control system devices. 

Transient assets, in some cases, may not be deployed with a secure configuration leading to weaknesses that could allow an adversary to propagate malicious executable code, e.g., the transient asset may be infected by malware and when connected to an ICS environment the malware propagates onto other systems.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0864)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0949 - Antivirus/Antimalware](../../../Defenses/Mitigations/M0949%20-%20Antivirus%20-%20Antimalware.md) — Install anti-virus software on all workstation and transient assets that may have external access, such as to web, email, or remote file shares.
- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Integrity checking of transient assets can include performing the validation of the booted operating system and programs using TPM-based technologies, such as Secure Boot and Trusted Boot. (Citation: Emerson Exchange) It can also include verifying filesystem changes, such as programs and configuration files stored on the system, executing processes, libraries, accounts, and open ports. (Citation: National Security Agency February 2016) [Emerson Exchange](https://emersonexchange365.com/products/control-safety-systems/f/plc-pac-systems-industrial-computing-forum/8383/increase-security-with-tpm-secure-boot-and-trusted-boot) · [National Security Agency February 2016](https://apps.nsa.gov/iaarchive/library/ia-guidance/security-configuration/industrial-control-systems/position-zero-integrity-checking-windows-based-ics-scada-systems.cfm)
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — Consider implementing full disk encryption, especially if engineering workstations are transient assets that are more likely to be lost, stolen, or tampered with. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment and control software movement between business and OT environments by way of one directional DMZs. Web access should be restricted from the OT environment. Engineering workstations, including transient cyber assets (TCAs) should have minimal connectivity to external networks, including Internet and email, further limit the extent to which these devices are dual-homed to multiple networks. (Citation: North America Transmission Forum December 2019) [North America Transmission Forum December 2019](https://www.natf.net/docs/natf/documents/resources/security/natf-transient-cyber-asset-guidance.pdf)
- [M0951 - Update Software](../../../Defenses/Mitigations/M0951%20-%20Update%20Software.md) — Update software on control network assets when possible. If feasible, use modern operating systems and software to reduce exposure to known vulnerabilities.

## Procedure examples

- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary utilized a computer, possibly stolen, with proprietary engineering software to communicate with a wastewater system.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Detection strategies

- [DET0744 - Detection of Transient Cyber Asset](../../../Defenses/Detection%20Strategies/DET0744%20-%20Detection%20of%20Transient%20Cyber%20Asset.md)

## Sources

- [North American Electric Reliability Corporation June 2021](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)
