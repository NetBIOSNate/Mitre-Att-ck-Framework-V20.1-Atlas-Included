# T0894 - System Binary Proxy Execution

[ICS](../../../README.md) / [Evasion](../README.md)

Adversaries may bypass process and/or signature-based defenses by proxying execution of malicious content with signed, or otherwise trusted, binaries. Binaries used in this technique are often Microsoft-signed files, indicating that they have been either downloaded from Microsoft or are already native in the operating system. (Citation: LOLBAS Project) Binaries signed with trusted digital certificates can typically execute on Windows systems protected by digital signature validation. Several Microsoft signed binaries that are default on Windows installations can be used to proxy execution of other files or commands. Similarly, on Linux systems adversaries may abuse trusted binaries such as split to proxy execution of malicious commands. (Citation: split man page)(Citation: GTFO split)

Adversaries may abuse application binaries installed on a system for proxy execution of malicious code or domain-specific commands. These commands could be used to target local resources on the device or networked devices within the environment through defined APIs ([Execution through API](https://attack.mitre.org/techniques/T0871)) or application-specific programming languages (e.g., MicroSCADA SCIL). Application binaries may be signed by the developer or generally trusted by the operators, analysts, and monitoring tools accustomed to the environment. These applications may be developed and/or directly provided by the device vendor to enable configuration, management, and operation of their devices without many alternatives. 

Adversaries may seek to target these trusted application binaries to execute or send commands without the development of custom malware. For example, adversaries may target a SCADA server binary which has the existing ability to send commands to substation devices, such as through IEC 104 command messages. Proxy execution may still require the development of custom tools to hook into the application binary’s execution.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0894)

**Tactics**  [Evasion](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Mitigations

- [M0938 - Execution Prevention](../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Disallow the execution of applications/programs which are not required for normal system functions, including any specific command-line arguments which may allow the execution of proxy commands or application binaries.

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0793 - Detection of System Binary Proxy Execution](../../../Defenses/Detection%20Strategies/DET0793%20-%20Detection%20of%20System%20Binary%20Proxy%20Execution.md)

## Procedure examples

- [C0034 - 2022 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md) — During the [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034), [Sandworm Team](https://attack.mitre.org/groups/G0034) executed a MicroSCADA application binary `scilc.exe` to send a predefined list of SCADA instructions specified in a file defined by the adversary, `s1.txt`. The executed command `C:\sc\prog\exec\scilc.exe -do pack\scil\s1.txt` leverages the SCADA software to send unauthorized command messages to remote substations.(Citation: Mandiant-Sandworm-Ukraine-2022) [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)

## Sources

- [GTFO split](https://gtfobins.github.io/gtfobins/split/)
- [LOLBAS Project](https://github.com/LOLBAS-Project/LOLBAS#criteria)
- [split man page](https://man7.org/linux/man-pages/man1/split.1.html)
