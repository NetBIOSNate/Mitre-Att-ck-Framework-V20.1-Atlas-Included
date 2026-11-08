# T1059.012 - Hypervisor CLI

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse hypervisor command line interpreters (CLIs) to execute malicious commands. Hypervisor CLIs typically enable a wide variety of functionality for managing both the hypervisor itself and the guest virtual machines it hosts. 

For example, on ESXi systems, tools such as `esxcli` and `vim-cmd` allow administrators to configure firewall rules and log forwarding on the hypervisor, list virtual machines, start and stop virtual machines, and more.(Citation: Broadcom ESXCLI Reference)(Citation: Crowdstrike Hypervisor Jackpotting Pt 2 2021)(Citation: LOLESXi) Adversaries may be able to leverage these tools in order to support further actions, such as [File and Directory Discovery](https://attack.mitre.org/techniques/T1083) or [Data Encrypted for Impact](https://attack.mitre.org/techniques/T1486).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/012)

**Tactics**  [Execution](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md)

## Procedure examples

- [S1096 - Cheerscrypt](../../../../Threat%20Intelligence/Software/Malware/S1096%20-%20Cheerscrypt.md) — Cheerscrypt has leveraged `esxcli` in order to terminate running virtual machines.(Citation: Trend Micro Cheerscrypt May 2022) [Trend Micro Cheerscrypt May 2022](https://www.trendmicro.com/en_se/research/22/e/new-linux-based-ransomware-cheerscrypt-targets-exsi-devices.html)
- [S1073 - Royal](../../../../Threat%20Intelligence/Software/Malware/S1073%20-%20Royal.md) — Royal ransomware uses `esxcli` to gather a list of running VMs and terminate them.(Citation: Trend Micro Royal Linux ESXi February 2023) [Trend Micro Royal Linux ESXi February 2023](https://www.trendmicro.com/en_us/research/23/b/royal-ransomware-expands-attacks-by-targeting-linux-esxi-servers.html)
- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has utilized `esxcli` to execute commands on compromised ESXi systems and VMs.(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has used the esxcli command line utility to modify firewall rules, install malware, and for artifact removal.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022)(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023) [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/) · [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)
- [S1218 - VIRTUALPIE](../../../../Threat%20Intelligence/Software/Malware/S1218%20-%20VIRTUALPIE.md) — [VIRTUALPIE](https://attack.mitre.org/software/S1218) is capable of command line execution on compromised ESXi servers.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Detection strategies

- [DET0558 - Detection Strategy for ESXi Hypervisor CLI Abuse](../../../../Defenses/Detection%20Strategies/DET0558%20-%20Detection%20Strategy%20for%20ESXi%20Hypervisor%20CLI%20Abuse.md)

## Sources

- [Broadcom ESXCLI Reference](https://developer.broadcom.com/xapis/esxcli-command-reference/latest/)
- [LOLESXi](https://lolesxi-project.github.io/LOLESXi/)
- [Crowdstrike Hypervisor Jackpotting Pt 2 2021](https://www.crowdstrike.com/en-us/blog/hypervisor-jackpotting-ecrime-actors-increase-targeting-of-esxi-servers/)
