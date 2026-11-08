# T0862 - Supply Chain Compromise

[ICS](../../../README.md) / [Initial Access](../README.md)

Adversaries may perform supply chain compromise to gain control systems environment access by means of infected products, software, and workflows. Supply chain compromise is the manipulation of products, such as devices or software, or their delivery mechanisms before receipt by the end consumer. Adversary compromise of these products and mechanisms is done for the goal of data or system compromise, once infected products are introduced to the target environment. 

Supply chain compromise can occur at all stages of the supply chain, from manipulation of development tools and environments to manipulation of developed products and tools distribution mechanisms. This may involve the compromise and replacement of legitimate software and patches, such as on third party or vendor websites. Targeting of supply chain compromise can be done in attempts to infiltrate the environments of a specific audience. In control systems environments with assets in both the IT and OT networks, it is possible a supply chain compromise affecting the IT environment could enable further access to the OT environment.   

Counterfeit devices may be introduced to the global supply chain posing safety and cyber risks to asset owners and operators. These devices may not meet the safety, engineering and manufacturing requirements of regulatory bodies but may feature tagging indicating conformance with industry standards. Due to the lack of adherence to standards and overall lesser quality, the counterfeit products may pose a serious safety and operational risk. (Citation: Control Global May 2019) 

Yokogawa identified instances in which their customers received counterfeit differential pressure transmitters using the Yokogawa logo. The counterfeit transmitters were nearly indistinguishable with a semblance of functionality and interface that mimics the genuine product. (Citation: Control Global May 2019) 

F-Secure Labs analyzed the approach the adversary used to compromise victim systems with Havex. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) The adversary planted trojanized software installers available on legitimate ICS/SCADA vendor websites. After being downloaded, this software infected the host computer with a Remote Access Trojan (RAT).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0862)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses. Perform periodic integrity checks of the device to validate the correctness of the firmware, software, programs, and configurations. Integrity checks, which typically include cryptographic hashes or digital signatures, should be compared to those obtained at known valid states, especially after events like device reboots, program downloads, or program restarts.
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — When available utilize hardware and software root-of-trust to verify the authenticity of a system. This may be achieved through cryptographic means, such as digital signatures or hashes, of critical software and firmware throughout the supply chain.
- [M0817 - Supply Chain Management](../../../Defenses/Mitigations/M0817%20-%20Supply%20Chain%20Management.md) — A supply chain management program should include methods the assess the trustworthiness and technical maturity of a supplier, along with technical methods (e.g., code-signing, bill of materials) needed to validate the integrity of newly obtained devices and components. Develop procurement language that emphasizes the expectations for suppliers regarding the artifacts, audit records, and technical capabilities needed to validate the integrity of the devices supply chain. (Citation: Robert A. Martin January 2021) [Robert A. Martin January 2021](https://www.mitre.org/sites/default/files/publications/pr-20-01465-37-trusting-our-supply-chains-a-comprehensive-data-driven-approach.pdf)
- [M0951 - Update Software](../../../Defenses/Mitigations/M0951%20-%20Update%20Software.md) — A patch management process should be implemented to check unused dependencies, unmaintained and/or previously vulnerable dependencies, unnecessary features, components, files, and documentation.
- [M0916 - Vulnerability Scanning](../../../Defenses/Mitigations/M0916%20-%20Vulnerability%20Scanning.md) — Implement continuous monitoring of vulnerability sources. Also, use automatic and manual code review tools. (Citation: OWASP) [OWASP](https://owasp.org/www-project-top-ten/)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) RAT is distributed through trojanized installers planted on compromised vendor sites. (Citation: Daavid Hentunen, Antti Tikkanen June 2014) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html)
- [G0035 - Dragonfly](../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) trojanized legitimate ICS equipment providers software packages available for download on their websites.(Citation: Symantec Security Response July 2014) [Symantec Security Response July 2014](https://docs.broadcom.com/doc/dragonfly_threat_against_western_energy_suppliers#:~:text=The%20attackers%2C%20known%20to%20Symantec,supply%20in%20the%20affected%20countries.)
- [G0088 - TEMP.Veles](../../../Threat%20Intelligence/Groups/G0088%20-%20TEMP.Veles.md) — [TEMP.Veles](https://attack.mitre.org/groups/G0088) targeted several ICS vendors and manufacturers. (Citation: Dragos Threat Intelligence August 2019) [Dragos Threat Intelligence August 2019](https://dragos.com/wp-content/uploads/Dragos-Oil-and-Gas-Threat-Perspective-2019.pdf)

## Detection strategies

- [DET0730 - Detection of Supply Chain Compromise](../../../Defenses/Detection%20Strategies/DET0730%20-%20Detection%20of%20Supply%20Chain%20Compromise.md)

## Sources

- [Control Global May 2019](https://www.controlglobal.com/industrynews/2019/yokogawa-announcement-warns-of-counterfeit-transmitters/)
- [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html)
