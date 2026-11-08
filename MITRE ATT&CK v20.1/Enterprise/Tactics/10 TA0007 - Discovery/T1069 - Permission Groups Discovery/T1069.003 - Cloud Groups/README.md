# T1069.003 - Cloud Groups

[Enterprise](../../../../README.md) / [Discovery](../../README.md) / [T1069 - Permission Groups Discovery](../README.md)

Adversaries may attempt to find cloud groups and permission settings. The knowledge of cloud permission groups can help adversaries determine the particular roles of users and groups within an environment, as well as which users are associated with a particular group.

With authenticated access there are several tools that can be used to find permissions groups. The <code>Get-MsolRole</code> PowerShell cmdlet can be used to obtain roles and permissions groups for Exchange and Office 365 accounts.(Citation: Microsoft Msolrole)(Citation: GitHub Raindance)

Azure CLI (AZ CLI) and the Google Cloud Identity Provider API also provide interfaces to obtain permissions groups. The command <code>az ad user get-member-groups</code> will list groups associated to a user account for Azure while the API endpoint <code>GET https://cloudidentity.googleapis.com/v1/groups</code> lists group resources available to a user for Google.(Citation: Microsoft AZ CLI)(Citation: Black Hills Red Teaming MS AD Azure, 2018)(Citation: Google Cloud Identity API Documentation) In AWS, the commands `ListRolePolicies` and `ListAttachedRolePolicies` allow users to enumerate the policies attached to a role.(Citation: Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022)

Adversaries may attempt to list ACLs for objects to determine the owner and other accounts with access to the object, for example, via the AWS <code>GetBucketAcl</code> API.(Citation: AWS Get Bucket ACL) Using this information an adversary can target accounts with permissions to a given object or leverage accounts they have already compromised to access the object.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1069/003)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md), [IaaS](../../../../Platforms/IaaS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can enumerate Azure AD groups.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) accessed Azure AD to download bulk lists of group members and their Active Directory attributes.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [S1091 - Pacu](../../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can enumerate IAM permissions.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [S0684 - ROADTools](../../../../Threat%20Intelligence/Software/Tools/S0684%20-%20ROADTools.md) — [ROADTools](https://attack.mitre.org/software/S0684) can enumerate Azure AD groups.(Citation: Roadtools) [Roadtools](https://dirkjanm.io/introducing-roadtools-and-roadrecon-azure-ad-exploration-framework/)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has executed API calls to enumerate permissions for compromised AWS accounts.(Citation: Unit42KelleyVaya_BlingLibra_Aug2024) [Unit42KelleyVaya_BlingLibra_Aug2024](https://unit42.paloaltonetworks.com/shinyhunters-ransomware-extortion/)

## Detection strategies

- [DET0251 - Behavioral Detection of Cloud Group Enumeration via API and CLI Access](../../../../Defenses/Detection%20Strategies/DET0251%20-%20Behavioral%20Detection%20of%20Cloud%20Group%20Enumeration%20via%20API%20and%20CLI%20Access.md)

## Sources

- [AWS Get Bucket ACL](https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetBucketAcl.html)
- [Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022](https://unit42.paloaltonetworks.com/compromised-cloud-compute-credentials/)
- [Black Hills Red Teaming MS AD Azure, 2018](https://www.blackhillsinfosec.com/red-teaming-microsoft-part-1-active-directory-leaks-via-azure/)
- [Google Cloud Identity API Documentation](https://cloud.google.com/identity/docs/reference/rest)
- [Microsoft AZ CLI](https://docs.microsoft.com/en-us/cli/azure/ad/user?view=azure-cli-latest)
- [Microsoft Msolrole](https://docs.microsoft.com/en-us/powershell/module/msonline/get-msolrole?view=azureadps-1.0)
- [GitHub Raindance](https://github.com/True-Demon/raindance)
