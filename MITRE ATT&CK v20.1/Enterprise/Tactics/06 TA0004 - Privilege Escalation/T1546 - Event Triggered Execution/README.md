# T1546 - Event Triggered Execution

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may establish persistence and/or elevate privileges using system mechanisms that trigger execution based on specific events. Various operating systems have means to monitor and subscribe to events such as logons or other user activity such as running specific applications/binaries. Cloud environments may also support various functions and services that monitor and can be invoked in response to specific cloud events.(Citation: Backdooring an AWS account)(Citation: Varonis Power Automate Data Exfiltration)(Citation: Microsoft DART Case Report 001)

Adversaries may abuse these mechanisms as a means of maintaining persistent access to a victim via repeatedly executing malicious code. After gaining access to a victim system, adversaries may create/modify event triggers to point to malicious content that will be executed whenever the event trigger is invoked.(Citation: FireEye WMI 2015)(Citation: Malware Persistence on OS X)(Citation: amnesia malware)

Since the execution can be proxied by an account with higher permissions, such as SYSTEM or service accounts, an adversary may be able to abuse these triggered execution mechanisms to escalate their privileges.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546)

**Tactics**  [Persistence](../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Sub-techniques

- [T1546.008 - Accessibility Features](T1546.008%20-%20Accessibility%20Features/README.md)
- [T1546.009 - AppCert DLLs](T1546.009%20-%20AppCert%20DLLs/README.md)
- [T1546.010 - AppInit DLLs](T1546.010%20-%20AppInit%20DLLs/README.md)
- [T1546.011 - Application Shimming](T1546.011%20-%20Application%20Shimming/README.md)
- [T1546.001 - Change Default File Association](T1546.001%20-%20Change%20Default%20File%20Association/README.md)
- [T1546.015 - Component Object Model Hijacking](T1546.015%20-%20Component%20Object%20Model%20Hijacking/README.md)
- [T1546.014 - Emond](T1546.014%20-%20Emond/README.md)
- [T1546.012 - Image File Execution Options Injection](T1546.012%20-%20Image%20File%20Execution%20Options%20Injection/README.md)
- [T1546.016 - Installer Packages](T1546.016%20-%20Installer%20Packages/README.md)
- [T1546.006 - LC_LOAD_DYLIB Addition](T1546.006%20-%20LC_LOAD_DYLIB%20Addition/README.md)
- [T1546.007 - Netsh Helper DLL](T1546.007%20-%20Netsh%20Helper%20DLL/README.md)
- [T1546.013 - PowerShell Profile](T1546.013%20-%20PowerShell%20Profile/README.md)
- [T1546.018 - Python Startup Hooks](T1546.018%20-%20Python%20Startup%20Hooks/README.md)
- [T1546.002 - Screensaver](T1546.002%20-%20Screensaver/README.md)
- [T1546.005 - Trap](T1546.005%20-%20Trap/README.md)
- [T1546.017 - Udev Rules](T1546.017%20-%20Udev%20Rules/README.md)
- [T1546.004 - Unix Shell Configuration Modification](T1546.004%20-%20Unix%20Shell%20Configuration%20Modification/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)

## Procedure examples

- [C0035 - KV Botnet Activity](../../../Threat%20Intelligence/Campaigns/C0035%20-%20KV%20Botnet%20Activity.md) — [KV Botnet Activity](https://attack.mitre.org/campaigns/C0035) involves managing events on victim systems via <code>libevent</code> to execute a callback function when any running process contains the following references in their path without also having a reference to <code>bioset</code>: busybox, wget, curl, tftp, telnetd, or lua. If the <code>bioset</code> string is not found, the related process is terminated.(Citation: Lumen KVBotnet 2023) [Lumen KVBotnet 2023](https://blog.lumen.com/routers-roasting-on-an-open-firewall-the-kv-botnet-investigation/)
- [S9043 - Mini Shai-Hulud](../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has modified settings and configuration files of AI coding agents and other coding applications in order to create event triggered executions through creating hooks and runOn conditions.(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/)
- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can set up S3 bucket notifications to trigger a malicious Lambda function when a CloudFormation template is uploaded to the bucket. It can also create Lambda functions that trigger upon the creation of users, roles, and groups.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [S1164 - UPSTYLE](../../../Threat%20Intelligence/Software/Malware/S1164%20-%20UPSTYLE.md) — [UPSTYLE](https://attack.mitre.org/software/S1164) creates a `.pth` file beginning with the text `import` so that any time another process or script attempts to reference the modified item the malicious code will also run.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
- [S0658 - XCSSET](../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — [XCSSET](https://attack.mitre.org/software/S0658)'s `dfhsebxzod` module searches for `.xcodeproj` directories within the user’s home folder and subdirectories. For each match, it locates the corresponding `project.pbxproj` file and embeds an encoded payload into a build rule, target configuration, or project setting. The payload is later executed during the build process.(Citation: Microsoft March 2025 XCSSET)(Citation: April 2021 TrendMicro XCSSET) [Microsoft March 2025 XCSSET](https://www.microsoft.com/en-us/security/blog/2025/03/11/new-xcsset-malware-adds-new-obfuscation-persistence-techniques-to-infect-xcode-projects/) · [April 2021 TrendMicro XCSSET](https://www.trendmicro.com/en_us/research/21/d/xcsset-quickly-adapts-to-macos-11-and-m1-based-macs.html)

## Mitigations

- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Manage the creation, modification, use, and permissions associated to privileged accounts, including SYSTEM and root.
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Perform regular software updates to mitigate exploitation risk.

## Detection strategies

- [DET0010 - Behavioral Detection of Event Triggered Execution Across Platforms](../../../Defenses/Detection%20Strategies/DET0010%20-%20Behavioral%20Detection%20of%20Event%20Triggered%20Execution%20Across%20Platforms.md)

## Sources

- [FireEye WMI 2015](https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/wp-windows-management-instrumentation.pdf)
- [Microsoft DART Case Report 001](https://www.microsoft.com/security/blog/2020/03/09/real-life-cybercrime-stories-dart-microsoft-detection-and-response-team)
- [amnesia malware](https://researchcenter.paloaltonetworks.com/2017/04/unit42-new-iotlinux-malware-targets-dvrs-forms-botnet/)
- [Backdooring an AWS account](https://medium.com/daniel-grzelak/backdooring-an-aws-account-da007d36f8f9)
- [Varonis Power Automate Data Exfiltration](https://www.varonis.com/blog/power-automate-data-exfiltration)
- [Malware Persistence on OS X](https://www.virusbulletin.com/uploads/pdf/conference/vb2014/VB2014-Wardle.pdf)
