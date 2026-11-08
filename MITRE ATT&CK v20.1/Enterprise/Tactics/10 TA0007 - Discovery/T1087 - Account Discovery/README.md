# T1087 - Account Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to get a listing of valid accounts, usernames, or email addresses on a system or within a compromised environment. This information can help adversaries determine which accounts exist, which can aid in follow-on behavior such as brute-forcing, spear-phishing attacks, or account takeovers (e.g., [Valid Accounts](https://attack.mitre.org/techniques/T1078)).

Adversaries may use several methods to enumerate accounts, including abuse of existing tools, built-in commands, and potential misconfigurations that leak account names and roles or permissions in the targeted environment.

For examples, cloud environments typically provide easily accessible interfaces to obtain user lists.(Citation: AWS List Users)(Citation: Google Cloud - IAM Servie Accounts List API) On hosts, adversaries can use default [PowerShell](https://attack.mitre.org/techniques/T1059/001) and other command line functionality to identify accounts. Information about email addresses and accounts may also be extracted by searching an infected system’s files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1087)

**Tactics**  [Discovery](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [IaaS](../../../Platforms/IaaS.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1087.004 - Cloud Account](T1087.004%20-%20Cloud%20Account/README.md)
- [T1087.002 - Domain Account](T1087.002%20-%20Domain%20Account/README.md)
- [T1087.003 - Email Account](T1087.003%20-%20Email%20Account/README.md)
- [T1087.001 - Local Account](T1087.001%20-%20Local%20Account/README.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code to attempt to discover accounts by cycling through relative identifiers (RIDs).(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [C0062 - Anthropic AI-orchestrated Campaign](../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary used Claude Code to query internal database user account tables to enumerate accounts and identify high-privilege accounts within compromised environments.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [G0143 - Aquatic Panda](../../../Threat%20Intelligence/Groups/G0143%20-%20Aquatic%20Panda.md) — [Aquatic Panda](https://attack.mitre.org/groups/G0143) used the <code>last</code> command in Linux environments to identify recently logged-in users on victim machines.(Citation: Crowdstrike HuntReport 2022) [Crowdstrike HuntReport 2022](https://go.crowdstrike.com/rs/281-OBQ-266/images/2022OverWatchThreatHuntingReport.pdf)
- [G1016 - FIN13](../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has enumerated all users and their roles from a victim's main treasury system.(Citation: Mandiant FIN13 Aug 2022) [Mandiant FIN13 Aug 2022](https://www.mandiant.com/resources/blog/fin13-cybercriminal-mexico)
- [S1229 - Havoc](../../../Threat%20Intelligence/Software/Malware/S1229%20-%20Havoc.md) — [Havoc](https://attack.mitre.org/software/S1229) can identify privileged user accounts on infected systems.(Citation: Fortinet Havoc MAR 2025) [Fortinet Havoc MAR 2025](https://www.fortinet.com/blog/threat-research/havoc-sharepoint-with-microsoft-graph-api-turns-into-fud-c2)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has identified vSphere administrator accounts.(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [S0445 - ShimRatReporter](../../../Threat%20Intelligence/Software/Tools/S0445%20-%20ShimRatReporter.md) — [ShimRatReporter](https://attack.mitre.org/software/S0445) listed all non-privileged and privileged accounts available on the machine.(Citation: FOX-IT May 2016 Mofang) [FOX-IT May 2016 Mofang](https://foxitsecurity.files.wordpress.com/2016/06/fox-it_mofang_threatreport_tlp-white.pdf)
- [C0024 - SolarWinds Compromise](../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) obtained a list of users and their roles from an Exchange server using `Get-ManagementRoleAssignment`.(Citation: Volexity SolarWinds) [Volexity SolarWinds](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/)
- [S1239 - TONESHELL](../../../Threat%20Intelligence/Software/Malware/S1239%20-%20TONESHELL.md) — [TONESHELL](https://attack.mitre.org/software/S1239) included functionality to retrieve a list of user accounts.(Citation: Zscaler) [Zscaler](https://www.zscaler.com/blogs/security-research/latest-mustang-panda-arsenal-toneshell-and-starproxy-p1)
- [S1065 - Woody RAT](../../../Threat%20Intelligence/Software/Malware/S1065%20-%20Woody%20RAT.md) — [Woody RAT](https://attack.mitre.org/software/S1065) can identify administrator accounts on an infected machine.(Citation: MalwareBytes WoodyRAT Aug 2022) [MalwareBytes WoodyRAT Aug 2022](https://www.malwarebytes.com/blog/threat-intelligence/2022/08/woody-rat-a-new-feature-rich-malware-spotted-in-the-wild)
- [S0658 - XCSSET](../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — [XCSSET](https://attack.mitre.org/software/S0658) attempts to discover accounts from various locations such as a user's Evernote, AppleID, Telegram, Skype, and WeChat data.(Citation: trendmicro xcsset xcode project 2020) [trendmicro xcsset xcode project 2020](https://documents.trendmicro.com/assets/pdf/XCSSET_Technical_Brief.pdf)

## Mitigations

- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Prevent administrator accounts from being enumerated when an application is elevating through UAC since it can lead to the disclosure of account names. The Registry key is located <code>HKLM\ SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\CredUI\EnumerateAdministrators</code>. It can be disabled through GPO: Computer Configuration > [Policies] > Administrative Templates > Windows Components > Credential User Interface: E numerate administrator accounts on elevation. (Citation: UCF STIG Elevation Account Enumeration) [UCF STIG Elevation Account Enumeration](https://www.stigviewer.com/stig/microsoft_windows_server_2012_member_server/2013-07-25/finding/WN12-CC-000077)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Manage the creation, modification, use, and permissions associated to user accounts.

## Detection strategies

- [DET0587 - Enumeration of User or Account Information Across Platforms](../../../Defenses/Detection%20Strategies/DET0587%20-%20Enumeration%20of%20User%20or%20Account%20Information%20Across%20Platforms.md)

## Sources

- [AWS List Users](https://docs.aws.amazon.com/cli/latest/reference/iam/list-users.html)
- [Google Cloud - IAM Servie Accounts List API](https://cloud.google.com/sdk/gcloud/reference/iam/service-accounts/list)
- [Elastic - Koadiac Detection with EQL](https://www.elastic.co/security-labs/embracing-offensive-tooling-building-detections-against-koadic-using-eql)
