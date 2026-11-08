# T1021.005 - VNC

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1021 - Remote Services](../README.md)

Adversaries may use [Valid Accounts](https://attack.mitre.org/techniques/T1078) to remotely control machines using Virtual Network Computing (VNC).  VNC is a platform-independent desktop sharing system that uses the RFB (“remote framebuffer”) protocol to enable users to remotely control another computer’s display by relaying the screen, mouse, and keyboard inputs over the network.(Citation: The Remote Framebuffer Protocol)

VNC differs from [Remote Desktop Protocol](https://attack.mitre.org/techniques/T1021/001) as VNC is screen-sharing software rather than resource-sharing software. By default, VNC uses the system's authentication, but it can be configured to use credentials specific to VNC.(Citation: MacOS VNC software for Remote Desktop)(Citation: VNC Authentication)

Adversaries may abuse VNC to perform malicious actions as the logged-on user such as opening documents, downloading files, and running arbitrary commands. An adversary could use VNC to remotely control and monitor a system to collect data and information to pivot to other systems within the network. Specific VNC libraries/implementations have also been susceptible to brute force attacks and memory usage exploitation.(Citation: Hijacking VNC)(Citation: macOS root VNC login without authentication)(Citation: VNC Vulnerabilities)(Citation: Offensive Security VNC Authentication Check)(Citation: Attacking VNC Servers PentestLab)(Citation: Havana authentication bug)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1021/005)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Inventory workstations for unauthorized VNC server software.
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Uninstall any VNC server software where not required.
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — VNC defaults to TCP ports 5900 for the server, 5800 for browser access, and 5500 for a viewer in listening mode. Filtering or blocking these ports will inhibit VNC traffic utilizing default ports.
- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Restrict software installation to user groups that require it. A VNC server must be manually installed by the user or adversary.

## Procedure examples

- [S0484 - Carberp](../../../../Threat%20Intelligence/Software/Malware/S0484%20-%20Carberp.md) — [Carberp](https://attack.mitre.org/software/S0484) can start a remote VNC session by downloading a new plugin.(Citation: Prevx Carberp March 2011) [Prevx Carberp March 2011](https://web.archive.org/web/20231227000328/http://pxnow.prevx.com/content/blog/carberp-a_modular_information_stealing_trojan.pdf)
- [S1014 - DanBot](../../../../Threat%20Intelligence/Software/Malware/S1014%20-%20DanBot.md) — [DanBot](https://attack.mitre.org/software/S1014) can use VNC for remote access to targeted systems.(Citation: ClearSky Siamesekitten August 2021) [ClearSky Siamesekitten August 2021](https://www.clearskysec.com/siamesekitten/)
- [G0046 - FIN7](../../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) has used TightVNC to control compromised hosts.(Citation: CrowdStrike Carbon Spider August 2021) [CrowdStrike Carbon Spider August 2021](https://www.crowdstrike.com/blog/carbon-spider-embraces-big-game-hunting-part-1/)
- [G0117 - Fox Kitten](../../../../Threat%20Intelligence/Groups/G0117%20-%20Fox%20Kitten.md) — [Fox Kitten](https://attack.mitre.org/groups/G0117) has installed TightVNC server and client on compromised servers and endpoints for lateral movement.(Citation: CISA AA20-259A Iran-Based Actor September 2020) [CISA AA20-259A Iran-Based Actor September 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-259a)
- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used VNC tools, including UltraVNC, to remotely interact with compromised hosts.(Citation: Symantec Shuckworm January 2022)(Citation: Microsoft Actinium February 2022)(Citation: Unit 42 Gamaredon February 2022) [Microsoft Actinium February 2022](https://www.microsoft.com/security/blog/2022/02/04/actinium-targets-ukrainian-organizations/) · [Symantec Shuckworm January 2022](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/shuckworm-gamaredon-espionage-ukraine) · [Unit 42 Gamaredon February 2022](https://unit42.paloaltonetworks.com/gamaredon-primitive-bear-ukraine-update-2021/)
- [G0036 - GCMAN](../../../../Threat%20Intelligence/Groups/G0036%20-%20GCMAN.md) — [GCMAN](https://attack.mitre.org/groups/G0036) uses VNC for lateral movement.(Citation: Securelist GCMAN) [Securelist GCMAN](https://securelist.com/apt-style-bank-robberies-increase-with-metel-gcman-and-carbanak-2-0-attacks/73638/)
- [S1160 - Latrodectus](../../../../Threat%20Intelligence/Software/Malware/S1160%20-%20Latrodectus.md) — [Latrodectus](https://attack.mitre.org/software/S1160) has routed C2 traffic using Keyhole VNC.(Citation: Palo Alto Latrodectus Activity June 2024) [Palo Alto Latrodectus Activity June 2024](https://github.com/PaloAltoNetworks/Unit42-timely-threat-intel/blob/main/2024-06-25-IOCs-from-Latrodectus-activity.txt)
- [S0279 - Proton](../../../../Threat%20Intelligence/Software/Malware/S0279%20-%20Proton.md) — [Proton](https://attack.mitre.org/software/S0279) uses VNC to connect into systems.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) has used a VNC module to monitor the victim and collect information to pivot to valuable systems on the network (Citation: Trickbot VNC module July 2021)(Citation: Bitdefender Trickbot VNC module Whitepaper 2021) [Trickbot VNC module July 2021](https://www.bleepingcomputer.com/news/security/trickbot-updates-its-vnc-module-for-high-value-targets/) · [Bitdefender Trickbot VNC module Whitepaper 2021](https://www.bitdefender.com/files/News/CaseStudies/study/399/Bitdefender-PR-Whitepaper-Trickbot-creat5515-en-EN.pdf)
- [S0670 - WarzoneRAT](../../../../Threat%20Intelligence/Software/Malware/S0670%20-%20WarzoneRAT.md) — [WarzoneRAT](https://attack.mitre.org/software/S0670) has the ability of performing remote desktop access via a VNC console.(Citation: Check Point Warzone Feb 2020) [Check Point Warzone Feb 2020](https://research.checkpoint.com/2020/warzone-behind-the-enemy-lines/)
- [S0412 - ZxShell](../../../../Threat%20Intelligence/Software/Malware/S0412%20-%20ZxShell.md) — [ZxShell](https://attack.mitre.org/software/S0412) supports functionality for VNC sessions.(Citation: Talos ZxShell Oct 2014) [Talos ZxShell Oct 2014](https://blogs.cisco.com/security/talos/opening-zxshell)

## Detection strategies

- [DET0178 - Behavioral Detection of Unauthorized VNC Remote Control Sessions](../../../../Defenses/Detection%20Strategies/DET0178%20-%20Behavioral%20Detection%20of%20Unauthorized%20VNC%20Remote%20Control%20Sessions.md)

## Sources

- [Attacking VNC Servers PentestLab](https://pentestlab.blog/2012/10/30/attacking-vnc-servers/)
- [MacOS VNC software for Remote Desktop](https://support.apple.com/guide/remote-desktop/set-up-a-computer-running-vnc-software-apdbed09830/mac)
- [Havana authentication bug](https://lists.openstack.org/pipermail/openstack/2013-December/004138.html)
- [macOS root VNC login without authentication](https://www.tenable.com/blog/detecting-macos-high-sierra-root-account-without-authentication)
- [Offensive Security VNC Authentication Check](https://www.offensive-security.com/metasploit-unleashed/vnc-authentication/)
- [Gnome Remote Desktop grd-settings](https://gitlab.gnome.org/GNOME/gnome-remote-desktop/-/blob/9aa9181e/src/grd-settings.c#L207)
- [Gnome Remote Desktop gschema](https://gitlab.gnome.org/GNOME/gnome-remote-desktop/-/blob/9aa9181e/src/org.gnome.desktop.remote-desktop.gschema.xml.in)
- [Apple Unified Log Analysis Remote Login and Screen Sharing](https://sarah-edwards-xzkc.squarespace.com/blog/2020/4/30/analysis-of-apple-unified-logs-quarantine-edition-entry-6-working-from-home-remote-logins)
- [VNC Vulnerabilities](https://www.bleepingcomputer.com/news/security/dozens-of-vnc-vulnerabilities-found-in-linux-windows-solutions/)
- [The Remote Framebuffer Protocol](https://datatracker.ietf.org/doc/html/rfc6143#section-7.2.2)
- [VNC Authentication](https://help.realvnc.com/hc/en-us/articles/360002250097-Setting-up-System-Authentication)
- [Hijacking VNC](https://int0x33.medium.com/day-70-hijacking-vnc-enum-brute-access-and-crack-d3d18a4601cc)
