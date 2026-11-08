# T0889 - Modify Program

[ICS](../../../README.md) / [Persistence](../README.md)

Adversaries may modify or add a program on a controller to affect how it interacts with the physical process, peripheral devices and other hosts on the network. Modification to controller programs can be accomplished using a Program Download in addition to other types of program modification such as online edit and program append. 

Program modification encompasses the addition and modification of instructions and logic contained in Program Organization Units (POU)  (Citation: IEC February 2013) and similar programming elements found on controllers. This can include, for example, adding new functions to a controller, modifying the logic in existing functions and making new calls from one function to another. 

Some programs may allow an adversary to interact directly with the native API of the controller to take advantage of obscure features or vulnerabilities.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0889)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Provide the ability to verify the integrity of control logic or programs loaded on a controller. While techniques like CRCs and checksums are commonly used, they are not cryptographically strong and can be vulnerable to collisions. Preferably cryptographic hash functions (e.g., SHA-2, SHA-3) should be used. (Citation: IEC February 2019) [IEC February 2019](https://webstore.iec.ch/publication/34421)
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict the modification of programs to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism.
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Utilize code signatures to verify the integrity and authenticity of programs installed on safety or control assets.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support Account Use Policies, Password Policies, and User Account Management.

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary altered the control logic (e.g., project files) of internet-exposed PLCs, producing ladder logic discrepancies, changing how the affected controller interacted with its process, after gaining access through default credentials.(Citation: Tenable Minnesota Water Utilities)(Citation: Forescout Water Systems Attack)(Citation: FBI Water and Wastewater) [FBI Water and Wastewater](https://www.fbi.gov/investigate/cyber/alerts/2026/malicious-cyber-actors-targeting-water-and-wastewater-sector-internet--facing-programmable-logic-controllers-causing-operational-disruptions) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know) · [Forescout Water Systems Attack](https://www.forescout.com/blog/ot-security-analysis-exposed-devices-attacked-in-us-water-systems/)
- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) used manufacturers’ commercial PLC programming software to modify their victim’s running PLC program logic. These include Rockwell Automation’s [Studio Logix 5000 Designer](https://attack.mitre.org/software/S9054), Schneider Electric’s [EcoStruxure Control Expert](https://attack.mitre.org/software/S9056), and Siemens’ [Totally Integrated Automation (TIA) Portal](https://attack.mitre.org/software/S9055).(Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1006 - PLC-Blaster](../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — [PLC-Blaster](https://attack.mitre.org/software/S1006) copies itself to various Program Organization Units (POU) on the target device. The POUs include the Data Block, Function, and Function Block. (Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) infects PLCs with different code depending on the characteristics of the target system. An infection sequence consists of code blocks and data blocks that will be downloaded to the PLC to alter its behavior. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Detection strategies

- [DET0783 - Detection of Modify Program](../../../Defenses/Detection%20Strategies/DET0783%20-%20Detection%20of%20Modify%20Program.md)

## Sources

- [IEC February 2013](https://webstore.iec.ch/publication/4552)
