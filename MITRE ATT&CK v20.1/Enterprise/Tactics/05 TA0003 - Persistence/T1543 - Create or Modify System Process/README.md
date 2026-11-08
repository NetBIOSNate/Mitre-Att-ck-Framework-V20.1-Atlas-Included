# T1543 - Create or Modify System Process

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may create or modify system-level processes to repeatedly execute malicious payloads as part of persistence. When operating systems boot up, they can start processes that perform background system functions. On Windows and Linux, these system processes are referred to as services.(Citation: TechNet Services) On macOS, launchd processes known as [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) and [Launch Agent](https://attack.mitre.org/techniques/T1543/001) are run to finish system initialization and load user specific parameters.(Citation: AppleDocs Launch Agent Daemons) 

Adversaries may install new services, daemons, or agents that can be configured to execute at startup or a repeatable interval in order to establish persistence. Similarly, adversaries may modify existing services, daemons, or agents to achieve the same effect.  

Services, daemons, or agents may be created with administrator privileges but executed under root/SYSTEM privileges. Adversaries may leverage this functionality to create or modify system processes in order to escalate privileges.(Citation: OSX Malware Detection)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1543)

**Tactics**  [Persistence](../README.md), [Privilege Escalation](../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1543.005 - Container Service](T1543.005%20-%20Container%20Service/README.md)
- [T1543.001 - Launch Agent](T1543.001%20-%20Launch%20Agent/README.md)
- [T1543.004 - Launch Daemon](T1543.004%20-%20Launch%20Daemon/README.md)
- [T1543.002 - Systemd Service](T1543.002%20-%20Systemd%20Service/README.md)
- [T1543.003 - Windows Service](T1543.003%20-%20Windows%20Service/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Use auditing tools capable of detecting privilege and service abuse opportunities on systems within an enterprise and correct them.
- [M1040 - Behavior Prevention on Endpoint](../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent an application from writing a signed vulnerable driver to the system.(Citation: Malicious Driver Reporting Center) On Windows 10 and 11, enable Microsoft Vulnerable Driver Blocklist to assist in hardening against third party-developed drivers.(Citation: Microsoft driver block rules) [Malicious Driver Reporting Center](https://www.microsoft.com/security/blog/2021/12/08/improve-kernel-security-with-the-new-microsoft-vulnerable-and-malicious-driver-reporting-center/) · [Microsoft driver block rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/microsoft-recommended-driver-block-rules)
- [M1045 - Code Signing](../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Enforce registration and execution of only legitimately signed service drivers where possible.
- [M1033 - Limit Software Installation](../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Restrict software installation to trusted repositories only and be cautious of orphaned software packages.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Ensure that Driver Signature Enforcement is enabled to restrict unsigned drivers from being installed.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Manage the creation, modification, use, and permissions associated to privileged accounts, including SYSTEM and root.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict read/write access to system-level process files to only select privileged users who have a legitimate need to manage system services.
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Where possible, consider enforcing the use of container services in rootless mode to limit the possibility of privilege escalation or malicious effects on the host running the container.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit privileges of user accounts and groups so that only authorized administrators can interact with system-level process changes and service configurations.

## Procedure examples

- [S1194 - Akira _v2](../../../Threat%20Intelligence/Software/Malware/S1194%20-%20Akira%20_v2.md) — [Akira _v2](https://attack.mitre.org/software/S1194) can create a child process for encryption.(Citation: CISA Akira Ransomware APR 2024) [CISA Akira Ransomware APR 2024](https://www.cisa.gov/sites/default/files/2024-04/aa24-109a-stopransomware-akira-ransomware_2.pdf)
- [S1184 - BOLDMOVE](../../../Threat%20Intelligence/Software/Malware/S1184%20-%20BOLDMOVE.md) — [BOLDMOVE](https://attack.mitre.org/software/S1184) can free all resources and terminate itself on victim machines.(Citation: Google Cloud BOLDMOVE 2023) [Google Cloud BOLDMOVE 2023](https://cloud.google.com/blog/topics/threat-intelligence/chinese-actors-exploit-fortios-flaw/)
- [S9015 - BRICKSTORM](../../../Threat%20Intelligence/Software/Malware/S9015%20-%20BRICKSTORM.md) — [BRICKSTORM](https://attack.mitre.org/software/S9015) has created a new background session and has spawned a child process of a parent process when it determines it is not running in its intended state.(Citation: CISA BRICKSTORM UNC5221 AR25-338A February 2026) [CISA BRICKSTORM UNC5221 AR25-338A February 2026](https://www.cisa.gov/news-events/analysis-reports/ar25-338a)
- [S9042 - CanisterWorm](../../../Threat%20Intelligence/Software/Malware/S9042%20-%20CanisterWorm.md) — [CanisterWorm](https://attack.mitre.org/software/S9042) can establish persistence in CI/CD environments by launching a background process (deploy.js) with stolen tokens.(Citation: Aikido TeamPCP Trivy MAR 2026) [Aikido TeamPCP Trivy MAR 2026](https://www.aikido.dev/blog/teampcp-deploys-worm-npm-trivy-compromise)
- [S0401 - Exaramel for Linux](../../../Threat%20Intelligence/Software/Malware/S0401%20-%20Exaramel%20for%20Linux.md) — [Exaramel for Linux](https://attack.mitre.org/software/S0401) has a hardcoded location that it uses to achieve persistence if the startup system is Upstart or System V and it is running as root.(Citation: ANSSI Sandworm January 2021) [ANSSI Sandworm January 2021](https://www.cert.ssi.gouv.fr/uploads/CERTFR-2021-CTI-005.pdf)
- [S1152 - IMAPLoader](../../../Threat%20Intelligence/Software/Malware/S1152%20-%20IMAPLoader.md) — [IMAPLoader](https://attack.mitre.org/software/S1152) modifies Windows tasks on the victim machine to reference a retrieved PE file through a path modification.(Citation: PWC Yellow Liderc 2023) [PWC Yellow Liderc 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [S1121 - LITTLELAMB.WOOLTEA](../../../Threat%20Intelligence/Software/Malware/S1121%20-%20LITTLELAMB.WOOLTEA.md) — [LITTLELAMB.WOOLTEA](https://attack.mitre.org/software/S1121) can initialize itself as a daemon to run persistently in the background.(Citation: Mandiant Cutting Edge Part 3 February 2024) [Mandiant Cutting Edge Part 3 February 2024](https://www.mandiant.com/resources/blog/investigating-ivanti-exploitation-persistence)
- [S1142 - LunarMail](../../../Threat%20Intelligence/Software/Malware/S1142%20-%20LunarMail.md) — [LunarMail](https://attack.mitre.org/software/S1142) can create an arbitrary process with a specified command line and redirect its output to a staging directory.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [S9050 - Vidar](../../../Threat%20Intelligence/Software/Malware/S9050%20-%20Vidar.md) — [Vidar](https://attack.mitre.org/software/S9050) has created the RegAsm.exe process in a suspended state.(Citation: Cyfirma_Vidar_June2024) [Cyfirma_Vidar_June2024](https://www.cyfirma.com/research/vidar-stealer-an-in-depth-analysis-of-an-information-stealing-malware/)

## Detection strategies

- [DET0571 - Detection of System Process Creation or Modification Across Platforms](../../../Defenses/Detection%20Strategies/DET0571%20-%20Detection%20of%20System%20Process%20Creation%20or%20Modification%20Across%20Platforms.md)

## Sources

- [AppleDocs Launch Agent Daemons](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html)
- [TechNet Services](https://technet.microsoft.com/en-us/library/cc772408.aspx)
- [OSX Malware Detection](https://papers.put.as/papers/macosx/2016/RSA_OSX_Malware.pdf)
