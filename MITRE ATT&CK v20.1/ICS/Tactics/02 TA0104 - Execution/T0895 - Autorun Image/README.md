# T0895 - Autorun Image

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may leverage AutoRun functionality or scripts to execute malicious code. Devices configured to enable AutoRun functionality or legacy operating systems may be susceptible to abuse of these features to run malicious code stored on various forms of removeable media (i.e., USB, Disk Images [.ISO]). Commonly, AutoRun or AutoPlay are disabled in many operating systems configurations to mitigate against this technique. If a device is configured to enable AutoRun or AutoPlay, adversaries may execute code on the device by mounting the removable media to the device, either through physical or virtual means. This may be especially relevant for virtual machine environments where disk images may be dynamically mapped to a guest system on a hypervisor.  

An example could include an adversary gaining access to a hypervisor through the management interface to modify a virtual machine’s hardware configuration. They could then deploy an iso image with a malicious AutoRun script to cause the virtual machine to automatically execute the code contained on the disk image. This would enable the execution of malicious code within a virtual machine without needing any prior remote access to that system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0895)

**Tactics**  [Execution](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0928 - Operating System Configuration](../../../Defenses/Mitigations/M0928%20-%20Operating%20System%20Configuration.md) — Configure operating systems to disable the autorun of any specific file types or drives.

## Detection strategies

- [DET0748 - Detection of Autorun Image](../../../Defenses/Detection%20Strategies/DET0748%20-%20Detection%20of%20Autorun%20Image.md)

## Procedure examples

- [C0034 - 2022 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md) — During the [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034), [Sandworm Team](https://attack.mitre.org/groups/G0034) used existing hypervisor access to map an ISO image named `a.iso` to a virtual machine running a SCADA server. The SCADA server’s operating system was configured to autorun CD-ROM images, and as a result, a malicious VBS script on the ISO image was automatically executed.(Citation: Mandiant-Sandworm-Ukraine-2022) [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)
