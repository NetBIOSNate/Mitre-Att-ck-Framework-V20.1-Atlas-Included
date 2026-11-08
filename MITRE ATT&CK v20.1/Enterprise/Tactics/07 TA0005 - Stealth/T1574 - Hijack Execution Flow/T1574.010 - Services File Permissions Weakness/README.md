# T1574.010 - Services File Permissions Weakness

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1574 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking the binaries used by services. Adversaries may use flaws in the permissions of Windows services to replace the binary that is executed upon service start. These service processes may automatically execute specific binaries as part of their functionality or to perform other actions. If the permissions on the file system directory containing a target binary, or permissions on the binary itself are improperly set, then the target binary may be overwritten with another binary using user-level permissions and executed by the original process. If the original process and thread are running under a higher permissions level, then the replaced binary will also execute under higher-level permissions, which could include SYSTEM.

Adversaries may use this technique to replace legitimate binaries with malicious ones as a means of executing code at a higher permissions level. If the executing process is set to run at a specific time or during a certain event (e.g., system bootup) then this technique can also be used for persistence.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1574/010)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Use auditing tools capable of detecting file system permissions abuse opportunities on systems within an enterprise and correct them. Toolkits like the PowerSploit framework contain PowerUp modules that can be used to explore systems for service file system permissions weaknesses.(Citation: Powersploit) [Powersploit](https://github.com/mattifestation/PowerSploit)
- [M1052 - User Account Control](../../../../Defenses/Mitigations/M1052%20-%20User%20Account%20Control.md) — Turn off UAC's privilege elevation for standard users <code>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System]</code>to automatically deny elevation requests, add: <code>"ConsentPromptBehaviorUser"=dword:00000000</code>. Consider enabling installer detection for all users by adding: <code>"EnableInstallerDetection"=dword:00000001</code>. This will prompt for a password for installation and also log the attempt. To disable installer detection, instead add: <code>"EnableInstallerDetection"=dword:00000000</code>. This may prevent potential elevation of privileges through exploitation during the process of UAC detecting the installer, but will allow the installation process to continue without being logged.(Citation: Executable Installers are Vulnerable) [Executable Installers are Vulnerable](https://seclists.org/fulldisclosure/2015/Dec/34)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit privileges of user accounts and groups so that only authorized administrators can interact with service changes and service binary target path locations. Deny execution from user directories such as file download directories and temp directories where able.

## Detection strategies

- [DET0436 - Detection Strategy for Hijack Execution Flow through Services File Permissions Weakness.](../../../../Defenses/Detection%20Strategies/DET0436%20-%20Detection%20Strategy%20for%20Hijack%20Execution%20Flow%20through%20Services%20File%20Permissions%20Weakne.md)

## Procedure examples

- [S0089 - BlackEnergy](../../../../Threat%20Intelligence/Software/Malware/S0089%20-%20BlackEnergy.md) — One variant of [BlackEnergy](https://attack.mitre.org/software/S0089) locates existing driver services that have been disabled and drops its driver component into one of those service's paths, replacing the legitimate executable. The malware then sets the hijacked service to start automatically to establish persistence.(Citation: F-Secure BlackEnergy 2014) [F-Secure BlackEnergy 2014](https://blog-assets.f-secure.com/wp-content/uploads/2019/10/15163408/BlackEnergy_Quedagh.pdf)
