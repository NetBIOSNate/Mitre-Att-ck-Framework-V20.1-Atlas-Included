# T1201 - Password Policy Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to access detailed information about the password policy used within an enterprise network or cloud environment. Password policies are a way to enforce complex passwords that are difficult to guess or crack through [Brute Force](https://attack.mitre.org/techniques/T1110). This information may help the adversary to create a list of common passwords and launch dictionary and/or brute force attacks which adhere to the policy (e.g. if the minimum password length should be 8, then not trying passwords such as 'pass123'; not checking for more than 3-4 passwords per account if the lockout is set to 6 as to not lock out accounts).

Password policies can be set and discovered on Windows, Linux, and macOS systems via various command shell utilities such as <code>net accounts (/domain)</code>, <code>Get-ADDefaultDomainPasswordPolicy</code>, <code>chage -l <username></code>, <code>cat /etc/pam.d/common-password</code>, and <code>pwpolicy getaccountpolicies</code>.(Citation: Superuser Linux Password Policies)(Citation: Jamf User Password Policies) Adversaries may also leverage a [Network Device CLI](https://attack.mitre.org/techniques/T1059/008) on network devices to discover password policy information (e.g. <code>show aaa</code>, <code>show aaa common-criteria policy all</code>).(Citation: US-CERT-TA18-106A)

Password policies can be discovered in cloud environments using available APIs such as <code>GetAccountPasswordPolicy</code> in AWS.(Citation: AWS GetPasswordPolicy)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1201)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [IaaS](../../../Platforms/IaaS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [SaaS](../../../Platforms/SaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Procedure examples

- [G0114 - Chimera](../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has used the NtdsAudit utility to collect information related to accounts and passwords.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [S0488 - CrackMapExec](../../../Threat%20Intelligence/Software/Tools/S0488%20-%20CrackMapExec.md) — [CrackMapExec](https://attack.mitre.org/software/S0488) can discover the password policies applied to the target system.(Citation: CME Github September 2018) [CME Github September 2018](https://github.com/byt3bl33d3r/CrackMapExec/wiki/SMB-Command-Reference)
- [S0236 - Kwampirs](../../../Threat%20Intelligence/Software/Malware/S0236%20-%20Kwampirs.md) — [Kwampirs](https://attack.mitre.org/software/S0236) collects password policy information with the command <code>net accounts</code>.(Citation: Symantec Orangeworm April 2018) [Symantec Orangeworm April 2018](https://www.symantec.com/blogs/threat-intelligence/orangeworm-targets-healthcare-us-europe-asia)
- [S0039 - Net](../../../Threat%20Intelligence/Software/Tools/S0039%20-%20Net.md) — The <code>net accounts</code> and <code>net accounts /domain</code> commands with [Net](https://attack.mitre.org/software/S0039) can be used to obtain password policy information.(Citation: Savill 1999) [Savill 1999](https://web.archive.org/web/20150511162820/http://windowsitpro.com/windows/netexe-reference)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has used net.exe in a script with <code>net accounts /domain</code> to find the password policy of a domain.(Citation: FireEye Targeted Attacks Middle East Banks) [FireEye Targeted Attacks Middle East Banks](https://web.archive.org/web/20200618235708/https://www.fireeye.com/blog/threat-research/2016/05/targeted_attacksaga.html)
- [C0012 - Operation CuckooBees](../../../Threat%20Intelligence/Campaigns/C0012%20-%20Operation%20CuckooBees.md) — During [Operation CuckooBees](https://attack.mitre.org/campaigns/C0012), the threat actors used the `net accounts` command as part of their advanced reconnaissance.(Citation: Cybereason OperationCuckooBees May 2022) [Cybereason OperationCuckooBees May 2022](https://www.cybereason.com/blog/operation-cuckoobees-deep-dive-into-stealthy-winnti-techniques)
- [S0378 - PoshC2](../../../Threat%20Intelligence/Software/Tools/S0378%20-%20PoshC2.md) — [PoshC2](https://attack.mitre.org/software/S0378) can use <code>Get-PassPol</code> to enumerate the domain password policy.(Citation: GitHub PoshC2) [GitHub PoshC2](https://github.com/nettitude/PoshC2_Python)
- [G0010 - Turla](../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has used <code>net accounts</code> and <code>net accounts /domain</code> to acquire password policy information.(Citation: ESET ComRAT May 2020) [ESET ComRAT May 2020](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET_Turla_ComRAT.pdf)

## Detection strategies

- [DET0161 - Password Policy Discovery – cross-platform behavior-chain analytics](../../../Defenses/Detection%20Strategies/DET0161%20-%20Password%20Policy%20Discovery%20%E2%80%93%20cross-platform%20behavior-chain%20analytics.md)

## Mitigations

- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure only valid password filters are registered. Filter DLLs must be present in Windows installation directory (<code>C:\Windows\System32\</code> by default) of a domain controller and/or local computer with a corresponding entry in <code>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\Notification Packages</code>. (Citation: Microsoft Install Password Filter n.d) [Microsoft Install Password Filter n.d](https://msdn.microsoft.com/library/windows/desktop/ms721766.aspx)

## Sources

- [AWS GetPasswordPolicy](https://docs.aws.amazon.com/IAM/latest/APIReference/API_GetAccountPasswordPolicy.html)
- [Jamf User Password Policies](https://www.jamf.com/jamf-nation/discussions/18574/user-password-policies-on-non-ad-machines)
- [Superuser Linux Password Policies](https://superuser.com/questions/150675/how-to-display-password-policy-information-for-a-user-ubuntu)
- [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
