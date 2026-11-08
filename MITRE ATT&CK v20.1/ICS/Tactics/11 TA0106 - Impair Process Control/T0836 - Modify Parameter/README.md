# T0836 - Modify Parameter

[ICS](../../../README.md) / [Impair Process Control](../README.md)

Adversaries may modify parameters used to instruct industrial control system devices. These devices operate via programs that dictate how and when to perform actions based on such parameters. Such parameters can determine the extent to which an action is performed and may specify additional options. For example, a program on a control system device dictating motor processes may take a parameter defining the total number of seconds to run that motor.      

An adversary can potentially modify these parameters to produce an outcome outside of what was intended by the operators. By modifying system and process critical parameters, the adversary may cause [Impact](https://attack.mitre.org/tactics/TA0105) to equipment and/or control processes. Modified parameters may be turned into dangerous, out-of-bounds, or unexpected values from typical operations. For example, specifying that a process run for more or less time than it should, or dictating an unusually high, low, or invalid value as a parameter.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0836)

**Tactics**  [Impair Process Control](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Procedure examples

- [C0066 - 2026 U.S. Water Utilities Attacks](../../../Threat%20Intelligence/Campaigns/C0066%20-%202026%20U.S.%20Water%20Utilities%20Attacks.md) — During the [2026 U.S. Water Utilities Attacks](https://attack.mitre.org/campaigns/C0066), the adversary changed the IP addresses of internet-facing MicroLogix controllers, altering their network configuration settings outside normal operations.(Citation: Tenable Minnesota Water Utilities)(Citation: Forescout Water Systems Attack)(Citation: Dragos Water Under Attack)(Citation: FBI Water and Wastewater) [FBI Water and Wastewater](https://www.fbi.gov/investigate/cyber/alerts/2026/malicious-cyber-actors-targeting-water-and-wastewater-sector-internet--facing-programmable-logic-controllers-causing-operational-disruptions) · [Dragos Water Under Attack](https://www.dragos.com/blog/water-utility-attacks-decade-of-gaps) · [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know) · [Forescout Water Systems Attack](https://www.forescout.com/blog/ot-security-analysis-exposed-devices-attacked-in-us-water-systems/)
- [S1165 - FrostyGoop](../../../Threat%20Intelligence/Software/Malware/S1165%20-%20FrostyGoop.md) — [FrostyGoop](https://attack.mitre.org/software/S1165) allows for the modification of system settings by reading and writing to registers via Modbus commands.(Citation: Dragos FROSTYGOOP 2024)(Citation: Nozomi BUSTLEBERM 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf) · [Nozomi BUSTLEBERM 2024](https://www.nozominetworks.com/blog/protecting-against-frostygoop-bustleberm-malware)
- [C0041 - FrostyGoop Incident](../../../Threat%20Intelligence/Campaigns/C0041%20-%20FrostyGoop%20Incident.md) — In [FrostyGoop Incident](https://attack.mitre.org/campaigns/C0041), the adversary caused the victim controllers to report incorrect measurements by modifying parameters.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can use the HTTP CGI scripts on Omron PLCs to modify parameters on EtherCat connected servo drives.(Citation: Wylie-22) [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) modifies specified Information Object Addresses (IOAs) for specified Application Service Data Unit (ASDU) addresses to either the ON or OFF state.(Citation: Industroyer2 Mandiant April 2022)(Citation: Industroyer2 Forescout July 2022) [Industroyer2 Mandiant April 2022](https://www.mandiant.com/resources/blog/industroyer-v2-old-malware-new-tricks) · [Industroyer2 Forescout July 2022](https://www.forescout.com/resources/industroyer2-and-incontroller-report/)
- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary gained remote computer access to the control system and altered data so that whatever function should have occurred at affected pumping stations did not occur or occurred in a different way. The software program installed in the laptop was one developed for changing configurations in the PDS computers. This ultimately led to 800,000 liters of raw sewage being spilled out into the community.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — In states 3 and 4 [Stuxnet](https://attack.mitre.org/software/S0603) sends two network bursts (done through the DP_SEND primitive). The data in the frames are instructions for the frequency converter drives. For example one of the frames contains records that change the maximum frequency (the speed at which the motor will operate). The frequency converter drives consist of parameters, which can be remotely configured via Profibus. One can write new values to these parameters changing the behavior of the device. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Provide the ability to verify the integrity and authenticity of changes to parameter values.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All field controllers should restrict the modification of parameter values to only certain users (e.g., engineers, field technician), preferably through implementing a role-based access mechanism. They should also restrict online edits and enable write protection for parameters.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require that user authenticate for all remote or local management sessions. The authentication mechanisms should also support Account Use Policies, Password Policies, and User Account Management.
- [M0818 - Validate Program Inputs](../../../Defenses/Mitigations/M0818%20-%20Validate%20Program%20Inputs.md) — Devices and programs should validate the content of any remote parameter changes, including those from HMIs, control servers, or engineering workstations.(Citation: PLCTop20 Mar 2023) [PLCTop20 Mar 2023](https://plc-security.com/content/Top_20_Secure_PLC_Coding_Practices_V1.0.pdf)

## Detection strategies

- [DET0776 - Detection of Modify Parameter](../../../Defenses/Detection%20Strategies/DET0776%20-%20Detection%20of%20Modify%20Parameter.md)
