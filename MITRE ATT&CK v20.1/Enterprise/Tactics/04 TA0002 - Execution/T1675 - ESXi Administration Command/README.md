# T1675 - ESXi Administration Command

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may abuse ESXi administration services to execute commands on guest machines hosted within an ESXi virtual environment. Persistent background services on ESXi-hosted VMs, such as the VMware Tools Daemon Service, allow for remote management from the ESXi server. The tools daemon service runs as `vmtoolsd.exe` on Windows guest operating systems, `vmware-tools-daemon` on macOS, and `vmtoolsd ` on Linux.(Citation: Broadcom VMware Tools Services) 

Adversaries may leverage a variety of tools to execute commands on ESXi-hosted VMs – for example, by using the vSphere Web Services SDK to programmatically execute commands and scripts via APIs such as `StartProgramInGuest`, `ListProcessesInGuest`,  `ListFileInGuest`, and `InitiateFileTransferFromGuest`.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023)(Citation: Broadcom Running Guest OS Operations) This may enable follow-on behaviors on the guest VMs, such as [File and Directory Discovery](https://attack.mitre.org/techniques/T1083), [Data from Local System](https://attack.mitre.org/techniques/T1005), or [OS Credential Dumping](https://attack.mitre.org/techniques/T1003).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1675)

**Tactics**  [Execution](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md)

## Detection strategies

- [DET0232 - Detection Strategy for ESXi Administration Command](../../../Defenses/Detection%20Strategies/DET0232%20-%20Detection%20Strategy%20for%20ESXi%20Administration%20Command.md)

## Procedure examples

- [S9051 - The Gentlemen Ransomware](../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has utilized ESXi administration commands to include `vmkfstools` to modify the compromised system.(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/)
- [G1048 - UNC3886](../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) used `vmtoolsd.exe` to run commands on guest virtual machines from a compromised ESXi host.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022)(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023)(Citation: Google Cloud Mandiant UNC3886 2024)(Citation: Mandiant Fortinet Zero Day) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations) · [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/) · [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence) · [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [S1217 - VIRTUALPITA](../../../Threat%20Intelligence/Software/Malware/S1217%20-%20VIRTUALPITA.md) — [VIRTUALPITA](https://attack.mitre.org/software/S1217) can execute commands on guest virtual machines from compromised ESXi hypervisors.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Mitigations

- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — If not required, restrict the permissions of users to perform Guest Operations on ESXi-hosted VMs.(Citation: Broadcom Virtual Machine Guest Operations Privileges) [Broadcom Virtual Machine Guest Operations Privileges](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/vsphere-security-7-0/defined-privileges/virtual-machine-guest-operations-privileges.html)

## Sources

- [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)
- [Broadcom Running Guest OS Operations](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere-sdks-tools/8-0/web-services-sdk-programming-guide/virtual-machine-guest-operations/running-guest-os-operations.html)
- [Broadcom VMware Tools Services](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/tools/12-4-0/vmware-tools-administration-12-4-0/introduction-to-vmware-tools/vmware-tools-service.html)
