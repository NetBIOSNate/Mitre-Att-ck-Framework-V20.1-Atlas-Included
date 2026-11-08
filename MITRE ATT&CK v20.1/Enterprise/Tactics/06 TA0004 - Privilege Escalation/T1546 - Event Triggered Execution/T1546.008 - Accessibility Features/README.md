# T1546.008 - Accessibility Features

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by accessibility features. Windows contains accessibility features that may be launched with a key combination before a user has logged in (ex: when the user is on the Windows logon screen). An adversary can modify the way these programs are launched to get a command prompt or backdoor without logging in to the system.

Two common accessibility programs are <code>C:\Windows\System32\sethc.exe</code>, launched when the shift key is pressed five times and <code>C:\Windows\System32\utilman.exe</code>, launched when the Windows + U key combination is pressed. The sethc.exe program is often referred to as "sticky keys", and has been used by adversaries for unauthenticated access through a remote desktop login screen.(Citation: FireEye Hikit Rootkit)

Depending on the version of Windows, an adversary may take advantage of these features in different ways. Common methods used by adversaries include replacing accessibility feature binaries or pointers/references to these binaries in the Registry. In newer versions of Windows, the replaced binary needs to be digitally signed for x64 systems, the binary must reside in <code>%systemdir%\</code>, and it must be protected by Windows File or Resource Protection (WFP/WRP).(Citation: DEFCON2016 Sticky Keys) The [Image File Execution Options Injection](https://attack.mitre.org/techniques/T1546/012) debugger method was likely discovered as a potential workaround because it does not require the corresponding accessibility feature binary to be replaced.

For simple binary replacement on Windows XP and later as well as Windows Server 2003/R2 and later, for example, the program (e.g., <code>C:\Windows\System32\utilman.exe</code>) may be replaced with "cmd.exe" (or another program that provides backdoor access). Subsequently, pressing the appropriate key combination at the login screen while sitting at the keyboard or when connected over [Remote Desktop Protocol](https://attack.mitre.org/techniques/T1021/001) will cause the replaced file to be executed with SYSTEM privileges.(Citation: Tilbury 2014)

Other accessibility features exist that may also be leveraged in a similar fashion:(Citation: DEFCON2016 Sticky Keys)(Citation: Narrator Accessibility Abuse)

* On-Screen Keyboard: <code>C:\Windows\System32\osk.exe</code>
* Magnifier: <code>C:\Windows\System32\Magnify.exe</code>
* Narrator: <code>C:\Windows\System32\Narrator.exe</code>
* Display Switcher: <code>C:\Windows\System32\DisplaySwitch.exe</code>
* App Switcher: <code>C:\Windows\System32\AtBroker.exe</code>

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/008)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) used sticky-keys to obtain unauthenticated, privileged console access.(Citation: Mandiant No Easy Breach)(Citation: FireEye APT29 Domain Fronting) [FireEye APT29 Domain Fronting](https://www.fireeye.com/blog/threat-research/2017/03/apt29_domain_frontin.html) · [Mandiant No Easy Breach](https://www.slideshare.net/slideshow/no-easy-breach-derby-con-2016/66447908)
- [G0022 - APT3](../../../../Threat%20Intelligence/Groups/G0022%20-%20APT3.md) — [APT3](https://attack.mitre.org/groups/G0022) replaces the Sticky Keys binary <code>C:\Windows\System32\sethc.exe</code> for persistence.(Citation: aptsim) [aptsim](http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html)
- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) leveraged sticky keys to establish persistence.(Citation: FireEye APT41 Aug 2019) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [G0001 - Axiom](../../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) actors have been known to use the Sticky Keys replacement within RDP sessions to obtain persistence.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G0009 - Deep Panda](../../../../Threat%20Intelligence/Groups/G0009%20-%20Deep%20Panda.md) — [Deep Panda](https://attack.mitre.org/groups/G0009) has used the sticky-keys technique to bypass the RDP login screen on remote systems during intrusions.(Citation: RSA Shell Crew) [RSA Shell Crew](https://www.rsa.com/content/dam/en/white-paper/rsa-incident-response-emerging-threat-profile-shell-crew.pdf)
- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can leverage WMI debugging to remotely replace binaries like sethc.exe, Utilman.exe, and Magnify.exe with cmd.exe.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [G0117 - Fox Kitten](../../../../Threat%20Intelligence/Groups/G0117%20-%20Fox%20Kitten.md) — [Fox Kitten](https://attack.mitre.org/groups/G0117) has used sticky keys to launch a command prompt.(Citation: CISA AA20-259A Iran-Based Actor September 2020) [CISA AA20-259A Iran-Based Actor September 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-259a)

## Detection strategies

- [DET0033 - Detection Strategy for Accessibility Feature Hijacking via Binary Replacement or Registry Modification](../../../../Defenses/Detection%20Strategies/DET0033%20-%20Detection%20Strategy%20for%20Accessibility%20Feature%20Hijacking%20via%20Binary%20Replacement%20or%20Regi.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Adversaries can replace accessibility features binaries with alternate binaries to execute this technique. Identify and block potentially malicious software executed through accessibility features functionality by using application control (Citation: Beechey 2010) tools, like Windows Defender Application Control(Citation: Microsoft Windows Defender Application Control), AppLocker, (Citation: Windows Commands JPCERT) (Citation: NSA MS AppLocker) or Software Restriction Policies (Citation: Corio 2008) where appropriate. (Citation: TechNet Applocker vs SRP) [Beechey 2010](http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Corio 2008](https://learn.microsoft.com/en-us/previous-versions/technet-magazine/cc510322%28v=msdn.10%29) · [Microsoft Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) · [TechNet Applocker vs SRP](https://technet.microsoft.com/en-us/library/ee791851.aspx) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html)
- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — If possible, use a Remote Desktop Gateway to manage connections and security configuration of RDP within a network.(Citation: TechNet RDP Gateway) [TechNet RDP Gateway](https://technet.microsoft.com/en-us/library/cc731150.aspx)
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — To use this technique remotely, an adversary must use it in conjunction with RDP. Ensure that Network Level Authentication is enabled to force the remote desktop session to authenticate before the session is created and the login screen displayed. It is enabled by default on Windows Vista and later.(Citation: TechNet RDP NLA) [TechNet RDP NLA](https://technet.microsoft.com/en-us/library/cc732713.aspx)

## Sources

- [Narrator Accessibility Abuse](https://giuliocomi.blogspot.com/2019/10/abusing-windows-10-narrators-feedback.html)
- [FireEye Hikit Rootkit](https://web.archive.org/web/20190216180458/https://www.fireeye.com/blog/threat-research/2012/08/hikit-rootkit-advanced-persistent-attack-techniques-part-1.html)
- [DEFCON2016 Sticky Keys](https://www.slideshare.net/DennisMaldonado5/sticky-keys-to-the-kingdom)
- [Tilbury 2014](https://web.archive.org/web/20200730053039/https://www.crowdstrike.com/blog/registry-analysis-with-crowdresponse/)
