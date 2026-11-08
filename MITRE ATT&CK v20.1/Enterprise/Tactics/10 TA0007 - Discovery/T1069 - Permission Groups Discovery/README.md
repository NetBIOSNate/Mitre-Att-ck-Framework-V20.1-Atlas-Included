# T1069 - Permission Groups Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to discover group and permission settings. This information can help adversaries determine which user accounts and groups are available, the membership of users in particular groups, and which users and groups have elevated permissions.

Adversaries may attempt to discover group permission settings in many different ways. This data may provide the adversary with information about the compromised environment that can be used in follow-on activity and targeting.(Citation: CrowdStrike BloodHound April 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1069)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md), [IaaS](../../../Platforms/IaaS.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1069.003 - Cloud Groups](T1069.003%20-%20Cloud%20Groups/README.md)
- [T1069.002 - Domain Groups](T1069.002%20-%20Domain%20Groups/README.md)
- [T1069.001 - Local Groups](T1069.001%20-%20Local%20Groups/README.md)

## Procedure examples

- [G0022 - APT3](../../../Threat%20Intelligence/Groups/G0022%20-%20APT3.md) — [APT3](https://attack.mitre.org/groups/G0022) has a tool that can enumerate the permissions associated with Windows groups.(Citation: Symantec Buckeye) [Symantec Buckeye](https://web.archive.org/web/20160910124439/http://www.symantec.com/connect/blogs/buckeye-cyberespionage-group-shifts-gaze-us-hong-kong)
- [G0096 - APT41](../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) used <code>net group</code> commands to enumerate various Windows user groups and permissions.(Citation: Rostovcev APT41 2021) [Rostovcev APT41 2021](https://www.group-ib.com/blog/apt41-world-tour-2021/)
- [S0335 - Carbon](../../../Threat%20Intelligence/Software/Malware/S0335%20-%20Carbon.md) — [Carbon](https://attack.mitre.org/software/S0335) uses the <code>net group</code> command.(Citation: GovCERT Carbon May 2016) [GovCERT Carbon May 2016](https://web.archive.org/web/20170718174931/https://www.melani.admin.ch/dam/melani/de/dokumente/2016/technical%20report%20ruag.pdf.download.pdf/Report_Ruag-Espionage-Case.pdf)
- [G1016 - FIN13](../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has enumerated all users and roles from a victim's main treasury system.(Citation: Mandiant FIN13 Aug 2022) [Mandiant FIN13 Aug 2022](https://www.mandiant.com/resources/blog/fin13-cybercriminal-mexico)
- [S0483 - IcedID](../../../Threat%20Intelligence/Software/Malware/S0483%20-%20IcedID.md) — [IcedID](https://attack.mitre.org/software/S0483) has the ability to identify Workgroup membership.(Citation: IBM IcedID November 2017) [IBM IcedID November 2017](https://securityintelligence.com/new-banking-trojan-icedid-discovered-by-ibm-x-force-research/)
- [S0233 - MURKYTOP](../../../Threat%20Intelligence/Software/Malware/S0233%20-%20MURKYTOP.md) — [MURKYTOP](https://attack.mitre.org/software/S0233) has the capability to retrieve information about groups.(Citation: FireEye Periscope March 2018) [FireEye Periscope March 2018](https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has enumerated the vSphere Admins and ESX Admins groups in targeted environments.(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [S0445 - ShimRatReporter](../../../Threat%20Intelligence/Software/Tools/S0445%20-%20ShimRatReporter.md) — [ShimRatReporter](https://attack.mitre.org/software/S0445) gathered the local privileges for the infected host.(Citation: FOX-IT May 2016 Mofang) [FOX-IT May 2016 Mofang](https://foxitsecurity.files.wordpress.com/2016/06/fox-it_mofang_threatreport_tlp-white.pdf)
- [S0623 - Siloscape](../../../Threat%20Intelligence/Software/Malware/S0623%20-%20Siloscape.md) — [Siloscape](https://attack.mitre.org/software/S0623) checks for Kubernetes node permissions.(Citation: Unit 42 Siloscape Jun 2021) [Unit 42 Siloscape Jun 2021](https://unit42.paloaltonetworks.com/siloscape/)
- [C0024 - SolarWinds Compromise](../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) used the `Get-ManagementRoleAssignment` PowerShell cmdlet to enumerate Exchange management role assignments through an Exchange Management Shell.(Citation: Volexity SolarWinds) [Volexity SolarWinds](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/)
- [G0092 - TA505](../../../Threat%20Intelligence/Groups/G0092%20-%20TA505.md) — [TA505](https://attack.mitre.org/groups/G0092) has used TinyMet to enumerate members of privileged groups.(Citation: IBM TA505 April 2020) [TA505](https://attack.mitre.org/groups/G0092) has also run <code>net group /domain</code>.(Citation: Trend Micro TA505 June 2019) [IBM TA505 April 2020](https://web.archive.org/web/20200420201624/https://securityintelligence.com/posts/ta505-continues-to-infect-networks-with-sdbbot-rat/) · [Trend Micro TA505 June 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/shifting-tactics-breaking-down-ta505-groups-use-of-html-rats-and-other-techniques-in-latest-campaigns/)
- [S0266 - TrickBot](../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) can identify the groups the user on a compromised host belongs to.(Citation: Cyberreason Anchor December 2019) [Cyberreason Anchor December 2019](https://www.cybereason.com/blog/dropping-anchor-from-a-trickbot-infection-to-the-discovery-of-the-anchor-malware)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used commercial tools, LOTL utilities, and appliances already present on the system for group and user discovery.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0179 - Behavioral Detection of Permission Groups Discovery](../../../Defenses/Detection%20Strategies/DET0179%20-%20Behavioral%20Detection%20of%20Permission%20Groups%20Discovery.md)

## Sources

- [K8s Authorization Overview](https://kubernetes.io/docs/reference/access-authn-authz/authorization/)
- [CrowdStrike BloodHound April 2018](https://www.crowdstrike.com/blog/hidden-administrative-accounts-bloodhound-to-the-rescue/)
