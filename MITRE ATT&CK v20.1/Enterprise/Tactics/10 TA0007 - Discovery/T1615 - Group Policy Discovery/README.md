# T1615 - Group Policy Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may gather information on Group Policy settings to identify paths for privilege escalation, security measures applied within a domain, and to discover patterns in domain objects that can be manipulated or used to blend in the environment. Group Policy allows for centralized management of user and computer settings in Active Directory (AD). Group policy objects (GPOs) are containers for group policy settings made up of files stored within a predictable network path `\<DOMAIN>\SYSVOL\<DOMAIN>\Policies\`.(Citation: TechNet Group Policy Basics)(Citation: ADSecurity GPO Persistence 2016)

Adversaries may use commands such as <code>gpresult</code> or various publicly available PowerShell functions, such as <code>Get-DomainGPO</code> and <code>Get-DomainGPOLocalGroup</code>, to gather information on Group Policy settings.(Citation: Microsoft gpresult)(Citation: Github PowerShell Empire) Adversaries may use this information to shape follow-on behaviors, including determining potential attack paths within the target network as well as opportunities to manipulate Group Policy settings (i.e. [Domain or Tenant Policy Modification](https://attack.mitre.org/techniques/T1484)) for their benefit.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1615)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0521 - BloodHound](../../../Threat%20Intelligence/Software/Tools/S0521%20-%20BloodHound.md) — [BloodHound](https://attack.mitre.org/software/S0521) has the ability to collect local admin information via GPO.(Citation: GitHub Bloodhound) [GitHub Bloodhound](https://github.com/BloodHoundAD/BloodHound)
- [S1159 - DUSTTRAP](../../../Threat%20Intelligence/Software/Malware/S1159%20-%20DUSTTRAP.md) — [DUSTTRAP](https://attack.mitre.org/software/S1159) can identify victim environment Group Policy information.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [S0082 - Emissary](../../../Threat%20Intelligence/Software/Malware/S0082%20-%20Emissary.md) — [Emissary](https://attack.mitre.org/software/S0082) has the capability to execute <code>gpresult</code>.(Citation: Emissary Trojan Feb 2016) [Emissary Trojan Feb 2016](http://researchcenter.paloaltonetworks.com/2016/02/emissary-trojan-changelog-did-operation-lotus-blossom-cause-it-to-evolve/)
- [S0363 - Empire](../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) includes various modules for enumerating Group Policy.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [C0049 - Leviathan Australian Intrusions](../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) performed extensive Active Directory enumeration of victim environments during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [S1141 - LunarWeb](../../../Threat%20Intelligence/Software/Malware/S1141%20-%20LunarWeb.md) — [LunarWeb](https://attack.mitre.org/software/S1141) can capture information on group policy settings(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [G0010 - Turla](../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) surveys a system upon check-in to discover Group Policy details using the <code>gpresult</code> command.(Citation: ESET ComRAT May 2020) [ESET ComRAT May 2020](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET_Turla_ComRAT.pdf)

## Detection strategies

- [DET0055 - Detection strategy for Group Policy Discovery on Windows](../../../Defenses/Detection%20Strategies/DET0055%20-%20Detection%20strategy%20for%20Group%20Policy%20Discovery%20on%20Windows.md)

## Sources

- [ADSecurity GPO Persistence 2016](https://adsecurity.org/?p=2716)
- [Microsoft gpresult](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/gpresult)
- [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [TechNet Group Policy Basics](https://blogs.technet.microsoft.com/musings_of_a_technical_tam/2012/02/13/group-policy-basics-part-1-understanding-the-structure-of-a-group-policy-object/)
