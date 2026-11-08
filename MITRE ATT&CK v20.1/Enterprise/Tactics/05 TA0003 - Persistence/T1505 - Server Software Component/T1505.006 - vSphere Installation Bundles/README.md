# T1505.006 - vSphere Installation Bundles

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1505 - Server Software Component](../README.md)

Adversaries may abuse vSphere Installation Bundles (VIBs) to establish persistent access to ESXi hypervisors. VIBs are collections of files used for software distribution and virtual system management in VMware environments. Since ESXi uses an in-memory filesystem where changes made to most files are stored in RAM rather than in persistent storage, these modifications are lost after a reboot. However, VIBs can be used to create startup tasks, apply custom firewall rules, or deploy binaries that persist across reboots. Typically, administrators use VIBs for updates and system maintenance.

VIBs can be broken down into three components:(Citation: VMware VIBs)

* VIB payload: a `.vgz` archive containing the directories and files to be created and executed on boot when the VIBs are loaded.  
* Signature file: verifies the host acceptance level of a VIB, indicating what testing and validation has been done by VMware or its partners before publication of a VIB. By default, ESXi hosts require a minimum acceptance level of PartnerSupported for VIB installation, meaning the VIB is published by a trusted VMware partner. However, privileged users can change the default acceptance level using the `esxcli` command line interface. Additionally, VIBs are able to be installed regardless of acceptance level by using the <code> esxcli software vib install --force</code> command. 
* XML descriptor file: a configuration file containing associated VIB metadata, such as the name of the VIB and its dependencies.  

Adversaries may leverage malicious VIB packages to maintain persistent access to ESXi hypervisors, allowing system changes to be executed upon each bootup of ESXi – such as using  `esxcli` to enable firewall rules for backdoor traffic, creating listeners on hard coded ports, and executing backdoors.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) Adversaries may also masquerade their malicious VIB files as PartnerSupported by modifying the XML descriptor file.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1505/006)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md)

## Detection strategies

- [DET0535 - Detect Abuse of vSphere Installation Bundles (VIBs) for Persistent Access](../../../../Defenses/Detection%20Strategies/DET0535%20-%20Detect%20Abuse%20of%20vSphere%20Installation%20Bundles%20%28VIBs%29%20for%20Persistent%20Access.md)

## Procedure examples

- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has used vSphere Installation Bundles (VIBs) to install malware and establish persistence across ESXi hypervisors.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022)(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023)(Citation: Mandiant Fortinet Zero Day) [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/) · [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence) · [Mandiant Fortinet Zero Day](https://www.mandiant.com/resources/blog/fortinet-malware-ecosystem)
- [S1218 - VIRTUALPIE](../../../../Threat%20Intelligence/Software/Malware/S1218%20-%20VIRTUALPIE.md) — [VIRTUALPIE](https://attack.mitre.org/software/S1218) has been installed on VMware ESXi servers through malicious vSphere Installation Bundles (VIBs).(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically audit ESXi hosts to ensure that only approved VIBs are installed. The command `esxcli software vib list` lists installed VIBs, while the command `esxcli software vib signature verify` verifies the signatures of installed VIBs.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)
- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Enabling secure boot allows ESXi to validate software and drivers during initial system boot.(Citation: Google Cloud Threat Intelligence ESXi Hardening 2023) [Google Cloud Threat Intelligence ESXi Hardening 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-detection-containment-hardening)
- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Enabling the `execInstalledOnly` feature prevents unsigned binaries from being run on ESXi hosts.(Citation: Google Cloud Threat Intelligence ESXi Hardening 2023) [Google Cloud Threat Intelligence ESXi Hardening 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-detection-containment-hardening)

## Sources

- [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)
- [VMware VIBs](https://blogs.vmware.com/vsphere/2011/09/whats-in-a-vib.html)
