# T1218.014 - MMC

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse mmc.exe to proxy execution of malicious .msc files. Microsoft Management Console (MMC) is a binary that may be signed by Microsoft and is used in several ways in either its GUI or in a command prompt.(Citation: win_mmc)(Citation: what_is_mmc) MMC can be used to create, open, and save custom consoles that contain administrative tools created by Microsoft, called snap-ins. These snap-ins may be used to manage Windows systems locally or remotely. MMC can also be used to open Microsoft created .msc files to manage system configuration.(Citation: win_msc_files_overview)

For example, <code>mmc C:\Users\foo\admintools.msc /a</code> will open a custom, saved console msc file in author mode.(Citation: win_mmc) Another common example is <code>mmc gpedit.msc</code>, which will open the Group Policy Editor application window. 

Adversaries may use MMC commands to perform malicious tasks. For example, <code>mmc wbadmin.msc delete catalog -quiet</code> deletes the backup catalog on the system (i.e. [Inhibit System Recovery](https://attack.mitre.org/techniques/T1490)) without prompts to the user (Note: <code>wbadmin.msc</code> may only be present by default on Windows Server operating systems).(Citation: win_wbadmin_delete_catalog)(Citation: phobos_virustotal)

Adversaries may also abuse MMC to execute malicious .msc files. For example, adversaries may first create a malicious registry Class Identifier (CLSID) subkey, which uniquely identifies a [Component Object Model](https://attack.mitre.org/techniques/T1559/001) class object.(Citation: win_clsid_key) Then, adversaries may create custom consoles with the “Link to Web Address” snap-in that is linked to the malicious CLSID subkey.(Citation: mmc_vulns) Once the .msc file is saved, adversaries may invoke the malicious CLSID payload with the following command: <code>mmc.exe -Embedding C:\path\to\test.msc</code>.(Citation: abusing_com_reg)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/014)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1051 - Medusa Group](../../../../Threat%20Intelligence/Groups/G1051%20-%20Medusa%20Group.md) — [Medusa Group](https://attack.mitre.org/groups/G1051) has leveraged Microsoft Management Console (MMC) to facilitate lateral movement and to interact locally or remotely with victim devices using the command `mmc.exe compmgmt.msc /computer:{hostname/ip}`.(Citation: CISA Medusa Group Medusa Ransomware March 2025) [CISA Medusa Group Medusa Ransomware March 2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a)
- [C0047 - RedDelta Modified PlugX Infection Chain Operations](../../../../Threat%20Intelligence/Campaigns/C0047%20-%20RedDelta%20Modified%20PlugX%20Infection%20Chain%20Operations.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) used Microsoft Management Console Snap-In Control files, or MSC files, executed via MMC to run follow-on PowerShell commands during [RedDelta Modified PlugX Infection Chain Operations](https://attack.mitre.org/campaigns/C0047).(Citation: Recorded Future RedDelta 2025) [Recorded Future RedDelta 2025](https://go.recordedfuture.com/hubfs/reports/cta-cn-2025-0109.pdf)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — MMC may not be necessary within a given environment since it is primarily used by system administrators, not regular users or clients.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of MMC if it is not required for a given system or network to prevent potential misuse by adversaries.

## Detection strategies

- [DET0222 - Detecting MMC (.msc) Proxy Execution and Malicious COM Activation](../../../../Defenses/Detection%20Strategies/DET0222%20-%20Detecting%20MMC%20%28.msc%29%20Proxy%20Execution%20and%20Malicious%20COM%20Activation.md)

## Sources

- [abusing_com_reg](https://bohops.com/2018/08/18/abusing-the-com-registry-structure-part-2-loading-techniques-for-evasion-and-persistence/)
- [mmc_vulns](https://research.checkpoint.com/2019/microsoft-management-console-mmc-vulnerabilities/)
- [win_msc_files_overview](https://www.ghacks.net/2017/06/10/windows-msc-files-overview/)
- [win_mmc](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mmc)
- [win_wbadmin_delete_catalog](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/wbadmin-delete-catalog)
- [win_clsid_key](https://docs.microsoft.com/en-us/windows/win32/com/clsid-key-hklm)
- [what_is_mmc](https://docs.microsoft.com/en-us/troubleshoot/windows-server/system-management-components/what-is-microsoft-management-console)
- [phobos_virustotal](https://www.virustotal.com/gui/file/0b4c743246478a6a8c9fa3ff8e04f297507c2f0ea5d61a1284fe65387d172f81/detection)
