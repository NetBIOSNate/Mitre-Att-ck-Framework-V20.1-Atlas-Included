# T1037.004 - RC Scripts

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1037 - Boot or Logon Initialization Scripts](../README.md)

Adversaries may establish persistence by modifying RC scripts, which are executed during a Unix-like system’s startup. These files allow system administrators to map and start custom services at startup for different run levels. RC scripts require root privileges to modify.

Adversaries may establish persistence by adding a malicious binary path or shell commands to <code>rc.local</code>, <code>rc.common</code>, and other RC scripts specific to the Unix-like distribution.(Citation: IranThreats Kittens Dec 2017)(Citation: Intezer HiddenWasp Map 2019) Upon reboot, the system executes the script's contents as root, resulting in persistence.

Adversary abuse of RC scripts is especially effective for lightweight Unix-like distributions using the root user as default, such as ESXi hypervisors, IoT, or embedded systems.(Citation: intezer-kaiji-malware) As ESXi servers store most system files in memory and therefore discard changes on shutdown, leveraging `/etc/rc.local.d/local.sh` is one of the few mechanisms for enabling persistence across reboots.(Citation: Juniper Networks ESXi Backdoor 2022)

Several Unix-like systems have moved to Systemd and deprecated the use of RC scripts. This is now a deprecated mechanism in macOS in favor of Launchd.(Citation: Apple Developer Doco Archive Launchd)(Citation: Startup Items) This technique can be used on Mac OS X Panther v10.3 and earlier versions which still execute the RC scripts.(Citation: Methods of Mac Malware Persistence) To maintain backwards compatibility some systems, such as Ubuntu, will execute the RC scripts if they exist with the correct file permissions.(Citation: Ubuntu Manpage systemd rc)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1037/004)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [ESXi](../../../../Platforms/ESXi.md)

## Detection strategies

- [DET0237 - Detection Strategy for Boot or Logon Initialization Scripts: RC Scripts](../../../../Defenses/Detection%20Strategies/DET0237%20-%20Detection%20Strategy%20for%20Boot%20or%20Logon%20Initialization%20Scripts%20-%20RC%20Scripts.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Limit privileges of user accounts so only authorized users can edit the `rc.common` file.

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has installed a run command on a compromised system to enable malware execution on system startup.(Citation: Mandiant APT29 Eye Spy Email Nov 22) [Mandiant APT29 Eye Spy Email Nov 22](https://www.mandiant.com/resources/blog/unc3524-eye-spy-email)
- [S0687 - Cyclops Blink](../../../../Threat%20Intelligence/Software/Malware/S0687%20-%20Cyclops%20Blink.md) — [Cyclops Blink](https://attack.mitre.org/software/S0687) has the ability to execute on device startup, using a modified RC script named S51armled.(Citation: NCSC Cyclops Blink February 2022) [NCSC Cyclops Blink February 2022](https://www.ncsc.gov.uk/files/Cyclops-Blink-Malware-Analysis-Report.pdf)
- [S0690 - Green Lambert](../../../../Threat%20Intelligence/Software/Malware/S0690%20-%20Green%20Lambert.md) — [Green Lambert](https://attack.mitre.org/software/S0690) can add <code>init.d</code> and <code>rc.d</code> files in the <code>/etc</code> folder to establish persistence.(Citation: Objective See Green Lambert for OSX Oct 2021)(Citation: Glitch-Cat Green Lambert ATTCK Oct 2021) [Objective See Green Lambert for OSX Oct 2021](https://objective-see.com/blog/blog_0x68.html) · [Glitch-Cat Green Lambert ATTCK Oct 2021](https://web.archive.org/web/20211018145402/https://www.glitch-cat.com/blog/green-lambert-and-attack)
- [S0394 - HiddenWasp](../../../../Threat%20Intelligence/Software/Malware/S0394%20-%20HiddenWasp.md) — [HiddenWasp](https://attack.mitre.org/software/S0394) installs reboot persistence by adding itself to <code>/etc/rc.local</code>.(Citation: Intezer HiddenWasp Map 2019) [Intezer HiddenWasp Map 2019](https://www.intezer.com/blog-hiddenwasp-malware-targeting-linux-systems/)
- [S0278 - iKitten](../../../../Threat%20Intelligence/Software/Malware/S0278%20-%20iKitten.md) — [iKitten](https://attack.mitre.org/software/S0278) adds an entry to the rc.common file for persistence.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [S9046 - IOControl](../../../../Threat%20Intelligence/Software/Malware/S9046%20-%20IOControl.md) — IOCONTROL has used an RC script (`/etc/rc3.d/S93InitSystemd.sh`) to establish persistence on a system across restarts.(Citation: Claroty-IOCONTROL)(Citation: Armis-IOCONTROL) [Claroty-IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol) · [Armis-IOCONTROL](https://www.armis.com/blog/iocontrol-malware-whats-new-whats-not/)
- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has utilized RC scripts to establish persistence in ESXi service.(Citation: CheckPointResearch_TheGentlemen_April2026) [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has placed a bash installation script into `/etc/rc.local.d/` to establish persistence.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)
- [G1047 - Velvet Ant](../../../../Threat%20Intelligence/Groups/G1047%20-%20Velvet%20Ant.md) — [Velvet Ant](https://attack.mitre.org/groups/G1047) used a modified `/etc/rc.local` file on compromised F5 BIG-IP devices to maintain persistence.(Citation: Sygnia VelvetAnt 2024A) [Sygnia VelvetAnt 2024A](https://www.sygnia.co/blog/china-nexus-threat-group-velvet-ant/)

## Sources

- [Apple Developer Doco Archive Launchd](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html)
- [Startup Items](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/StartupItems.html)
- [Juniper Networks ESXi Backdoor 2022](https://blogs.juniper.net/en-us/threat-research/a-custom-python-backdoor-for-vmware-esxi-servers)
- [Ubuntu Manpage systemd rc](http://manpages.ubuntu.com/manpages/bionic/man8/systemd-rc-local-generator.8.html)
- [IranThreats Kittens Dec 2017](https://iranthreats.github.io/resources/attribution-flying-rocket-kitten/)
- [Methods of Mac Malware Persistence](https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf)
- [intezer-kaiji-malware](https://www.intezer.com/blog/research/kaiji-new-chinese-linux-malware-turning-to-golang/)
- [Intezer HiddenWasp Map 2019](https://www.intezer.com/blog-hiddenwasp-malware-targeting-linux-systems/)
