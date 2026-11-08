# T1006 - Direct Volume Access

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may directly access a volume to bypass file access controls and file system monitoring. Windows allows programs to have direct access to logical volumes. Programs with direct access may read and write files directly from the drive by analyzing file system data structures. This technique may bypass Windows file access controls as well as file system monitoring tools.(Citation: Hakobyan 2009)

Utilities, such as `NinjaCopy`, exist to perform these actions in PowerShell.(Citation: Github PowerSploit Ninjacopy) Adversaries may also use built-in or third-party utilities (such as `vssadmin`, `wbadmin`, and [esentutl](https://attack.mitre.org/software/S0404)) to create shadow copies or backups of data from system volumes.(Citation: LOLBAS Esentutl)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1006)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries copied volume shadow copies through executing `vssadmin` in order to dump the `NTDS.dit` file.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0051 - APT28 Nearest Neighbor Campaign](../../../Threat%20Intelligence/Campaigns/C0051%20-%20APT28%20Nearest%20Neighbor%20Campaign.md) — During [APT28 Nearest Neighbor Campaign](https://attack.mitre.org/campaigns/C0051), [APT28](https://attack.mitre.org/groups/G0007) accessed volume shadow copies through executing <code>vssadmin</code> in order to dump the NTDS.dit file.(Citation: Nearest Neighbor Volexity) [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
- [S0404 - esentutl](../../../Threat%20Intelligence/Software/Tools/S0404%20-%20esentutl.md) — [esentutl](https://attack.mitre.org/software/S0404) can use the Volume Shadow Copy service to copy locked files such as `ntds.dit`.(Citation: LOLBAS Esentutl)(Citation: Cary Esentutl) [Cary Esentutl](https://dfironthemountain.wordpress.com/2018/12/06/locked-file-access-using-esentutl-exe/) · [LOLBAS Esentutl](https://lolbas-project.github.io/lolbas/Binaries/Esentutl/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has created volume shadow copies of virtual domain controller disks to extract the `NTDS.dit` file.(Citation: MSTIC Octo Tempest Operations October 2023) [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has executed the Windows-native `vssadmin` command to create volume shadow copies.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0426 - Detection of Direct Volume Access for File System Evasion](../../../Defenses/Detection%20Strategies/DET0426%20-%20Detection%20of%20Direct%20Volume%20Access%20for%20File%20System%20Evasion.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of behaviors related to efforts by an adversary to create backups, such as command execution or preventing API calls to backup related services.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure only accounts required to configure and manage backups have the privileges to do so. Monitor these accounts for unauthorized backup activity.

## Sources

- [Github PowerSploit Ninjacopy](https://github.com/PowerShellMafia/PowerSploit/blob/master/Exfiltration/Invoke-NinjaCopy.ps1)
- [Hakobyan 2009](http://www.codeproject.com/Articles/32169/FDump-Dumping-File-Sectors-Directly-from-Disk-usin)
- [LOLBAS Esentutl](https://lolbas-project.github.io/lolbas/Binaries/Esentutl/)
