# T0871 - Execution through API

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may attempt to leverage Application Program Interfaces (APIs) used for communication between control software and the hardware. Specific functionality is often coded into APIs which can be called by software to engage specific functions on a device or other software.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0871)

**Tactics**  [Execution](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) leveraged existing PLC management protocols through the manufacturer’s engineering tools. These include EtherNet/IP CIP, S7Comm, and UMAS.(Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) leverages a reconstructed TriStation protocol within its framework to trigger APIs related to program download, program allocation, and program changes. (Citation: Jos Wetzels January 2018) [Jos Wetzels January 2018](https://www.midnightbluelabs.com/blog/2018/1/16/analyzing-the-triton-industrial-malware)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Access Management technologies can be used to enforce authorization policies and decisions, especially when existing field devices do not provide capabilities to support user identification and authentication. (Citation: McCarthy, J et al. July 2018) These technologies typically utilize an in-line network device or gateway system to prevent access to unauthenticated users, while also integrating with an authentication service to first verify user credentials. [McCarthy, J et al. July 2018](https://doi.org/10.6028/NIST.SP.1800-2)
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — All APIs used to perform execution, especially those hosted on embedded controllers (e.g., PLCs), should provide adequate authorization enforcement of user access. Minimize user's access to only required API calls. (Citation: MITRE June 2020) [MITRE June 2020](https://cwe.mitre.org/data/definitions/227.html)
- [M0938 - Execution Prevention](../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Minimize the exposure of API calls that allow the execution of code.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All APIs on remote systems or local processes should require the authentication of users before executing any code or system changes.

## Detection strategies

- [DET0742 - Detection of Execution through API](../../../Defenses/Detection%20Strategies/DET0742%20-%20Detection%20of%20Execution%20through%20API.md)
