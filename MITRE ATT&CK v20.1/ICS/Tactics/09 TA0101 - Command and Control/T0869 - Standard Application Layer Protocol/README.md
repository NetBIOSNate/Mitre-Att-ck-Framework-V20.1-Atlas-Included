# T0869 - Standard Application Layer Protocol

[ICS](../../../README.md) / [Command and Control](../README.md)

Adversaries may establish command and control capabilities over commonly used application layer protocols such as HTTP(S), OPC, RDP, telnet, DNP3, and modbus. These protocols may be used to disguise adversary actions as benign network traffic. Standard protocols may be seen on their associated port or in some cases over a non-standard port.  Adversaries may use these protocols to reach out of the network for command and control, or in some cases to other infected devices within the network.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0869)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T0869.001 - DNS](T0869.001%20-%20DNS/README.md)
- [T0869.002 - Publish/Subscribe Protocols](T0869.002%20-%20Publish%20-%20Subscribe%20Protocols/README.md)

## Procedure examples

- [S0089 - BlackEnergy](../../../Threat%20Intelligence/Software/Malware/S0089%20-%20BlackEnergy.md) — [BlackEnergy](https://attack.mitre.org/software/S0089) uses HTTP POST request to contact external command and control servers. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [S1165 - FrostyGoop](../../../Threat%20Intelligence/Software/Malware/S1165%20-%20FrostyGoop.md) — [FrostyGoop](https://attack.mitre.org/software/S1165) utilizes the Modbus protocol for transmitting commands to victim devices.(Citation: Dragos FROSTYGOOP 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can remotely send commands to a malicious agent uploaded on Omron PLCs over HTTP or HTTPS.(Citation: CISA-AA22-103A) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) communicated with its command and control using HTTP requests. (Citation: Robert Falcone, Bryan Lee May 2016) [Robert Falcone, Bryan Lee May 2016](https://unit42.paloaltonetworks.com/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) sends HTTPS POST messages with randomly generated URLs to communicate with a remote server. (Citation: Tom Fakterman August 2019) (Citation: SecureWorks September 2019) [SecureWorks September 2019](https://www.secureworks.com/research/revil-sodinokibi-ransomware) · [Tom Fakterman August 2019](https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) uses a thread to monitor a data block DB890 of sequence A or B. This thread is constantly running and probing this block (every 5 minutes). On an infected PLC, if block DB890 is found and contains a special magic value (used by Stuxnet to identify his own block DB890), this blocks data can be read and written. This thread is likely used to optimize the way sequences A and B work, and modify their behavior when the Step7 editor is opened. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) can communicate with the implant utilizing the TriStation 'get main processor diagnostic data' command and looks for a specifically crafted packet body from which it extracts a command value and its arguments. (Citation: Jos Wetzels January 2018) [Jos Wetzels January 2018](https://www.midnightbluelabs.com/blog/2018/1/16/analyzing-the-triton-industrial-malware)

## Mitigations

- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Network allowlists can be implemented through either host-based files or system host files to specify what external connections (e.g., IP address, MAC address, port, protocol) can be made from a device. Allowlist techniques that operate at the application layer (e.g., DNP3, Modbus, HTTP) are addressed in the [Filter Network Traffic](https://attack.mitre.org/mitigations/M0937) mitigation.
- [M0931 - Network Intrusion Prevention](../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Ensure proper network segmentation between higher level corporate resources and the control process environment.

## Detection strategies

- [DET0799 - Detection of Standard Application Layer Protocol](../../../Defenses/Detection%20Strategies/DET0799%20-%20Detection%20of%20Standard%20Application%20Layer%20Protocol.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
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
