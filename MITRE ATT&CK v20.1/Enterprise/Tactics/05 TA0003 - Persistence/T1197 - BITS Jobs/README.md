# T1197 - BITS Jobs

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may abuse BITS jobs to persistently execute code and perform various background tasks. Windows Background Intelligent Transfer Service (BITS) is a low-bandwidth, asynchronous file transfer mechanism exposed through [Component Object Model](https://attack.mitre.org/techniques/T1559/001) (COM).(Citation: Microsoft COM)(Citation: Microsoft BITS) BITS is commonly used by updaters, messengers, and other applications preferred to operate in the background (using available idle bandwidth) without interrupting other networked applications. File transfer tasks are implemented as BITS jobs, which contain a queue of one or more file operations.

The interface to create and manage BITS jobs is accessible through [PowerShell](https://attack.mitre.org/techniques/T1059/001) and the [BITSAdmin](https://attack.mitre.org/software/S0190) tool.(Citation: Microsoft BITS)(Citation: Microsoft BITSAdmin)

Adversaries may abuse BITS to download (e.g. [Ingress Tool Transfer](https://attack.mitre.org/techniques/T1105)), execute, and even clean up after running malicious code (e.g. [Indicator Removal](https://attack.mitre.org/techniques/T1070)). BITS tasks are self-contained in the BITS job database, without new files or registry modifications, and often permitted by host firewalls.(Citation: CTU BITS Malware June 2016)(Citation: Mondok Windows PiggyBack BITS May 2007)(Citation: Symantec BITS May 2007) BITS enabled execution may also enable persistence by creating long-standing jobs (the default maximum lifetime is 90 days and extendable) or invoking an arbitrary program when a job completes or errors (including after system reboots).(Citation: PaloAlto UBoatRAT Nov 2017)(Citation: CTU BITS Malware June 2016)

BITS upload functionalities can also be used to perform [Exfiltration Over Alternative Protocol](https://attack.mitre.org/techniques/T1048).(Citation: CTU BITS Malware June 2016)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1197)

**Tactics**  [Execution](../../04%20TA0002%20-%20Execution/README.md), [Persistence](../README.md), [Stealth](../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Detection strategies

- [DET0098 - Detect abuse of Windows BITS Jobs for download, execution and persistence](../../../Defenses/Detection%20Strategies/DET0098%20-%20Detect%20abuse%20of%20Windows%20BITS%20Jobs%20for%20download%2C%20execution%20and%20persistence.md)

## Procedure examples

- [G0087 - APT39](../../../Threat%20Intelligence/Groups/G0087%20-%20APT39.md) — [APT39](https://attack.mitre.org/groups/G0087) has used the BITS protocol to exfiltrate stolen data from a compromised host.(Citation: FBI FLASH APT39 September 2020) [FBI FLASH APT39 September 2020](https://www.iranwatch.org/sites/default/files/public-intelligence-alert.pdf)
- [G0096 - APT41](../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) used [BITSAdmin](https://attack.mitre.org/software/S0190) to download and install payloads.(Citation: FireEye APT41 March 2020)(Citation: Crowdstrike GTR2020 Mar 2020) [FireEye APT41 March 2020](https://www.fireeye.com/blog/threat-research/2020/03/apt41-initiates-global-intrusion-campaign-using-multiple-exploits.html) · [Crowdstrike GTR2020 Mar 2020](https://go.crowdstrike.com/rs/281-OBQ-266/images/Report2020CrowdStrikeGlobalThreatReport.pdf)
- [S0534 - Bazar](../../../Threat%20Intelligence/Software/Malware/S0534%20-%20Bazar.md) — [Bazar](https://attack.mitre.org/software/S0534) has been downloaded via Windows BITS functionality.(Citation: NCC Group Team9 June 2020) [NCC Group Team9 June 2020](https://research.nccgroup.com/2020/06/02/in-depth-analysis-of-the-new-team9-malware-family/)
- [S0190 - BITSAdmin](../../../Threat%20Intelligence/Software/Tools/S0190%20-%20BITSAdmin.md) — [BITSAdmin](https://attack.mitre.org/software/S0190) can be used to create [BITS Jobs](https://attack.mitre.org/techniques/T1197) to launch a malicious process.(Citation: TrendMicro Tropic Trooper Mar 2018) [TrendMicro Tropic Trooper Mar 2018](https://blog.trendmicro.com/trendlabs-security-intelligence/tropic-trooper-new-strategy/)
- [S0154 - Cobalt Strike](../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can download a hosted "beacon" payload using [BITSAdmin](https://attack.mitre.org/software/S0190).(Citation: CobaltStrike Scripted Web Delivery)(Citation: Talos Cobalt Strike September 2020)(Citation: Cobalt Strike Manual 4.3 November 2020) [Talos Cobalt Strike September 2020](https://web.archive.org/web/20210219195905/https://talos-intelligence-site.s3.amazonaws.com/production/document_files/files/000/095/031/original/Talos_Cobalt_Strike.pdf) · [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf) · [CobaltStrike Scripted Web Delivery](https://www.cobaltstrike.com/help-scripted-web-delivery)
- [S0554 - Egregor](../../../Threat%20Intelligence/Software/Malware/S0554%20-%20Egregor.md) — [Egregor](https://attack.mitre.org/software/S0554) has used BITSadmin to download and execute malicious DLLs.(Citation: Intrinsec Egregor Nov 2020) [Intrinsec Egregor Nov 2020](https://www.intrinsec.com/egregor-prolock/?cn-reloaded=1)
- [S0201 - JPIN](../../../Threat%20Intelligence/Software/Malware/S0201%20-%20JPIN.md) — A [JPIN](https://attack.mitre.org/software/S0201) variant downloads the backdoor payload via the BITS service.(Citation: Microsoft PLATINUM April 2016) [Microsoft PLATINUM April 2016](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf)
- [G0065 - Leviathan](../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has used [BITSAdmin](https://attack.mitre.org/software/S0190) to download additional tools.(Citation: FireEye Periscope March 2018) [FireEye Periscope March 2018](https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html)
- [S0652 - MarkiRAT](../../../Threat%20Intelligence/Software/Malware/S0652%20-%20MarkiRAT.md) — [MarkiRAT](https://attack.mitre.org/software/S0652) can use BITS Utility to connect with the C2 server.(Citation: Kaspersky Ferocious Kitten Jun 2021) [Kaspersky Ferocious Kitten Jun 2021](https://securelist.com/ferocious-kitten-6-years-of-covert-surveillance-in-iran/102806/)
- [G0040 - Patchwork](../../../Threat%20Intelligence/Groups/G0040%20-%20Patchwork.md) — [Patchwork](https://attack.mitre.org/groups/G0040) has used BITS jobs to download malicious payloads.(Citation: Unit 42 BackConfig May 2020) [Unit 42 BackConfig May 2020](https://unit42.paloaltonetworks.com/updated-backconfig-malware-targeting-government-and-military-organizations/)
- [S0654 - ProLock](../../../Threat%20Intelligence/Software/Malware/S0654%20-%20ProLock.md) — [ProLock](https://attack.mitre.org/software/S0654) can use BITS jobs to download its malicious payload.(Citation: Group IB Ransomware September 2020) [Group IB Ransomware September 2020](https://web.archive.org/web/20220119114433/https://groupib.pathfactory.com/ransomware-reports/prolock_wp)
- [S0333 - UBoatRAT](../../../Threat%20Intelligence/Software/Malware/S0333%20-%20UBoatRAT.md) — [UBoatRAT](https://attack.mitre.org/software/S0333) takes advantage of the /SetNotifyCmdLine option in [BITSAdmin](https://attack.mitre.org/software/S0190) to ensure it stays running on a system to maintain persistence.(Citation: PaloAlto UBoatRAT Nov 2017) [PaloAlto UBoatRAT Nov 2017](https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/)
- [G0102 - Wizard Spider](../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used batch scripts that utilizes WMIC to execute a [BITSAdmin](https://attack.mitre.org/software/S0190) transfer of a ransomware payload to each compromised machine.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Mitigations

- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Modify network and/or host firewall rules, as well as other network controls, to only allow legitimate BITS traffic.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Consider reducing the default BITS job lifetime in Group Policy or by editing the <code>JobInactivityTimeout</code> and <code>MaxDownloadTime</code> Registry values in <code> HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\BITS</code>.(Citation: Microsoft BITS) [Microsoft BITS](https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Consider limiting access to the BITS interface to specific users or groups.(Citation: Symantec BITS May 2007) [Symantec BITS May 2007](https://www.symantec.com/connect/blogs/malware-update-windows-update)

## Sources

- [CTU BITS Malware June 2016](https://www.secureworks.com/blog/malware-lingers-with-bits)
- [Symantec BITS May 2007](https://www.symantec.com/connect/blogs/malware-update-windows-update)
- [PaloAlto UBoatRAT Nov 2017](https://researchcenter.paloaltonetworks.com/2017/11/unit42-uboatrat-navigates-east-asia/)
- [Microsoft BITS](https://msdn.microsoft.com/library/windows/desktop/bb968799.aspx)
- [Microsoft BITSAdmin](https://msdn.microsoft.com/library/aa362813.aspx)
- [Microsoft COM](https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx)
- [Mondok Windows PiggyBack BITS May 2007](https://arstechnica.com/information-technology/2007/05/malware-piggybacks-on-windows-background-intelligent-transfer-service/)
