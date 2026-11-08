# T1673 - Virtual Machine Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

An adversary may attempt to enumerate running virtual machines (VMs) after gaining access to a host or hypervisor. For example, adversaries may enumerate a list of VMs on an ESXi hypervisor using a [Hypervisor CLI](https://attack.mitre.org/techniques/T1059/012) such as `esxcli` or `vim-cmd` (e.g. `esxcli vm process list or vim-cmd vmsvc/getallvms`).(Citation: Crowdstrike Hypervisor Jackpotting Pt 2 2021)(Citation: TrendMicro Play) Adversaries may also directly leverage a graphical user interface, such as VMware vCenter, in order to view virtual machines on a host. 

Adversaries may use the information from [Virtual Machine Discovery](https://attack.mitre.org/techniques/T1673) during discovery to shape follow-on behaviors. Subsequently discovered VMs may be leveraged for follow-on activities such as [Service Stop](https://attack.mitre.org/techniques/T1489) or [Data Encrypted for Impact](https://attack.mitre.org/techniques/T1486).(Citation: Crowdstrike Hypervisor Jackpotting Pt 2 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1673)

**Tactics**  [Discovery](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S1096 - Cheerscrypt](../../../Threat%20Intelligence/Software/Malware/S1096%20-%20Cheerscrypt.md) — Cheerscrypt has leveraged `esxcli vm process list` in order to gather a list of running virtual machines to terminate them.(Citation: Trend Micro Cheerscrypt May 2022) [Trend Micro Cheerscrypt May 2022](https://www.trendmicro.com/en_se/research/22/e/new-linux-based-ransomware-cheerscrypt-targets-exsi-devices.html)
- [S9060 - MiniBus](../../../Threat%20Intelligence/Software/Malware/S9060%20-%20MiniBus.md) — [MiniBus](https://attack.mitre.org/software/S9060) has the ability to identify processes associated with virtual machine utilities.(Citation: Mandiant_UNC1549_Feb2024) [Mandiant_UNC1549_Feb2024](https://cloud.google.com/blog/topics/threat-intelligence/suspected-iranian-unc1549-targets-israel-middle-east)
- [S9019 - PureCrypter](../../../Threat%20Intelligence/Software/Malware/S9019%20-%20PureCrypter.md) — [PureCrypter](https://attack.mitre.org/software/S9019) can identify virtual machines by querying the WMI object Win32_ComputerSystem for manufacturer and model and check it against the regular expression Microsoft|VMWare|Virtual.(Citation: Zscaler PureCrypter JUN 2022) [Zscaler PureCrypter JUN 2022](https://www.zscaler.com/blogs/security-research/technical-analysis-purecrypter)
- [S1242 - Qilin](../../../Threat%20Intelligence/Software/Malware/S1242%20-%20Qilin.md) — [Qilin](https://attack.mitre.org/software/S1242) can detect virtual machine environments including ESXi hosts, datacenters, and clusters within vCenter environments.(Citation: Halcyon Qilin.B OCT 2024)(Citation: Cisco Talos Qilin Ransomware OCT 2025) [Halcyon Qilin.B OCT 2024](https://www.halcyon.ai/blog/new-qilin-b-ransomware-variant-boasts-enhanced-encryption-and-defense-evasion) · [Cisco Talos Qilin Ransomware OCT 2025](https://blog.talosintelligence.com/uncovering-qilin-attack-methods-exposed-through-multiple-cases/)
- [G1048 - UNC3886](../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has used scripts to enumerate ESXi hypervisors and their guest VMs.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023) [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)
- [S1217 - VIRTUALPITA](../../../Threat%20Intelligence/Software/Malware/S1217%20-%20VIRTUALPITA.md) — [VIRTUALPITA](https://attack.mitre.org/software/S1217) can target specific guest virtual machines for script execution.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Detection strategies

- [DET0199 - Detection Strategy for Virtual Machine Discovery](../../../Defenses/Detection%20Strategies/DET0199%20-%20Detection%20Strategy%20for%20Virtual%20Machine%20Discovery.md)

## Sources

- [TrendMicro Play](https://www.trendmicro.com/en_us/research/24/g/new-play-ransomware-linux-variant-targets-esxi-shows-ties-with-p.html)
- [Crowdstrike Hypervisor Jackpotting Pt 2 2021](https://www.crowdstrike.com/en-us/blog/hypervisor-jackpotting-ecrime-actors-increase-targeting-of-esxi-servers/)
