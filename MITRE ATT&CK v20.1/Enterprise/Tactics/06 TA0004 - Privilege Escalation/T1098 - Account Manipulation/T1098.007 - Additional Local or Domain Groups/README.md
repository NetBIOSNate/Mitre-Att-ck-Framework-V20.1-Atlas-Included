# T1098.007 - Additional Local or Domain Groups

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1098 - Account Manipulation](../README.md)

An adversary may add additional local or domain groups to an adversary-controlled account to maintain persistent access to a system or domain.

On Windows, accounts may use the `net localgroup` and `net group` commands to add existing users to local and domain groups.(Citation: Microsoft Net Localgroup)(Citation: Microsoft Net Group) On Linux, adversaries may use the `usermod` command for the same purpose.(Citation: Linux Usermod)

For example, accounts may be added to the local administrators group on Windows devices to maintain elevated privileges. They may also be added to the Remote Desktop Users group, which allows them to leverage [Remote Desktop Protocol](https://attack.mitre.org/techniques/T1021/001) to log into the endpoints in the future.(Citation: Microsoft RDP Logons) Adversaries may also add accounts to VPN user groups to gain future persistence on the network.(Citation: Cyber Security News) On Linux, accounts may be added to the sudoers group, allowing them to persistently leverage [Sudo and Sudo Caching](https://attack.mitre.org/techniques/T1548/003) for elevated privileges. 

In Windows environments, machine accounts may also be added to domain groups. This allows the local SYSTEM account to gain privileges on the domain.(Citation: RootDSE AD Detection 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/007)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0310 - Suspicious Addition to Local or Domain Groups](../../../../Defenses/Detection%20Strategies/DET0310%20-%20Suspicious%20Addition%20to%20Local%20or%20Domain%20Groups.md)

## Procedure examples

- [G0022 - APT3](../../../../Threat%20Intelligence/Groups/G0022%20-%20APT3.md) — [APT3](https://attack.mitre.org/groups/G0022) has been known to add created accounts to local admin groups to maintain elevated access.(Citation: aptsim) [aptsim](http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html)
- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) has added user accounts to the User and Admin groups.(Citation: FireEye APT41 Aug 2019) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [G1023 - APT5](../../../../Threat%20Intelligence/Groups/G1023%20-%20APT5.md) — [APT5](https://attack.mitre.org/groups/G1023) has created their own accounts with Local Administrator privileges to maintain access to systems with short-cycle credential rotation.(Citation: Mandiant Pulse Secure Update May 2021) [Mandiant Pulse Secure Update May 2021](https://www.mandiant.com/resources/blog/updates-on-chinese-apt-compromising-pulse-secure-vpn-devices)
- [S1111 - DarkGate](../../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) elevates accounts created through the malware to the local administration group during execution.(Citation: Ensilo Darkgate 2018) [Ensilo Darkgate 2018](https://www.fortinet.com/blog/threat-research/enter-the-darkgate-new-cryptocurrency-mining-and-ransomware-campaign)
- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has added newly created accounts to the administrators group to maintain elevated access.(Citation: US-CERT TA18-074A) [US-CERT TA18-074A](https://www.us-cert.gov/ncas/alerts/TA18-074A)
- [G1016 - FIN13](../../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has assigned newly created accounts the sysadmin role to maintain persistence.(Citation: Sygnia Elephant Beetle Jan 2022) [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has added accounts to specific groups with <code>net localgroup</code>.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has added a user named DefaultAccount to the Administrators and Remote Desktop Users groups.(Citation: DFIR Report APT35 ProxyShell March 2022) [DFIR Report APT35 ProxyShell March 2022](https://thedfirreport.com/2022/03/21/apt35-automates-initial-access-using-proxyshell)
- [S0039 - Net](../../../../Threat%20Intelligence/Software/Tools/S0039%20-%20Net.md) — The `net localgroup` and `net group` commands in [Net](https://attack.mitre.org/software/S0039) can be used to add existing users to local and domain groups.(Citation: Microsoft Net Localgroup) (Citation: Microsoft Net Group) [Microsoft Net Group](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc754051%28v=ws.11%29) · [Microsoft Net Localgroup](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc725622%28v=ws.11%29)
- [S0382 - ServHelper](../../../../Threat%20Intelligence/Software/Malware/S0382%20-%20ServHelper.md) — [ServHelper](https://attack.mitre.org/software/S0382) has added a user named "supportaccount" to the Remote Desktop Users and Administrators groups.(Citation: Proofpoint TA505 Jan 2019) [Proofpoint TA505 Jan 2019](https://www.proofpoint.com/us/threat-insight/post/servhelper-and-flawedgrace-new-malware-introduced-ta505)
- [S0649 - SMOKEDHAM](../../../../Threat%20Intelligence/Software/Malware/S0649%20-%20SMOKEDHAM.md) — [SMOKEDHAM](https://attack.mitre.org/software/S0649) has added user accounts to local Admin groups.(Citation: FireEye SMOKEDHAM June 2021) [FireEye SMOKEDHAM June 2021](https://www.fireeye.com/blog/threat-research/2021/06/darkside-affiliate-supply-chain-software-compromise.html)

## Sources

- [Cyber Security News](https://cybersecuritynews.com/superblack-actors-exploiting-two-fortinet-vulnerabilities/)
- [Linux Usermod](https://www.man7.org/linux/man-pages/man8/usermod.8.html)
- [Microsoft Net Group](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc754051%28v=ws.11%29)
- [Microsoft Net Localgroup](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc725622%28v=ws.11%29)
- [Microsoft RDP Logons](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/security-policy-settings/allow-log-on-through-remote-desktop-services)
- [RootDSE AD Detection 2022](https://rootdse.org/posts/monitoring-realtime-activedirectory-domain-scenarios)
