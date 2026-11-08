# T1021 - Remote Services

[Enterprise](../../../README.md) / [Lateral Movement](../README.md)

Adversaries may use [Valid Accounts](https://attack.mitre.org/techniques/T1078) to log into a service that accepts remote connections, such as telnet, SSH, and VNC. The adversary may then perform actions as the logged-on user.

In an enterprise environment, servers and workstations can be organized into domains. Domains provide centralized identity management, allowing users to log in using one set of credentials across the entire network. If an adversary is able to obtain a set of valid domain credentials, they could log in to many different machines using remote access protocols such as secure shell (SSH) or remote desktop protocol (RDP).(Citation: SSH Secure Shell)(Citation: TechNet Remote Desktop Services) They could also log in to accessible SaaS or IaaS services, such as those that federate their identities to the domain, or management platforms for internal virtualization environments such as VMware vCenter. 

Legitimate applications (such as [Software Deployment Tools](https://attack.mitre.org/techniques/T1072) and other administrative programs) may utilize [Remote Services](https://attack.mitre.org/techniques/T1021) to access remote hosts. For example, Apple Remote Desktop (ARD) on macOS is native software used for remote management. ARD leverages a blend of protocols, including [VNC](https://attack.mitre.org/techniques/T1021/005) to send the screen and control buffers and [SSH](https://attack.mitre.org/techniques/T1021/004) for secure file transfer.(Citation: Remote Management MDM macOS)(Citation: Kickstart Apple Remote Desktop commands)(Citation: Apple Remote Desktop Admin Guide 3.3) Adversaries can abuse applications such as ARD to gain remote code execution and perform lateral movement. In versions of macOS prior to 10.14, an adversary can escalate an SSH session to an ARD session which enables an adversary to accept TCC (Transparency, Consent, and Control) prompts without user interaction and gain access to data.(Citation: FireEye 2019 Apple Remote Desktop)(Citation: Lockboxx ARD 2019)(Citation: Kickstart Apple Remote Desktop commands)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1021)

**Tactics**  [Lateral Movement](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [IaaS](../../../Platforms/IaaS.md), [ESXi](../../../Platforms/ESXi.md)

## Sub-techniques

- [T1021.007 - Cloud Services](T1021.007%20-%20Cloud%20Services/README.md)
- [T1021.008 - Direct Cloud VM Connections](T1021.008%20-%20Direct%20Cloud%20VM%20Connections/README.md)
- [T1021.003 - Distributed Component Object Model](T1021.003%20-%20Distributed%20Component%20Object%20Model/README.md)
- [T1021.001 - Remote Desktop Protocol](T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1021.002 - SMB/Windows Admin Shares](T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1021.004 - SSH](T1021.004%20-%20SSH/README.md)
- [T1021.005 - VNC](T1021.005%20-%20VNC/README.md)
- [T1021.006 - Windows Remote Management](T1021.006%20-%20Windows%20Remote%20Management/README.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code with attempting to connect to other systems via FTP.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0143 - Aquatic Panda](../../../Threat%20Intelligence/Groups/G0143%20-%20Aquatic%20Panda.md) — [Aquatic Panda](https://attack.mitre.org/groups/G0143) used remote scheduled tasks to install malicious software on victim systems during lateral movement actions.(Citation: Crowdstrike HuntReport 2022) [Crowdstrike HuntReport 2022](https://go.crowdstrike.com/rs/281-OBQ-266/images/2022OverWatchThreatHuntingReport.pdf)
- [S1063 - Brute Ratel C4](../../../Threat%20Intelligence/Software/Tools/S1063%20-%20Brute%20Ratel%20C4.md) — [Brute Ratel C4](https://attack.mitre.org/software/S1063) has the ability to use RPC for lateral movement.(Citation: Palo Alto Brute Ratel July 2022) [Palo Alto Brute Ratel July 2022](https://unit42.paloaltonetworks.com/brute-ratel-c4-tool/)
- [G1003 - Ember Bear](../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) uses valid network credentials gathered through credential harvesting to move laterally within victim networks, often employing the [Impacket](https://attack.mitre.org/software/S0357) framework to do so.(Citation: Cadet Blizzard emerges as novel threat actor) [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [S0437 - Kivars](../../../Threat%20Intelligence/Software/Malware/S0437%20-%20Kivars.md) — [Kivars](https://attack.mitre.org/software/S0437) has the ability to remotely trigger keyboard input and mouse clicks. (Citation: TrendMicro BlackTech June 2017) [TrendMicro BlackTech June 2017](https://blog.trendmicro.com/trendlabs-security-intelligence/following-trail-blacktech-cyber-espionage-campaigns/)
- [S1016 - MacMa](../../../Threat%20Intelligence/Software/Malware/S1016%20-%20MacMa.md) — [MacMa](https://attack.mitre.org/software/S1016) can manage remote screen sessions.(Citation: ESET DazzleSpy Jan 2022) [ESET DazzleSpy Jan 2022](https://www.welivesecurity.com/2022/01/25/watering-hole-deploys-new-macos-malware-dazzlespy-asia/)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) can propagate via peer-to-peer communication and updates using RPC.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [G0102 - Wizard Spider](../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used the WebDAV protocol to execute [Ryuk](https://attack.mitre.org/software/S0446) payloads hosted on network file shares.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses.
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — If remote services, such as the ability to make direct connections to cloud virtual machines, are not required, disable these connection types where feasible. On ESXi servers, consider enabling lockdown mode, which disables direct access to an ESXi host and requires that the host be managed remotely using vCenter.(Citation: Google Cloud Threat Intelligence ESXi Hardening 2023)(Citation: Broadcom ESXi Lockdown Mode) [Google Cloud Threat Intelligence ESXi Hardening 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-detection-containment-hardening) · [Broadcom ESXi Lockdown Mode](https://knowledge.broadcom.com/external/article/336894/enabling-or-disabling-lockdown-mode-on-a.html)
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Prevent unnecessary remote access to file shares, hypervisors, sensitive systems, etc. Mechanisms to limit access may include use of network concentrators, RDP gateways, etc.(Citation: Sygnia ESXi Ransomware 2024) [Sygnia ESXi Ransomware 2024](https://www.sygnia.co/blog/esxi-ransomware-attacks/)
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication on remote service logons where possible.
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Do not reuse local administrator account passwords across systems. Ensure password complexity and uniqueness such that the passwords cannot be cracked or guessed.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit the accounts that may use remote services. Limit the permissions for accounts that are at higher risk of compromise; for example, configure SSH so users can only run specific programs.

## Detection strategies

- [DET0269 - Behavioral Detection Strategy for Remote Service Logins and Post-Access Activity](../../../Defenses/Detection%20Strategies/DET0269%20-%20Behavioral%20Detection%20Strategy%20for%20Remote%20Service%20Logins%20and%20Post-Access%20Activity.md)

## Sources

- [Apple Remote Desktop Admin Guide 3.3](https://images.apple.com/remotedesktop/pdf/ARD_Admin_Guide_v3.3.pdf)
- [Remote Management MDM macOS](https://support.apple.com/en-us/HT209161)
- [Kickstart Apple Remote Desktop commands](https://support.apple.com/en-us/HT201710)
- [Lockboxx ARD 2019](http://lockboxx.blogspot.com/2019/07/macos-red-teaming-206-ard-apple-remote.html)
- [FireEye 2019 Apple Remote Desktop](https://www.fireeye.com/blog/threat-research/2019/10/leveraging-apple-remote-desktop-for-good-and-evil.html)
- [TechNet Remote Desktop Services](https://technet.microsoft.com/en-us/windowsserver/ee236407.aspx)
- [SSH Secure Shell](https://www.ssh.com/ssh)
